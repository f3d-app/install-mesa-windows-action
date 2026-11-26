# Install Mesa on Windows Action

This GitHub Action download, extract and install mesa binary release
from https://github.com/mmozeiko/build-mesa/ into a designated folder.

Just add this to your workflow:
```yaml
  - name: Install Mesa Windows
    uses: f3d-app/install-mesa-windows-action@v1
    with:
      path: ${{github.workspace}}/path/to/folder
```

Any executable in that directory using `opengl32.dll` or `libEGL.dll` will then just work out of the box.

The path can contain wildcards, which means the mesa files can be copied to multiple directories in a single action use.
If the directories do not exists, they will be created.

Note: `libEGL.dll` support is currently experimental and not tested in CI.

## Defining mesa version

Which mesa version to use can be set like this:

```yaml
  - name: Install Mesa Windows
    uses: f3d-app/install-mesa-windows-action@v1
    with:
      path: ${{github.workspace}}/path/to/folder
      version: 24.0.5
```

Note: Only `26.3.1` (default) version is tested in CI.

## Defining implementation

Which mesa implementation to use can be set like this:

```yaml
  - name: Install Mesa Windows
    uses: f3d-app/install-mesa-windows-action@v1
    with:
      path: ${{github.workspace}}/path/to/folder
      implementation: d3d12
```

Note: Only `llvmpipe` (default) and `d3d12` are tested in CI and known to work properly.

## Defining CPU architecture

Which CPU architecture to use can be set like this:

```yaml
  - name: Install Mesa Windows
    uses: f3d-app/install-mesa-windows-action@v1
    with:
      path: ${{github.workspace}}/path/to/folder
      cpu: arm64
```

Note: Only `x64` (default), is tested in CI.
