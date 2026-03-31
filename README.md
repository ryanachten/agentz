# agentz

Personal shared agent and skill configurations.

## Commands

### Install
```bash
npx github:ryanachten/agentz --install
```
Adds shared agents to `.agents/shared/` as a git submodule.

### Update
```bash
npx github:ryanachten/agentz --update
```
Updates shared agents to the latest version.

### Uninstall
```bash
npx github:ryanachten/agentz --uninstall
```
Removes shared agents from your project.

## Usage

After installing, shared skills are available in `.agents/shared/`. Reference them in your workspace configuration or `.instructions.md`:

```
.agents/shared/skills/[skill-name]/SKILL.md
```

## Requirements

- Git (for submodule operations)
- npm/Node.js (to run via npx)
- Git repository (your project must be initialized with git)

## Notes

### Git Integration Options

**Option 1: Commit submodule (recommended for teams)**
- Commit `.gitmodules` and `.agents/shared` to version control
- Locks the team to a specific agent version
- Cloners use `git clone --recursive` to fetch agents automatically
- Or after cloning: `git submodule update --init --recursive`

**Option 2: Add to .gitignore (for developer flexibility)**
- Add `.agents/` to `.gitignore`
- Each developer runs `npx agentz --install` independently
- No version lock—developers can use different agent versions
- Lighter git footprint
