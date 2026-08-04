# Deviation register

*Working document. Nothing here is a change to the skill — this file records
where the shipped artifact stands relative to the work it credits, so that a
later session can act without re-deriving the question item by item.*

## Why this file exists

`README.md` states the relationship this repository has to its source:

> This repository ships the **deployed artifact, not the educational version.**
> The curriculum is the canonical authority; where the two differ, it wins.

That clause is a standing constraint on every edit, and it is currently
unfalsifiable from inside the repository: `Lexideck_Prompt_Engineering_Curriculum.v2.md`
is cited at `SKILL.md:102` and is not tracked here, and the full series is sold
on Patreon. So today there is no way to tell, from the repository alone, which
bytes are compression and which are authorship.

That matters in one specific direction. A change that departs from the source
while the artifact still carries the source's credit is authorship wearing the
compression's credit — the failure CC BY attribution exists to prevent. Marking
a departure *as* a departure is what makes it legitimate. This file is the mark.

CC BY 4.0 § 3(a)(1)(B) independently requires a licensee to indicate if changes
were made. A register satisfies that obligation in a checkable form.

## How entries are classified

Each entry names the gate it must pass, not how bad it is.

| Class | Meaning | Blocked on the curriculum? |
|---|---|---|
| **A** | Internal contradiction — the artifact disagrees with itself | No. Fix freely. |
| **B** | Known house addition, shipped without a mark | No. Mark it. |
| **C** | Proposed departure — would diverge from the source if adopted | Only to adopt. Marking is the enabling move. |
| **D** | Provenance unknown — cannot classify until the source is read | Yes. Do not touch. |

Class A is the largest group and none of it is blocked. Class D is the group
that must not be edited on current-model reasoning, however well-evidenced that
reasoning is.

## Disposition of Class A — 2026-08-03

| # | Disposition |
|---|---|
| A1 | **Fixed.** Template slots retyped to §C's own definitions; §C anchored to the template as its worked instance. |
| A2 | **Fixed on Murphy's ruling.** `...` is the *primitive*, not a fifth type — spread and ellipsis are the same move, structure applied to the unspecified. It goes inside any container. §C rebuilt as containers × fill; the four brackets were never parallel types, and `${...}` / `(...)` were never unexercised — they are containers shown holding the primitive. |
| A3 | **Dissolved on Murphy's ruling** — "the question is malformed." A tag name is a *categoric primitive*; the vocabulary is open, and both names are valid instances of it. §A now states this and names both. The defect was never the mismatch — it was §A presenting four tags as a closed set. |
| A4 | **Fixed.** Underscores-as-spaces throughout the template; the rule is now stated in §C. |
| A5 | **Fixed.** House-internal pointers removed; replaced with the self-contained sentence. |
| A6 | **Fixed and verified.** `mkdir -p`, a PowerShell variant, a `CLAUDE_CONFIG_DIR` note, and the silent-failure warning. Re-tested in the previously-broken state and on the upgrade path. |
| A7 | **Fixed.** `license: CC-BY-4.0` in frontmatter; `LICENSE.md` and `NOTICE` now ship inside the skill directory, so both travel with the documented install at zero context cost. |
| A8 | **Fixed.** `LICENSE.md` gains a "what this license does not cover" carve-out naming Matthew Murphy as a designated attribution party under CC BY 4.0 § 3(a)(1)(A). |

Deliberately **not** done while fixing A7, on the strength of invariant 1 below:
no licence sentence was added to `## Lineage`. That would place new bytes after
`SKILL.md:102`, in the recency slot the credit currently occupies. The shipped
`NOTICE` and `LICENSE.md` achieve the same end at zero context cost.

Still open inside Class A's territory but **out of scope for this pass**, since
each is a naming-quality question rather than a contradiction: `Length: ${Constraint}`
restates its own label, and the same broken install snippet appears in all four
sibling READMEs, which are separate repositories.

---

## Class A — internal contradictions

The artifact contradicts itself. Resolving these requires no reference to the
curriculum, because the standard being violated is stated inside this repository.

