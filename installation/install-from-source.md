# Install from source

This guide provides instructions for installing and setting up the project from source.

**Important Note for Developers:** This project uses a custom versioning scheme for development builds that may not strictly adhere to PEP 440 for PyPI. This guide includes steps to manage that for local development.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

* **Git:** For cloning the project repository.
  * [Installation Guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* **uv:** A fast Python package installer and resolver.
  * Follow the official installation instructions: [uv Installation Guide](https://docs.astral.sh/uv/getting-started/installation/)

## Installation Steps

Follow these steps to get your project up and running:

### 1. Clone the Repository

First, clone the project from its Git repository:

```
git clone https://github.com/datawhores/OF-Scraper/
cd OF-Scraper
```

### 2. Pull the Latest Tags

To ensure you have access to all version information, pull the Git tags:

Bash

```
git pull --tags
```

### 3. Prepare Environment Variables (for Custom Versioning)

The project uses a custom versioning strategy for local development and CI/CD that overrides the default PEP 440 checks during the build process. You need to source a script to set the necessary environment variables:

Bash

```
source scripts/commit_version.sh
```

This script will set variables that allow Hatch to correctly interpret and build the project's development versions.

### 4. Create a Python Virtual Environment

It's highly recommended to use a virtual environment to isolate your project's dependencies from your system's Python installation. `uv` can create these for you:

Bash

```
uv venv
```

This will create a new virtual environment named `.venv` (by default) in your project directory.

### 5. Activate the Virtual Environment

Before installing dependencies, you need to activate the virtual environment:

Bash

```
source .venv/bin/activate
```

_(On Windows, you would typically use `.\.venv\Scripts\activate`)_

You should see `(.venv) or OF-Scraper` or similar prefix in your terminal prompt, indicating the virtual environment is active.

### 6. Install Project Dependencies

Now, use `uv` to install all project dependencies and reinstall any existing ones to ensure a clean state:

Bash

```
uv sync --reinstall
```

This command will read your `pyproject.toml` (or `requirements.txt`) and install all necessary packages into your activated virtual environment. The `--reinstall` flag ensures that if any packages are already present, they are reinstalled, which can be useful after pulling updates.
