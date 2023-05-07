# gdextension

GDExtension template that automatically builds into a self-contained addon for the Godot Asset Library.

### Getting started:

1. Clone this repository (or a new repository with this template) with submodules.
    - `git clone --recurse-submodules https://github.com/nathanfranke/gdextension.git` \
    - `cd gdextension`
2. Update to the latest `godot-cpp`.
    - `git submodule update --remote`
2. Build a debug binary for the current platform.
    - `CTRL + Shift + P` -> `Run Task` -> `build godot_cpp debug` (only for the first time)
    - Inside [launch.json](.vscode/launch.json) set the program path to the path to your godot executable.
    - For Debugging in VS Code you can now just press `F5` or select `Run`->`Start Debugging` in the menu bar
3. Run the project inside Godot and check the output:
   ```
   Hello GDScript!
   Hello GDExtension Node!
   Hello GDExtension Singleton!
   ```

An official guide can be found [here](https://docs.godotengine.org/en/stable/tutorials/scripting/gdextension/gdextension_cpp_example.html#doc-gdextension-cpp-example)

### Repository structure:
- `project/` - Godot project boilerplate.
  - `addons/example/` - Files to be distributed to other projects.¹
  - `demo/` - Scenes and scripts for internal testing. Not strictly necessary.
- `src/` - Source code of this extension.
- `godot-cpp/` - Submodule needed for GDExtension compilation.

¹ Before distributing as an addon, all binaries for all platforms must be built and copied to the `bin/` directory. This is done automatically by GitHub Actions.

### Make it your own:
1. Rename `project/addons/example/` and `project/addons/example/example.gdextension`.
2. Replace `LICENSE`, `README.md`, and your code in `src/`.
3. Not required, but consider leaving a note about this template if you found it helpful!

### Distributing your extension on the Godot Asset Library with GitHub Actions:
1. Go to Repository→Actions and download the latest artifact.
2. Test the artifact by extracting the addon into a project.
3. Create a new release on GitHub, uploading the artifact as an asset.
4. On the asset, Right Click→Copy Link to get a direct file URL. Don't use the artifacts directly from GitHub Actions, as they expire.
5. When submitting/updating on the Godot Asset Library, Change "Repository host" to `Custom` and "Download URL" to the one you copied.
