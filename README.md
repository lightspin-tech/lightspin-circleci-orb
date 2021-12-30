# LightSpin IaC CircleCI Orb

## Description
The LightSpin Orb enables you to call a LightSpin IaC scan on IaC files that exists on your repository.
The scan results are displayed in the LightSpin platform.

## Usage
```yaml
version: 2.1
orbs:
  lightspin-orb: lightspin-tech/lightspin@1.0.0
workflows:
  invoke-iac:
    jobs:
      - lightspin-orb/lightspin_scan:
            path-to-scan: "terraform"
            friendly-name: $CIRCLE_BUILD_NUM'_circle_CI'
            token: "LS_TOKEN"
            tenant-id: "LS_TENANT"          
```
- "path-to-scan" is the path to the IaC files to be scaned in your repostory.
- "friendly-name" will be the name displayed in the LightSpin IaC platform for your new scan.
- "token" is the environment variable name that holds the LightSpin platform token
- "tenant-id" is the environment variable name that holds the LightSpin tenant ID

Make sure to initialize the mentioned environemnt variables with the required value before running the orb in a pipeline.
