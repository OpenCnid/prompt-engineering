# prompt-engineering

> [!IMPORTANT]
> **This repository has moved into [OpenCnid/dovetail](https://github.com/OpenCnid/dovetail).**
>
> `prompt-engineering` is now one of nine skills in that pack, at
> [`skills/prompt-engineering/`](https://github.com/OpenCnid/dovetail/tree/main/skills/prompt-engineering).
> Install the whole pack with a plain clone — there are no submodules:
>
> ```bash
> git clone https://github.com/OpenCnid/dovetail.git
> cd dovetail && bash scripts/install.sh
> ```
>
> The eight skills were separate repositories while each was developed on its
> own. They are used together, so they are now maintained together; keeping them
> apart cost a pin-bumping step before every change and bought nothing a reader
> could see. This repository is archived and read-only. Its history is the record
> of how this skill got here, and `docs/provenance.md` in dovetail names the
> commit its content arrived at.


*Structural clarity and manifold alignment over "magic words."*

[![license](https://img.shields.io/badge/license-CC_BY_4.0-3b7ddd)](LICENSE.md)
![lineage](https://img.shields.io/badge/lineage-Lexideck_curriculum-9b8cf7)

A Claude Code skill that fires whenever you are authoring a prompt, template,
agent instruction, system prompt, or output schema and precision matters.

> **The credit belongs elsewhere and it is not a formality.** This skill is a
> compression of the **Lexideck Prompt Engineering Curriculum** by
> **[Matthew Murphy](https://github.com/gusthemole)** — "Talking to AIs
> Effectively," a nine-part series covering semantic tagging, hierarchical
> markers, structured placeholders, collections, and attention management. This
> repository ships the **deployed artifact, not the educational version.** The
> curriculum is the canonical authority; where the two differ, it wins.
>
> Full curriculum: [patreon.com/c/LexideckTechnologies](https://www.patreon.com/c/LexideckTechnologies)

## What it carries

Five tools, and a best-practice loop that keeps them honest:

| | |
|---|---|
| **Semantic tagging** | XML-style containers that stop context bleeding between blocks |
| **Hierarchical markers** | explicit outlining that matches the content's real depth |
| **Structured placeholders** | `${user input}`, `{objects}`, `[lists]`, `(options)` |
| **Collections** | how to shape multiple data points so a model can act on them |
| **Attention management** | where to put the thing that matters, and how to say it matters |

The master template is itself a **hypershot** — a frame with free variables
rather than filled-in examples. That technique has its own repository:
[OpenCnid/hypershot-protocol](https://github.com/OpenCnid/hypershot-protocol).

## The practice most people skip

> **Uncontaminated context.** A prompt for another agent carries exactly what
> that agent cannot derive cold and needs in order to look. What you expect it
> to find is content placed where it will be attended to — so the agent hands it
> back, and no report separates that from a finding. Most of all when the
> expectation is true.
>
> One question sorts it: *does this let the agent look, or does it tell the
> agent what looking will turn up?*

A held expectation has one destination and it is not a prompt. Put it to the
collaborator.

## Install

```bash
git clone https://github.com/OpenCnid/prompt-engineering.git
mkdir -p ~/.claude/skills
cp -r prompt-engineering/skills/prompt-engineering ~/.claude/skills/
```

**Do not skip the `mkdir`.** If `~/.claude/skills/` does not already exist, `cp`
reads the trailing path as a *rename target*: you get `~/.claude/skills/SKILL.md`
with no skill directory, exit code 0, and no error. The skill never loads and
nothing tells you why.

PowerShell:

```powershell
git clone https://github.com/OpenCnid/prompt-engineering.git
New-Item -ItemType Directory -Force ~/.claude/skills
Copy-Item -Recurse -Force prompt-engineering/skills/prompt-engineering ~/.claude/skills/
```

`-Force` matters on the second run — without it, an upgrade fails with *an item
with the specified name already exists*.

If you have set `CLAUDE_CONFIG_DIR`, that is your skills root, not `~/.claude`.

Or install it with the rest of the stack:
[OpenCnid/dovetail](https://github.com/OpenCnid/dovetail).

## House note

Across OpenCnid repositories, a session that authors prompt bytes invokes this
skill **and** `hypershot-protocol` first, before its first authored byte, and
authors against them. Invocations satisfy that; a commit message saying you read
them does not.

## License

Prose and skill: [CC BY 4.0](LICENSE.md) © OpenCnid Labs. The method is Matthew
Murphy's — credit the source, not just the application.
