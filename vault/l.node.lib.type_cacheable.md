---
id: d45e603f-b2e4-4140-bb23-fe3a122b071e
title: Lib-type_cacheable
desc: ''
updated: 1598636241982
created: 1598636241982
stub: false
link: 'https://github.com/joshuaslate/type-cacheable'
---

# Gotcha
- everything decorated becomes a promise

# Example
```ts
import * as Redis from 'redis';
import { Cacheable, CacheClear } from '@type-cacheable/core';

const userClient = Redis.createClient();

class TestClass {
  public aProp: string = 'aVal!';

  private userRepository: Repository<User>;

  // This static method is being called to generate a cache key based on the given arguments.
  // Not featured here: the second argument, context, which is the instance the method
  // was called on.
  static setCacheKey = (args: any[]) => args[0];

  // If getUserById('123') were called, the return value would be cached
  // in a hash under user:123, which would expire in 86400 seconds
  @Cacheable({
    cacheKey: TestClass.setCacheKey,
    hashKey: 'user',
    client: userClient,
    ttlSeconds: 86400,
  })
  public async getUserById(id: string): Promise<any> {
    return this.userRepository.findOne(id);
  }

  // If getProp('123') were called, the return value would be cached
  // under 123 in this case for 10 seconds
  @Cacheable({ cacheKey: TestClass.setCacheKey, ttlSeconds: (args) => args[1] })
  public async getProp(id: string, cacheForSeconds: number): Promise<any> {
    return this.aProp;
  }

  // If setProp('123', 'newVal') were called, the value cached under
  // key 123 would be deleted in this case.
  @CacheClear({ cacheKey: TestClass.setCacheKey })
  public async setProp(id: string, value: string): Promise<void> {
    this.aProp = value;
  }
}

```

# Use Use adapter directly

```ts
import cacheManager from '@type-cacheable/core';
import keyGenerator from './utils/cacheKeyGenerator';

class UserService {
  private userRepository: Repository<User>;
  private rolesRepository: Repository<Role>;

  public async blockUser(id: string): Promise<void> {
    await this.userRepository.update({ id }, { isBlocked: true });
    const key = keyGenerator([id], CacheKey.UserRoles);
    await cacheManager.client?.del(key);
  }

  public async getUserDetails(id: string): Promise<UserWithRoles> {
    const key = keyGenerator([id], CacheKey.UserRoles);

    let userRoles = await cacheManager.client?.get(key);
    if (!userRoles) {
      userRoles = await this.rolesRepository.find({ userId: id });
      await cacheManager.client?.set(key, userRoles, 3600);
    }

    const user = await this.userRepository.findOne(id);

    return { ...user, userRoles };
  }
}
```
