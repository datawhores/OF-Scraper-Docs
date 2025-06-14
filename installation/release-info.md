---
description: >-
  This page provides an overview of the different release types, versioning, and
  file formats for OF-Scraper.
---

# Release Info

## Release Types

OF-Scraper uses distinct release types to indicate stability and origin.

### Continuous Development Builds (Snapshot Releases)

These releases are generated directly from recent commits on development branches (like `main`). They represent the absolute latest state of the codebase and typically include a commit hash in their name.

* Naming Convention: Often includes a branch name, a short commit hash, and the **date of the associated commit for chronological sorting** (e.g., 3.13.dev8-a70aca3e)
* **Stability:** These are bleeding-edge versions and may contain new features, bug fixes, or unresolved issues. They are primarily for testing and development.
* **Example Tag:** `main-9e54ed3-1749940070` &#x20;

### Pre-release Versions (e.g., `X.Y.Z.devN`)

These releases are designated as "semi-stable" and are pushed for broader testing before a full stable release. They typically follow a `major.minor.patch.devN` numbering scheme.

* **Naming Convention:** Follows the format `major.minor.patch.devN` (e.g., `3.7.0.dev0`).
* **Stability:** More stable than continuous development builds, but still undergoing testing.
* **Example Version:** `3.7.0.dev0`

### Stable Releases (Numbered)

These are production-ready versions of OF-Scraper, thoroughly tested and considered stable for general use. They mark a specific commit as a reliable release point.

* **Naming Convention:** Standard semantic versioning (e.g., `X.Y.Z`, like `3.6.0`).
* **Stability:** Highly stable and recommended for most users.
* **Example Version:** `3.6.0`

***

## Release Distributions

### Python Package

Stable and pre-release versions of the Python package are hosted on **PyPI**

For a comprehensive history of all releases (including pre-releases), visit the official PyPI page:&#x20;

{% embed url="https://pypi.org/project/ofscraper/#history" %}

### Docker Images

Stable, pre-release, and dev versions of multi-arch Docker images are hosted on **GitHub Container Registry** and **Docker Hub**

{% embed url="https://hub.docker.com/r/datawhores/of-scraper/tags" %}

{% embed url="https://github.com/datawhores/OF-Scraper/pkgs/container/of-scraper" %}

### Binaries

Stable, pre-release, and dev versions are released as binaries on **GitHub** for Windows, macOS, and Linux



{% embed url="https://github.com/datawhores/OF-Scraper/releases" %}

#### Release Files

Binaries include various file types **compatible with different platforms**

#### Example Files

Below is an illustrative list of files you might find in a release, with common naming patterns.

* `ofscraper_windows_x64.zip` (Windows zips)
* `ofscraper_linux` (Linux script)
