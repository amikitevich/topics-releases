# topics-releases
Standalone Topics application downloads. Source code is maintained separately.

## Agent skill

`skills/tcs/SKILL.md` tells AI coding agents to use the `tcs` command for your topics.
Install Topics first, then install the skill with the [skills](https://github.com/vercel-labs/skills) installer:

```sh
npx skills add amikitevich/topics-releases
```

The installer asks which agents to supply, such as Claude Code, OpenCode, Gemini CLI or Codex.
Add `-g` to install for your user instead of the current project.
