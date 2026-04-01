# Stride Dependencies

Build workflows and prebuilt binaries for third-party dependencies used by the [Stride](https://github.com/stride3d/stride) game engine.

This repo is added as a git submodule in the Stride repo at `build/submodules/deps`.

## How it works

Each dependency has a GitHub Actions workflow that can be triggered manually via `workflow_dispatch`. The workflow builds the dependency from source and commits the resulting binaries back to this repo.

To update a dependency:

1. Trigger the relevant workflow from the **Actions** tab
2. The workflow builds and commits the updated binaries automatically
3. In the Stride repo, update the submodule to pick up the new commit

## Dependencies

| Dependency | Directory | Workflow | Purpose |
|---|---|---|---|
| [SwiftShader](https://github.com/google/swiftshader) | `swiftshader/` | `build-swiftshader.yml` | CPU-based Vulkan ICD for GPU testing in CI without hardware |
