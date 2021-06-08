---
id: 7154111a-bcc0-4596-b04a-770e69f0ac9f
title: Unittest
desc: ''
updated: 1600019385806
created: 1600019385806
stub: false
---



```python
class TestFoo(unittest.TestCase) :
    def setUp(self):
        pass

    def test_queries(self):
        self.assertTrue(get_url(self.url+"q=erik")[0]) #normal query
        #self.assertRaises(Exception, get_url, self.url+"q=") #test with blank

if __name__ == '__main__':
    unittest.main()
```