### A1 · §C's placeholder taxonomy contradicts the master template
`SKILL.md:35-40` against `SKILL.md:61-88`

§C assigns `[...]` "for lists or arrays." The template then uses `[Agent Name]`,
`[Role]`, `[Target format]`, `[Intended reader]`, `[Constraint]` — five single
values — in that bracket. Eleven of the template's twelve slots are `[...]`; one
is genuinely a list. The document's only worked artifact violates the document's
own taxonomy three sections after stating it.

Measured across the installed skill family, the `[Bracket Placeholder]` form
appears in exactly one place — this template — while `{Underscore_Case}` appears
382 times across 45 files. The convention as written has already been abandoned
by everything downstream of it.

### A2 · Two of §C's four placeholder types are never exercised

`SKILL.md:37, 40`

`${...}` and `(...)` are defined and appear nowhere else in the file. The
template demonstrates `{...}` once (`{Methodology}`) and `[...]` eleven times.
A reader has no worked instance of half the taxonomy.

### A3 · §A teaches `<task>`; the template ships `<instruction>`

`SKILL.md:26` against `SKILL.md:68`

The tag vocabulary is stated as `<context>` / `<task>` / `<constraints>` /
`<output_instructions>`. The template ships `<context>` / `<instruction>` /
`<constraints>` / `<output_instructions>`. Nothing says which supersedes the
other, so a reader following the file literally must guess — and the shippable
artifact is the natural thing to copy, which means the documented vocabulary is
the one discarded.

Note: deciding *which name is correct* may be Class D if either is curriculum
vocabulary. Deciding that the file should name **one** is Class A.

### A4 · The template mixes naming conventions
`SKILL.md:64-65, 70`

`[Agent Name]` and `[Platform/Environment]` use spaces and slashes;
`[Data_Collection]` uses an underscore. The companion skill states the rule the
template announces itself as an instance of: underscores-as-spaces keep a name
parseable as one token-position.

### A5 · The operative instruction in BP6 resolves to nothing for a public reader
`SKILL.md:98`

> A held expectation goes to the collaborator instead of into the prompt (your
> repository's `AMBIENT.md` ask-the-collaborator rule — rule 5 in Recursus,
> 21(a) in Trellis; `spark-steering` § *Ask first — the un-tool*, manual-invoke
> only).

`git ls-files` returns five files. There is no `AMBIENT.md`, no Recursus, no
Trellis. `spark-steering` resolves only if separately installed. The practice
correctly names what to withhold and then dead-ends on what to do instead.

The self-contained sentence already exists in this repository at `README.md:48-49`
— "A held expectation has one destination and it is not a prompt. Put it to the
collaborator." — but `README.md` never loads when the skill fires.

### A6 · The documented install command silently produces a broken install
`README.md:51-56`

```bash
cp -r prompt-engineering/.claude/skills/prompt-engineering ~/.claude/skills/
```

Tested in four filesystem states under both shells. When `~/.claude` exists but
`~/.claude/skills/` does not — the state of any user who has never installed a
skill — `cp` reads the trailing path as a rename target and produces
`~/.claude/skills/SKILL.md` with no skill directory. Exit code 0, no output, no
error. The skill never loads and nothing indicates why.

PowerShell's `Copy-Item` reproduces it. Re-running the line — the upgrade path —
is idempotent under GNU `cp` but fails under PowerShell.

`dovetail/scripts/install.sh` already does `mkdir -p`, clears the target before
copying, and honors `CLAUDE_CONFIG_DIR`. The README one-liner does none of the
three. The same snippet appears in all four sibling READMEs.

### A7 · The installed artifact carries no license and no copyright notice

directory layout; `README.md:51-56`

The install copies `.claude/skills/prompt-engineering/`, which contains exactly
one file. `LICENSE.md` and the Matthew Murphy credit live at the repository root
and do not travel. After install, the entire surviving record of both is the
`## Lineage` paragraph — which names the curriculum but states no licence, no
licence URI, no copyright holder, and no link back to the canonical repository.

