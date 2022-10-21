# Weave Catalog

This repo represents ceritifed Weave GitOps Profiles and Templates to be used with Weave GitOps Enterprise (WGE). 


# Developing

Our default branch is `main`. We consider all code in `main` as production, and should be in sync with the latest version of each release. 

Those who would like to contribute to this repository should create a branch with a naming convention that is:

`<username>/something-short-that-makes-sense`

for example:
`tonyjchong/reset-everything`


# How to create / update a Profile
A profile is basically a helm chart located in the `charts` directory. 

If you want your chart to show up as a `Profile` in WGE, then you must add the follow block in your `Chart.yaml` file. 

```
annotations:
  "weave.works/profile": <profile-name>
  # The following 2 are optional but come in handy
  "weave.works/category": <Category>
  "weave.works/layer": <layer-X>
```


## Creating a PR
When you create a PR to merge into `main`, let someone on the Platform Dev Team to review. Once the change is merged, the GitHub action will publish the update for use.  

## Test


## Resetting everyting

* Delete all releases using the GH command. This only does 10 at a time so keep running it until the list is empty
`gh release list | sed 's/|/ /' | awk '{print $1}' | while read -r line; do gh release delete -y "$line"; done`



* Delete all the tags
```
git fetch
git tag -l | xargs -n 1 git push --delete origin
```

