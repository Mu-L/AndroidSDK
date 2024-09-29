# Contribute

Contributions are made by forking this repository, making the changes, and opening a pull request.

## Update Guide

[README](./README.md) is the first place where people are looking for help.  Please remember to add or update the corresponding part in README, especially the hidden piece which is not told by code.

## Create A New Docker Image For Different Purpose

The [primary Docker image](./android-sdk/Dockerfile) was created in barebone, for the sake of providing Android environment only.  If you have other needs, please build a dedicated Docker image:

* Create a specific directory under [android-sdk](./android-sdk) directory and a `Dockerfile` inside it.
* A `version-inspector.sh` file is necessary to print out tools' version information.
* Update corresponding CI workflow: [GitHub Action](https://github.com/thyrlian/AndroidSDK/blob/master/.github/workflows/docker-image.yml).
* Add corresponding Docker image building and publishing steps to [`image-publisher.sh`](./image-publisher.sh) script.

## Accept New SDK Licenses

Update the script [`android-sdk/license-accepter.sh`](./android-sdk/license-accepter.sh) with the new agreement checksums.  Do not remove pre-existing license agreement acceptances.

If a new agreement is accepted, a file should be created in the directory [`EULA`](./EULA).  If there is an update, ensure the agreements contain a suffix with the timestamp in the format `-YYYYMMDD`.

## Pass All Checks

Make sure that all [tests](https://github.com/thyrlian/AndroidSDK/actions/workflows/docker-image.yml) pass on the CI.
