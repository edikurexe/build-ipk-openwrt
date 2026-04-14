# build-ipk-openwrt

GitHub Actions workflow for building OpenWrt IPK packages from an external GitHub repository and publishing the build result as a GitHub Release.

## What this repository does
- Detects the latest stable OpenWrt release automatically
- Downloads the matching OpenWrt SDK
- Builds packages for:
  - x86-64
  - armvirt-64
- Pulls package sources from an external GitHub repository
- Publishes generated `.ipk` artifacts to a GitHub Release

## Workflow inputs
The workflow can be triggered manually with these inputs:
- `source_repo_url` — GitHub repository containing the package source
- `branch` — source branch (default: `main`)
- `subdir` — optional subdirectory inside the source repository
- `package_name` — package folder name to build
- `make_flags` — optional extra flags passed to `make`
- `release_tag` — optional custom release tag
- `release_name` — optional custom release name
- `draft` — create the release as draft
- `prerelease` — mark the release as pre-release

## Typical use case
Use this repository when you want a lightweight way to compile an OpenWrt package from a GitHub source repository without maintaining a full local OpenWrt build environment.

## Main stack
- GitHub Actions
- OpenWrt SDK
- Shell / Bash

## Notes
This repository is intended as a practical automation utility for package build workflows around OpenWrt.
