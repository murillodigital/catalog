# How to set up a helm repo using GitHub Pages

1. https://harness.io/blog/helm-chart-repo (Step 1 - 3)
2. Get the right GitHub actions from the original repo or copy the actions here
  
## Usage
Just add the chart to `./charts` and the let the GH Action do the rest. 

## Test
```
helm repo add tony https://tonyjchong.github.io/weave-profiles
helm search repo tony
helm install 