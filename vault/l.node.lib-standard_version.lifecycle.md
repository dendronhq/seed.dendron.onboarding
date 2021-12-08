---
id: 2e9d2d82-c254-4150-870b-073d379f15a7
title: lifecycle
desc: ''
updated: 1595516653869
created: 1595516653869

---


- prerelease: executed before anything happens. If the prerelease script returns a non-zero exit code, versioning will be aborted, but it has no other effect on the process.
- prebump/postbump: executed before and after the version is bumped. If the prebump script returns a version #, it will be used rather than the version calculated by standard-version.
- prechangelog/postchangelog: executes before and after the CHANGELOG is generated.
- precommit/postcommit: called before and after the commit step.
- pretag/posttag: called before and after the tagging step.


```json
{
  "standard-version": {
    "scripts": {
      "prebump": "echo 9.9.9"
    }
  }
}
```

# Cook

### skip a step

{
  "standard-version": {
    "skip": {
      "changelog": true
    }
  }
}
