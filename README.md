# Topics

Topics keeps outlines of items with notes in plain Markdown files.
Use the `tcs` command in a terminal, or use the Things web application in a browser.

This repository contains release downloads and the agent skill. Source code is maintained separately.

## Install Topics

Topics supports macOS Apple Silicon and Linux x64 with glibc. Windows is not supported.
You do not need Bun, Node, a source checkout or administrator access.

1. Download the installer:

   ```sh
   curl --proto '=https' --tlsv1.2 -fsSL \
     https://github.com/amikitevich/topics-releases/releases/latest/download/install.sh \
     -o install-topics.sh
   ```

2. Inspect `install-topics.sh` before you run it.
3. Run the installer:

   ```sh
   sh install-topics.sh
   ```

4. Make sure that `~/.local/bin` is in your shell `PATH`.
5. Check the installation:

   ```sh
   tcs --version
   ```

To update, run the same installer again. Then restart `tcs web`.
The installer does not change your topics.

To install a specific version, download the installer from that [release](https://github.com/amikitevich/topics-releases/releases) and add `--version vMAJOR.MINOR.PATCH`.
macOS programs are unsigned. macOS can ask you to approve them.

## Install the agent skill

The skill tells AI coding agents to use `tcs` for your topics.
Install Topics first.

Use the `tcs` command:

```sh
tcs skill install
```

This installs the skill for your user in `~/.agents/skills` and `~/.claude/skills`.
These locations supply Claude Code, OpenCode, Gemini CLI, Codex and other agents.

Other options:

```sh
tcs skill install --agent claude,gemini   # Only the named agents
tcs skill install --project               # The current project only
tcs skill show                            # Print the skill
```

You can also use the [skills](https://github.com/vercel-labs/skills) installer with `skills/tcs/SKILL.md` from this repository:

```sh
npx skills add amikitevich/topics-releases
```

The installer asks which agents to supply. Add `-g` to install for your user instead of the current project.

Installing the skill does not change topics or start a server.

## Common commands

Set your topic directory one time. The directory must exist:

```sh
tcs config set vault "/path/to/topics"
```

Start the web application:

```sh
tcs web
```

Open the printed URL, for example `http://127.0.0.1:4317`. Keep the terminal open. Press Ctrl+C to stop the server.

Use a different port or a different topic directory:

```sh
tcs web --port 4318
tcs web --vault ./other-topics
```

Read topics in the terminal:

```sh
tcs list                 # All topics
tcs outline ideas        # The items of one topic
tcs --help               # All commands
tcs help add             # Help for one command
```

**Warning:** The web application has no authentication. Do not expose it publicly.
It listens only on `127.0.0.1`.

## More information

Each release archive contains these guides:

| File          | Contents                                              |
| ------------- | ----------------------------------------------------- |
| `README.md`   | Installation, updates and data boundaries             |
| `CLI.md`      | Commands, selectors, input, receipts and errors       |
| `THINGS.md`   | Browser controls, drafts and conflicts                |
| `FORMAT.md`   | Marked headings, metadata, notes and resolution       |
| `RECOVERY.md` | Locks, journals and recovery commands                 |
| `SKILL.md`    | The agent skill                                       |

After installation, the guides are in `~/.local/share/topics/current/`.
