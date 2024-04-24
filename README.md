# Install Mesa on Windows Action

This GitHub Action download, extract and install mesa binary release
from https://github.com/pal1000/mesa-dist-win into a designated folder.

Just add this to your workflow:
```yaml
  - name: Install Mesa Windows
    uses: f3d-app/install-mesa-windows-action@v1
    with:
      path: ${{github.workspace}}/path/to/folder
```

Any executable in that directory using `opengl32.dll` and other mesa related libraries
will then just work out of the box.

Note that this action will define `GALLIUM_DRIVER` environnement variable that is needed for mesa to work as expected.

The path can contain wildcards, which means the mesa files can be copied to multiple directories in a single action use.
If the directories do not exists, they will be created.

## Defining mesa version

Which mesa version to use can be set like this:

```yaml
  - name: Install Mesa Windows
    uses: f3d-app/install-mesa-windows-action@v1
    with:
      path: ${{github.workspace}}/path/to/folder
      version: 24.0.5
```

Please note only the default version is tested by the CI of this repository.