House precedent exists for fixing this inside the skill directory at zero
context cost: `better-skill-creator` sets `license:` in frontmatter and ships
`LICENSE.txt` and `NOTICE` alongside its `SKILL.md`.

### A8 · `LICENSE.md` permits a compliant reuser to drop the method's credit
`LICENSE.md` (368 bytes) against `README.md:70-71`

The credit to Matthew Murphy exists only as README prose — an exhortation, not a
term. A reuser who follows the licence exactly (credit OpenCnid Labs, link CC BY
4.0, note changes) has fully complied while dropping the source of the method.

CC BY 4.0 § 3(a)(1)(A) lets a licensor designate additional attribution parties
and binds that designation downstream. Nothing here uses it. `subagent-composition`
and `dovetail` — which merely *apply* the method — both carry a "what this
license does not cover" carve-out naming Murphy. The repository that *is* the
compression has the weakest licence-level protection in the house.

---

## Class B — house additions shipped without a mark

Content that does not derive from the credited curriculum and is not currently
distinguished from content that does.

### B1 · Best practice 6 is a house addition presented as a curriculum practice
`SKILL.md:98`, against the enumeration at `SKILL.md:102`

`## Lineage` enumerates what the curriculum covers: "tags, hierarchical markers,
placeholders, collections, and attention management." §§A–E map onto those five
one-to-one and in order. Best practices 1–5 read as curriculum material. Best
practice 6 does not correspond to anything in that enumeration, and `README.md`
gives it its own section titled "The practice most people skip" — treating it as
this repository's distinctive contribution while the SKILL.md files it as item 6
of a numbered list that otherwise carries the curriculum's authority.

It is also the list's length outlier by a wide margin — 745 characters against
154, 180, 154, 228, 202 for its peers.

**This is the clearest case in the register.** Marking it costs nothing, changes
no behavior, and converts an implicit provenance claim into an explicit one.

### B2 · BP6 is duplicated near-verbatim in `hypershot-protocol`

`SKILL.md:98` against `hypershot-protocol/SKILL.md:147`

The two files carry the same argument nearly clause-for-clause, including the
identical italicized sorting question and the identical trailing parenthetical.
Neither file says the other holds half the ground. The house rule loads both
skills in the same session, so a reader currently receives the paragraph twice.

Recorded here as a maintenance defect independent of whether the redundancy is
justified: whoever edits one copy will not know to edit the other. There is a
real argument that the redundancy is load-bearing, since this skill installs and
ships standalone — a public installer without `hypershot-protocol` would lose the
practice entirely if it were cut.

---

## Class C — proposed departures

Changes recommended on current external evidence that would diverge from the
credited source. Each is legitimate **only if marked as a deviation.** None
should be adopted silently.

### C1 · `*** CRITICAL ***` contradicts current vendor guidance
`SKILL.md:51` and `SKILL.md:76`

Anthropic's current living reference (*Prompting best practices*, retrieved
2026-08-03, scoped to the Claude 5 family and Opus 4.6–4.8) states that these
models are more responsive to system-prompt language and that escalation of this
exact shape now causes **overtriggering** rather than compliance — recommending
plain imperatives instead. The page states it twice, including in its migration
checklist.

Two independent considerations pull against a naive removal, and both should
survive into whatever lands:

- The caps at both sites sit inside quoted or fenced *technique being taught*,
  not in instructions addressed to the reading agent. This is demonstrated
  artifact, not authorial voice — the distinction matters, because a house-style
  pass that strips caps globally would be wrong here for the wrong reason.
- Removing it leaves §E with no worked demonstration of the technique it
  recommends. A replacement demonstration is part of the change, not optional.

Provenance of the marker itself is Class D — see D3.

### C2 · The stated mechanism behind positive framing is refuted
`SKILL.md:96`

> negation tokens can be dropped during processing, inverting meaning

