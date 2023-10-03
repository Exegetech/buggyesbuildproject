# Buggy EsBuild

Repo for reproduction of stale build in `esbuild`.

## Steps To Reproduce
This below steps don't work as expected:
1. Run `bazel clean` to make sure we start from a clean slate
2. `git checkout HEAD~1` to checkout commit that says "Using Util.ts"
3. Run `bazel build //mypackage:build`
4. Observe that it builds
5. `git checkout master` to checkout commit that says "Using util/index.ts"
6. Run `bazel build //mypackage:build`
7. Observe that it does not build

What should happen: It should build correctly.

