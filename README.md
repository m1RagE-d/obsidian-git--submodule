# Git Submodule for Obsidian

This is a beginner-made, Codex-assisted fork of the excellent [Obsidian Git](https://github.com/Vinzent03/obsidian-git) plugin. I made it while learning, so please treat it as an experimental fork rather than a polished official plugin.

The goal of this fork is simple: keep the familiar Obsidian Git workflow, but add a more practical UI for vaults that use Git submodules. It also adds a compact Git graph view for browsing commit history in a style similar to VS Code.

## What This Fork Adds

### Submodule Source Control

The new Submodules view works like a small multi-repository source control panel. Each submodule can be expanded and managed separately:

-   View branch, upstream, current commit, clean/dirty state, and ahead/behind counts.
-   Stage or unstage individual files inside a submodule.
-   Stage all, unstage all, or discard working tree changes for a submodule.
-   Inspect file diffs directly from the submodule panel.
-   Commit changes inside a submodule with its own commit message.
-   Pull or push an individual submodule.
-   Add, initialize, update, sync, deinitialize, or remove submodules from the UI.

Submodule features require the desktop version of Obsidian because they use the native Git binary.

### Git Graph View

This fork also adds a Git Graph view that visualizes commits, branches, merges, refs, authors, and dates. It is meant to be a lightweight graph similar in spirit to the Git graph experience in VS Code.

Open it from the command palette with `Open Git graph view`, or from the Source Control view toolbar.

## Original Plugin

## 📚 Documentation

All setup instructions (including mobile), common issues, tips, and advanced configuration can be found in the 📖 [full documentation](https://publish.obsidian.md/git-doc).

> Mobile users: The plugin is **highly unstable ⚠️ !** Please check the dedicated [Mobile](#-mobile-support-%EF%B8%8F--experimental) section below.

## Key Features

-   🔁 **Automatic commit-and-sync** (commit, pull, and push) on a schedule.
-   📥 **Auto-pull on Obsidian startup**
-   📂 **Submodule support** for managing multiple repositories (desktop only and opt-in)
-   🔧 **Source Control View** to stage/unstage, commit and diff files - Open it with the `Open source control view` command.
-   📜 **History View** for browsing commit logs and changed files - Open it with the `Open history view` command.
-   🌿 **Git Graph View** for a branch/merge visualization similar to VS Code - Open it with the `Open Git graph view` command.
-   🧩 **Submodules View** to add, initialize, update, sync, pull, push, deinit, and remove submodules - Open it with the `Open submodules view` command.
-   🔍 **Diff View** for viewing changes in a file - Open it with the `Open diff view` command.
-   📝 **Signs in the editor** to indicate added, modified, and deleted lines/hunks (desktop only).
-   GitHub integration to open files and history in your browser

> For detailed file history, consider pairing this plugin with the [Version History Diff](obsidian://show-plugin?id=obsidian-version-history-diff) plugin.

## UI Previews

### 🔧 Source Control View

Manage your file changes directly inside Obsidian like stage/unstage individual files and commit them.

![Source Control View](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/source-view.png)

### 📜 History View

Show the commit history of your repository. The commit message, author, date, and changed files can be shown. Author and date are disabled by default as shown in the screenshot, but can be enabled in the settings.

![History View](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/history-view.png)

### 🌿 Git Graph View

Visualize commits, branches, merges, tags, authors, and dates in a compact graph similar to VS Code's Git graph style. Open it via the `Open Git graph view` command. Desktop only.

### 🧩 Submodules View

Manage submodules from Obsidian in a multi-repository source control panel. Each submodule can be expanded like its own repository, with branch/upstream metadata, ahead/behind counts, staged changes, working tree changes, file diffs, stage/unstage/discard actions, and its own commit box. The view also provides buttons to open, pull, push, deinitialize, or remove a submodule, plus toolbar actions to add a submodule, initialize missing submodules, update recursively, sync URLs from `.gitmodules`, and refresh.

### 🔍 Diff View

Compare versions with a clear and concise diff viewer.
Open it from the source control view or via the `Open diff view` command.

![Diff View](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/diff-view.png)

### 📝 Signs in the Editor

View line-by-line changes directly in the editor with added, modified, and deleted line/hunk indicators. You can stage and reset changes right from the signs. There also commands to navigate between hunks and stage/reset hunks under the cursor. Needs to be enabled in the plugin settings.

![Signs](https://raw.githubusercontent.com/Vinzent03/obsidian-git/master/images/signs.png)

## Available Commands

> Not exhaustive - these are just some of the most common commands. For a full list, see the Command Palette in Obsidian.

-   🔄 Changes
    -   `List changed files`: Lists all changes in a modal
    -   `Open diff view`: Open diff view for the current file
    -   `Stage current file`
    -   `Unstage current file`
    -   `Discard all changes`: Discard all changes in the repository
-   ✅ Commit
    -   `Commit`: If files are staged only commits those, otherwise commits only files that have been staged
    -   `Commit with specific message`: Same as above, but with a custom message
    -   `Commit all changes`: Commits all changes without pushing
    -   `Commit all changes with specific message`: Same as above, but with a custom message
-   🔀 Commit-and-sync
    -   `Commit-and-sync`: With default settings, this will commit all changes, pull, and push
    -   `Commit-and-sync with specific message`: Same as above, but with a custom message
    -   `Commit-and-sync and close`: Same as `Commit-and-sync`, but if running on desktop, will close the Obsidian window. Will not exit Obsidian app on mobile.
-   🌐 Remote
    -   `Push`, `Pull`
    -   `Edit remotes`: Add new remotes or edit existing remotes
    -   `Remove remote`
    -   `Clone an existing remote repo`: Opens dialog that will prompt for URL and authentication to clone a remote repo
    -   `Open file on GitHub`: Open the file view of the current file on GitHub in a browser window. Note: only works on desktop
    -   `Open file history on GitHub`: Open the file history of the current file on GitHub in a browser window. Note: only works on desktop
-   🏠 Manage local repository
    -   `Initialize a new repo`
    -   `Create new branch`
    -   `Delete branch`
    -   `CAUTION: Delete repository`
-   🧩 Submodules
    -   `Open submodules view`: Manage submodules in a side pane
    -   `Submodules: Init`: Run `git submodule update --init --recursive`
    -   `Submodules: Update`: Run `git submodule update --init --remote --merge --recursive`
    -   `Submodules: Sync URLs`: Run `git submodule sync --recursive`
-   🧪 Miscellaneous
    -   `Open source control view`: Opens side pane displaying [Source control view](#sidebar-view)
    -   `Open history view`: Opens side pane displaying [History view](#history-view)
    -   `Open Git graph view`: Opens side pane displaying [Git Graph View](#-git-graph-view)
    -   `Edit .gitignore`
    -   `Add file to .gitignore`: Add current file to `.gitignore`

## 🧩 Submodule Usage

Submodule management is desktop only because it relies on the native Git binary. Existing automatic support still works through the `Update submodules` setting: `Commit-and-sync` can commit and push submodule changes, and `Pull` can update submodules recursively.

For manual control, use `Open submodules view`. From there you can:

-   Add a new submodule by URL, path, and optional branch.
-   Initialize missing submodules after cloning a vault.
-   Update submodules from their configured remotes and merge into checked-out branches.
-   Sync URLs after editing `.gitmodules`.
-   Expand each submodule as a separate source control group.
-   Stage or unstage individual files, stage all, unstage all, discard working tree changes, and inspect file diffs.
-   Commit staged submodule changes with a submodule-specific commit message. If nothing is staged, the commit button stages that submodule's changes first.
-   Pull or push an individual initialized submodule.
-   Deinitialize or remove a submodule from the repository.

Recommended setup for each submodule:

-   Keep the submodule checked out on a branch, not just a detached commit.
-   Configure an upstream branch if you want pull/push buttons and automatic sync to work smoothly.
-   Commit the superproject after changing the submodule commit pointer or `.gitmodules`.

## 💻 Desktop Notes

### 🔐 Authentication

Some Git services may require further setup for HTTPS/SSH authentication. Refer to the [Authentication Guide](https://publish.obsidian.md/git-doc/Authentication)

### Obsidian on Linux

-   ⚠️ Snap is not supported due to its sandboxing restrictions.
-   ⚠️ Flatpak is not recommended, because it doesn't have access to all system files. They are actively fixing many issues, but there are still issues. Especially with more advanced setups.
-   ✅ Please use AppImage or a full access installation of your system's package manager instead ([Linux installation guide](https://publish.obsidian.md/git-doc/Installation#Linux))

## 📱 Mobile Support (⚠️ Experimental)

The Git implementation on mobile is **very unstable**! I would not recommend using this plugin on mobile, but try other syncing services.

One such alternative is [GitSync](https://github.com/ViscousPot/GitSync), which is available on both Android and iOS. It is not associated with this plugin, but it may be a better option for mobile users. A tutorial for setting it up can be found [here](https://viscouspotenti.al/posts/gitsync-all-devices-tutorial).

> 🧪 The Git plugin works on mobile thanks to [isomorphic-git](https://isomorphic-git.org/), a JavaScript-based re-implementation of Git - but it comes with serious limitations and issues. It is not possible for an Obsidian plugin to use a native Git installation on Android or iOS.

### ❌ Mobile Feature Limitations

-   No **SSH authentication** ([isomorphic-git issue](https://github.com/isomorphic-git/isomorphic-git/issues/231))
-   Limited repo size, because of memory restrictions
-   No rebase merge strategy
-   No submodules support

### ⚠️ Performance Caveats

> [!caution]
> Depending on your device and available free RAM, Obsidian may
>
> -   crash on clone/pull
> -   create buffer overflow errors
> -   run indefinitely.
>
> It's caused by the underlying git implementation on mobile, which is not efficient. I don't know how to fix this. If that's the case for you, I have to admit this plugin won't work for you. So commenting on any issue or creating a new one won't help. I am sorry.

### Tips for Mobile Use:

If you have a large repo/vault I recommend to stage individual files and only commit staged files.

## 🙋 Contact & Credits

-   The Line Authoring feature was developed by [GollyTicker](https://github.com/GollyTicker), so any questions may be best answered by her.
-   This plugin was initial developed by [denolehov](https://github.com/denolehov). Since March 2021, it's me [Vinzent03](https://github.com/Vinzent03) who is developing this plugin. That's why the GitHub repository got moved to my account in July 2024.
-   If you have any kind of feedback or questions, feel free to reach out via GitHub issues.

## ☕ Support

If you find this plugin useful and would like to support its development, you can support me on Ko-fi.

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/F1F195IQ5)