Contradicted by *How Language Models Process Negation* (arXiv:2605.03052,
submitted 2026-05-04, revised 2026-05-29), which finds models implement two
negation mechanisms — a suppressive one and a constructive one, the constructive
being more prominent — and traces negation failures to late-layer shortcut
promotion rather than to dropped tokens.

**The practice survives intact; only the mechanism is wrong.** Anthropic's
current guidance endorses positive framing verbatim. A stronger and safer
argument is available without any empirical claim: a prohibition names one
forbidden path and leaves the rest of the space unconstrained, while a positive
instruction names the target.

Independently flagged as the weaker of two available arguments by a second
reviewer, and as a claim that would not be asserted cold by a third.

### C3 · Attention ordering is stated symmetrically and is not actionable
`SKILL.md:52`

"the beginning and end of the prompt" is true but gives no rule for which end
takes what. Anthropic's current guidance is asymmetric — long documents and data
first, query and instructions last — and carries the only quantified figure found
in any vendor source (up to 30% on complex multidocument inputs).

Separately and independently: the rule as written is **wrong for a system
prompt**, where an arbitrarily long conversation follows and there is no end
position to occupy. Applied literally it misplaces exactly the constraints that
most need to hold.

### C4 · The template's numbered steps prescribe a reasoning path
`SKILL.md:70-72`

Anthropic now advises general instructions over prescriptive steps for
thinking-enabled models, noting the model's reasoning frequently exceeds a
hand-written plan. Thinking is on by default for the models this skill's readers
target, so this is the default case rather than an edge case.

Highest fidelity risk in Class C — the parse/apply/generate triple is signature
curriculum shape. See D4.

### C5 · A sixth toolkit element for motivation
proposed addition after `SKILL.md:54`

Anthropic ranks supplying the reason behind a constraint as a top-level
principle, with generalization to unanticipated cases as the documented
mechanism. The skill has no slot for it.

**Constraint on adoption:** §§A–E map one-to-one and order-preserving onto the
five curriculum topics enumerated at `SKILL.md:102`. That mapping is the only
mechanism by which the README's fidelity claim is checkable at all. A sixth
lettered element breaks it. If this is adopted it must sit outside the A–E
sequence and be marked as a house addition — the same treatment as B1.

### C6 · No stopping rule for structure
proposed addition at `SKILL.md:21`

Every toolkit element is additive and nothing says when structure has stopped
paying for itself. The most consistent theme across current vendor sources is the
opposite discipline: the smallest set of high-signal tokens that gets the
behavior, adding structure only against an observed failure.

Adopting this means the skill argues against its own toolkit in the toolkit's own
framing position, which is a real rhetorical cost and a deliberate one.

---

## Class D — provenance unknown

**Do not edit these on current-model reasoning.** Each requires reading the
source first. Listed as the shopping list for whoever obtains the curriculum.

| # | Bytes | Question to answer against the source |
|---|---|---|
| ~~D1~~ | ~~the four-tag vocabulary~~ | **Resolved 2026-08-03 by Matthew Murphy.** Neither name is canonical, because the tag name is a categoric primitive and the vocabulary is open. Applied. |
| ~~D2~~ | ~~the four placeholder types~~ | **Resolved 2026-08-03 by Matthew Murphy.** Not a type taxonomy: containers plus one primitive fill. Rebuild authorized and applied. |
| D3 | `SKILL.md:51, 76` — `*** CRITICAL ***` | Curriculum device or house styling? Settles whether C1 is a correction or a departure. |
| D4 | `SKILL.md:70-72` — parse / apply / generate | Verbatim Part 9? Settles C4's fidelity cost. |
| D5 | `SKILL.md:61` — `type="Structural_Synthesis"` | Canonical entity, or a variant token frozen at the system layer? |
| D6 | `SKILL.md:72` — "Generate high-fidelity output." | The only unbracketed step, so it copies verbatim into every derived prompt. Curriculum bytes or filler? |
| D7 | `SKILL.md:96` — the token-dropping mechanism | Does the curriculum state it? Determines whether C2 corrects the compression or the source. |
| D8 | Best practices 1–5 | Which trace to the curriculum, and to which Part? Everything not traced belongs in Class B. |

