---
id: 91a2f878-3e19-4e7d-baff-021ffee0882d
title: internal
desc: ''
updated: 1595516401406
created: 1595516401406

---

# --- Run standard-version
# Flows
## Summary
- Retrieve the current version of your repository by looking at bumpFiles[1], falling back to the last git tag.
- bump the version in bumpFiles[1] based on your commits.
- Generates a changelog based on your commits (uses conventional-changelog under the hood).
- Creates a new commit including your bumpFiles[1] and updated CHANGELOG.
- Creates a new tag with the new version number.

## Main
# Hiearchies
