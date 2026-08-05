# Record

Append-only. One entry per session. Nothing above a new entry is ever edited.

## 2026-08-04 · Audit the prompt-engineering skill against its source, then the stack around it

**Did** — In this repo, 7 commits on `d/prompt-engineering-improvements-461d89`
touching 6 files (+1066/−24): `SKILL.md` rebuilt at §A, §C, §E, the master
template and best practices 1 and 4; `DEVIATIONS.md` added (930 lines);
`LICENSE.md` gained a CC BY § 3(a)(1)(A) attribution carve-out naming Matthew
Murphy; `NOTICE` and a licence copy added inside the skill directory so credit
survives the documented install; `README.md` install command fixed.

Across five other repositories: `upsum` created, published public, 5 commits;
`judge-composition` 2 commits; `self-play` 4; `hypershot-protocol` 1; `dovetail`
3 (unpushed). All but dovetail pushed.

**Learned** — A spawned sub-agent receives the full skills listing and can
invoke any installed skill unprompted (3 of 3 trials on a matching task), and a
working-directory `.claude/skills/` loads as a project skill. Both were live
during an A/B run of this skill, so every arm and the control could reach both
versions under test. The run was void.

The curriculum resolved every open provenance question: §§A–E compress Parts
4–8; best practices 4 and 5 trace to Parts 1 and 9; practices 1 and 3 descend
from WonderPrompt rather than this curriculum; practice 6 and the master
template are house-authored. The lineage note claimed to compress "the Part 9
capstone" and did not.

Three separate defects were found today only as side effects of other work: an
install command that silently produced a broken install, references resolving
only inside one organisation (three repositories), and skill bodies past the
compaction prefix. None was found by looking.

**Decided** — Mark deviations rather than suppress them (Cnid). Murphy ruled
that `...` is a primitive composing inside containers, not a fifth container;
that a tag name is a categoric primitive drawn from an open vocabulary; that
hypershots are worked examples carrying form rather than shape, so the
curriculum and the companion skill are one practice at two altitudes; and that
the summary gradient runs newest-detailed to oldest-collapsed, not the reverse.

**Left** — dovetail unpushed: it is the one repository with no URL supplied, so
the push is the owner's. Class B, C and E of the deviation register untouched;
Class E is the largest and turns on one question — what altitude this skill is
written for — which decides about eight items at once. `trellis-engine` holds 92
local-only commits, 2 stashes and 7 uncommitted skill files; out of scope today
and still the largest unpreserved body of work on this machine.

**Checks** — 11 findings, 4/4 ran, exit 1 (repo state partially blind: no remote
contacted). Acted on: this branch had 7 commits on no remote and `TODO.md` had
not named it — the forward-pass missed the session's own primary work and the
checks caught it. `WonderPrompt.txt` now carries its public address.

Dismissed with reason: the four remaining `inside baseball` findings are all in
`DEVIATIONS.md`, which *quotes* dead citations as the evidence for the defects it
records. Removing the quotes would destroy the register. `Lessons.txt` and
`AMBIENT.md` appear there as specimens, not as pointers this repo owes a reader.
Four sibling branches with no upstream predate this session and belong to other
worktrees.