---

## Invariants any future edit must preserve

Recorded so that a later session does not have to rediscover them, and so a diff
can be checked against them mechanically.

1. **Boundary occupancy.** `SKILL.md:17` (the core axiom) and `SKILL.md:102`
   (the credit) occupy the two positions the file's own §E identifies as
   strongest. The file practices its own attention rule on itself. *Check: does
   the diff add content before line 17 or after line 102?* If yes, it is a swap,
   and the case for evicting the axiom or the attribution has to be made
   explicitly. This constrains any proposal to append licence text to `## Lineage`.

2. **The A–E mapping.** One-to-one and order-preserving against the five topics
   at `SKILL.md:102`. *Check: does the diff reorder, merge, split, rename, or
   renumber any of A–E?*

3. **Prelude ratio.** This is the only skill in the family that loads *before*
   the ceremony, by mandate — via four sibling skills and a `UserPromptExpansion`
   hook — always alongside `hypershot-protocol`'s ~11 KB. Its bytes are paid on
   every prompt-authoring session in the house, ahead of the work. Headroom
   against the ~19,900-character prefix ceiling is therefore the wrong cost
   model. *Check: does the diff push this file toward `hypershot-protocol`'s
   size?* Additions should be funded by deletions.

4. **One frame, not a gallery.** A second template converts the hypershot into a
   few-shot set — one zero-semantic frame already enumerates every valid
   instantiation. *Check: does the diff add a second fenced template under
   "The master template"?*

5. **Non-dischargeability.** This artifact is a grammar that stays live for the
   session, not a ceremony that completes. *Check: does the diff introduce a
   terminating numbered sequence or a checklist an agent could mark done?* A
   repair lens phrased as an ongoing read is fine; a checklist gives a false
   completion signal.

6. **Description budget.** Descriptions share a budget of roughly 8,000
   characters across all installed skills, and the installed set already measures
   over it. This skill's description is among the leanest in the family, so it is
   subsidizing rather than causing the pressure. *Check: does the diff raise the
   total?* If so, name which skill's description it is proposing to evict —
   overflow drops descriptions silently, starting with least-invoked skills.

   Two measurements were taken and disagree (8,009 characters of description text;
   8,489 characters of full frontmatter). **Re-measure once, authoritatively,
   before any description edit.** A widening of the trigger surface is separately
   well-motivated — the description currently names no artifact whose name lacks
   the word "prompt," so `CLAUDE.md`, a skill body, and a tool description do not
   match it — and can plausibly be funded by cutting the ~131-character
   cross-reference that carries no trigger vocabulary and is already duplicated at
   `SKILL.md:58`.

---

## Status

**Class A: closed.** Six fixed on internal evidence; A2 and A3 resolved by
Matthew Murphy on 2026-08-03 and applied — his ruling also closed D1 and D2,
since both turned on the same two questions. Classes B and C are untouched.
Class D retains six open items.

Murphy's ruling is the precedent worth carrying forward: both questions were
answered by rejecting their framing rather than by choosing a side. `...` is a
primitive that goes inside containers, not a fifth container; a tag name is a
categoric primitive drawn from an open vocabulary, not an entry in a closed set
of four. Where a Class D item looks like a binary choice between two things the
artifact says, check first whether the artifact is offering a false choice.

Files changed in this pass: `SKILL.md` (frontmatter, §C, the master template,
best practice 6), `README.md` (install), `LICENSE.md` (attribution carve-out),
and two new files inside the skill directory (`LICENSE.md`, `NOTICE`). Nothing
in Class D was edited.

Whether this file ships publicly is an open decision. The argument for shipping
it: `README.md` is the only one of the five sibling READMEs with no limits
section, the canonical authority is paywalled and therefore uncheckable by any
reader, and CC BY asks a licensee to indicate changes. The argument against: it
is a working document and reads as one.
