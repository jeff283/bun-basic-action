# Bun Basic Action

A GitHub composite action that sets up [Bun](https://bun.sh) and runs your build process. This action automates the common workflow of checking out code, installing Bun, installing dependencies, and building your project.

## Features

-  **Fast Setup**: Automatically installs the latest version of Bun
-  **Dependency Management**: Runs `bun ci` for clean, reproducible dependency installation
-  **Build Automation**: Executes your build script using Bun
-  **Composite Action**: Easy to integrate into any workflow

## Usage

Add this action to your workflow:

```yaml
name: My Workflow

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Run Bun Basic Action
        uses: jeff283/bun-basic-action@main
```

## What This Action Does

This composite action performs the following steps:

1. **Checkout Code**: Uses `actions/checkout@v4` to checkout your repository
2. **Setup Bun**: Installs the latest version of Bun using `oven-sh/setup-bun@v2`
3. **Install Dependencies**: Runs `bun ci` to install dependencies from your lockfile
4. **Build**: Executes `bun run build` to build your application

## Requirements

Your repository should have:
- A `package.json` file with a `build` script defined
- A `bun.lockb` file (Bun's lockfile) for reproducible installs

## Example Repository Structure

```
your-repo/
├── package.json      # Must include a "build" script
├── bun.lockb        # Bun lockfile
├── index.ts         # Your source files
└── tsconfig.json    # TypeScript configuration (if using TypeScript)
```



## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.


## Author

Jeff Njoroge ([@jeff283](https://github.com/jeff283))
