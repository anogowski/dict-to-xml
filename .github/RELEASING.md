# Here are the steps on how to make a new release

1. Create a commit on branch `upstream/main`.
2. Create a version tag. Version should be in the form of "vx.y.z". ex: v1.0.9
3. Add version tag to commit
4. Push commit and tag: git push --atomic origin main v1.0.9
