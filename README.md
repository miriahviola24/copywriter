# Centerfield UX Copy Skill

A structured UX microcopy reference and AI agent prompt for Centerfield's internal and customer-facing tools — including **Batting Cage** and the **CRM Agent**.

This skill was built by extracting and analyzing 250+ approved copy examples directly from Figma design sources, then codifying the patterns into reusable rules, review rubrics, and an AI-ready prompt.

---

## What's in this skill

| Section | Description |
|---|---|
| **Part 1 — Reference Dataset** | Copy patterns extracted from approved Figma sources, organized by message type |
| **Part 2 — Voice & Style Rules** | Inferred grammar, tone, and formatting rules, each classified by evidence level |
| **Part 3 — Copy Review Rubric** | Pass/Revise/Fail checklists for every copy type |
| **Part 4 — Agent Prompt** | Drop-in system prompt for Claude, ChatGPT, or any LLM |
| **Part 5 — Example Prompts & Outputs** | Worked examples showing the skill in action |
| **Part 6 — Decision Log Protocol** | How to log approved copy decisions so the skill learns over time |
| **Part 7 — Gaps** | Known copy types not yet covered, with suggested sources |

---

## Source files

All examples were extracted from the following Figma sources:

| File | Node | Label | Text Nodes |
|---|---|---|---|
| Batting Cage Design System 1.0 | 500:5331 | Modals Library | 105 |
| Batting Cage Design System 1.0 | 1020:582 | Message Library (ALIYA) | 71 |
| CRM | 1426:31987 | Agent Mocks (FINAL) | ~150 meaningful |
| Bulk Actions | 472:2239 | Cluster Mocks | 0 (visual only) |

**Total unique approved examples analyzed:** ~326 meaningful text nodes

---

## Copy types covered

- Confirmation modals (title, bold message, body copy, CTAs)
- Success toasts and banners
- Error messages
- Warning messages
- Instructional / compliance reminders (CRM)
- Contact matching messages
- Upload / file area copy
- Empty states
- CRM activity log entries
- Tooltip patterns (inferred — pending validation)

---

## Core voice principles

**Always:**
- Direct — state what is happening, not what might be happening
- Specific — use actual entity names, numbers, dates; never "this item"
- Consequential — in confirmations, explain what changes *before* asking for agreement
- Structured — use discrete list formatting for multi-step errors or instructions
- Complete sentences with proper punctuation — all body copy, toasts, warnings, and error messages end with a period; fragments are only acceptable for short labels, pill copy, and modal titles
- Entity names in single quotes: `'Cluster Name'`, `'Zone Name'`
- Sentence case for body copy and toasts; Title Case for modal titles and error headlines
- Passive voice for system-led success: *"has been saved successfully"*
- Active voice for agent-led activity logs: *"Agent Name called Contact Name"*

**Never:**
- No emoji
- No exclamation points
- No apology language: "Sorry", "Oops", "Unfortunately"
- No casual filler: "Hey", "Just", "Simply", "Basically"
- No generic entity references: never "the item", "the selected record", "this thing"

---

## Quick pattern reference

### Confirmation modal
```
Title:        Confirm [Gerund Verb] [Object]
Bold message: Are you sure you want to [action] the [entity type] '[name]'?
Body:         [Consequence] + severity signal
              — Reversible:   ends with "please proceed with caution"
              — Irreversible: starts with "CAUTION:"
              — Wide scope:   starts with "IMPORTANT:"
CTAs:         Cancel  |  Yes, [Verb] [Object]  (or "Confirm" for acknowledgements)
```

### Success toast
```
[Entity] '[name]' has been [action] successfully.
[N] [Entities] have been [action] successfully.
```

### Error message
```
Headline (title case): Unable to Save
Body: [Specific field/constraint/row that caused the error]
Multiple fixes: "Take any of the following actions to resolve: [list]"
```

### Warning
```
Factual statement of condition. No alarm.
Time-sensitive: include exact date/time/timezone — format: h:mmpm Timezone
```

### Empty states
```
Nothing here yet:  "No [Entity] yet" + "[Entity] you [create/add/receive] will appear here."
No results found:  "No results found" + "Try adjusting your filters or search..."
```

---

## Decision log

Approved copy decisions are logged to `ux-copy-decisions.json`. This allows the skill to learn from real production choices over time.

**To log a decision**, after approving a copy option, prompt Claude:
> "Log this as an approved decision in ux-copy-decisions.json"

Claude will append an entry with the date, copy type, use case, chosen copy, and pattern used. Once a pattern appears 3+ times in the log without deviation, it is elevated from ⚠️ *Inferred* to ✅ *Strongly supported*.

---

## How to use the AI agent prompt

The full system prompt is in **Part 4** of the skill spec. Copy it into:
- Claude's custom instructions or a Cowork skill
- A ChatGPT custom GPT system prompt
- Any LLM instruction block

When given a copy request, the agent returns:
1. **Recommended Copy** — the best option following approved patterns
2. **Why it fits** — the specific pattern or rule it follows
3. **Alternatives** — 1–2 variations with notes on when to use each
4. **Tone/alignment notes** — flags anything inferred vs. strongly supported

---

## Known gaps

The following copy types are not yet covered and should be added as examples become available:

- Tooltip copy (no examples extracted yet)
- Form field validation / inline field errors
- Loading states and progress messages
- Onboarding / first-run flows
- Primary page-level CTA copy outside of modals
- Accessibility / aria-label conventions

---

## Confidence levels

Each pattern in the skill is marked with one of two confidence levels:

- ✅ **Strongly supported** — backed by multiple direct Figma examples
- ⚠️ **Inferred** — extrapolated from analogous patterns; should be validated with real examples before treating as standard

---

## Related resources

- [Centerfield UX Copy Skill — Notion page](https://www.notion.so/336cb15b3901811d88f1f4dcdbfc4b15)
- Batting Cage Design System 1.0 (Figma)
- CRM Agent Mocks (Figma)
