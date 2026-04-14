# Centerfield UX Copy Skill Spec
**Source:** Batting Cage Design System 1.0 (Modals Library + Message Library), CRM Agent Mocks
**Extracted:** 250+ approved copy examples across 4 Figma files
**Purpose:** Reusable skill for generating, reviewing, and improving UI microcopy in Centerfield's internal and customer-facing tools

---

## Part 1: Structured Reference Dataset

All examples are drawn directly from approved Figma sources. Confidence is noted per section.

---

### 1.1 Confirmation Modal Copy
**Source:** Batting Cage Design System — Modals Library (node 500-5331)
**Confidence:** ✅ Strongly supported by examples

#### Anatomy
Every confirmation modal has three layers:
- **Title** (20px bold) — names the action
- **Bold message** (16px bold) — asks the question with specific entity names
- **Body copy** (14px regular) — explains consequences + caution signal
- **Two CTAs** — Cancel (text link) + Confirm (filled button)

#### Title Patterns
| Pattern | Examples |
|---|---|
| `Confirm [Verb]ing [Object]` | Confirm Deleting Zone, Confirm Deactivating Existing Zone, Confirm Archiving Cluster, Confirm Pausing Experiment, Confirm Resuming Experiment |
| `Confirm [Verb]ing [Adjective] [Object]` | Confirm Changing Rules of Active Cluster, Confirm Changing Rules of Inactive Cluster, Confirm Deleting Linked Zones, Confirm Deleting Selected Cluster(s) |
| `Confirm [Noun Phrase]` | Confirm Clearing Group Rules, Confirm Clearing All Rules, Confirm Proceeding Without Rules, Confirm Updating Experiment Control |
| `[Verb] [Object] [Sub-entity]` | Edit Experiment Variation, Edit Experiment Variations |
| `[Noun Phrase]` (descriptive, not verb-led) | Overlapping Experiment Rules, Cancel Experiment Scheduling |

**Rule (strongly supported):** Titles use title case. The most common pattern is `Confirm [Gerund Verb] [Object]`. Non-confirm titles (Edit, Cancel, Overlapping…) are situational exceptions, not the norm.

#### Bold Message (Sub-headline) Patterns
| Pattern | Example |
|---|---|
| `Are you sure you want to [action] the [object type] '[name]'?` | "Are you sure you want to delete the Homepage Zone 'Compare NRL Header'?" |
| `Are you sure you want to [action] the '[brand]' [object type] '[name]'?` | "Are you sure you want to deactivate the ADT.com Zone 'P1 Flag'?" |
| `Are you sure you want to [action] the linked [object] '[name]'?` | "Are you sure you want to delete the linked Zone 'Bullet 1'?" |
| `Are you sure you want to [action] [plural objects]?` | "Are you sure you want to permanently delete the selected Cluster(s)?" |
| Informational (no question) | "These Rules are already tied to an Active Cluster. The Cluster 'Atlanta Newer' will now be the control for the Experiment." |

**Rule (strongly supported):** Named entities are always in single quotes. The bold message is always specific — it names the actual entity being affected, never generic.

#### Body Copy Consequence Patterns
| Severity | Pattern | Example |
|---|---|---|
| Standard / Reversible | Explains impact + "please proceed with caution" | "Any changes could have repercussions to other Batting Cage functionality, so please proceed with caution" |
| Standard / Reversible | Names when it takes effect | "This will go into effect immediately so please proceed with caution." |
| Moderate / Reversible | Notes what is preserved or how to undo | "This will go into effect immediately and will cause the Cluster to no longer be visible to end-users. You will be able to reactivate the Cluster as needed without having to preview to publish." |
| Severe / Irreversible | Leads with CAUTION: | "CAUTION: Archiving a cluster permanently deactivates a Cluster so that it can no longer be viewed by end-users. This is irreversible." |
| Critical / Setup | Leads with IMPORTANT: | "IMPORTANT: If Rules are not defined, this Experiment will apply to ALL traffic for 'ADT Security'." |
| Advisory | Recommended Action: prefix + asterisk footnote | "Recommended Action: Visit the 'Atlanta Newer' Cluster page…\n*Once an Experiment is Active the Control Cluster can not be edited…" |

**Rule (strongly supported):** Body copy always explains *what will happen* before asking the user to proceed. "please proceed with caution" is the standard close for reversible-but-impactful actions. CAUTION: and IMPORTANT: are reserved for irreversible or high-scope consequences.

#### CTA Patterns
| Cancel button | Confirm button |
|---|---|
| Always: "Cancel" | "Yes, [Verb] [Object]" — when action is specific and reversible-ish |
| | "Yes, [Verb]" — when object is clear from context |
| | "Confirm" — when action is informational, acknowledgement-only, or multi-step setup |

**Examples of "Yes, [Action]" CTAs:**
Yes, Save Changes / Yes, Delete Zone / Yes, Deactivate Zone / Yes, Delete Zone / Yes, Save & Update Rules / Yes, Deactivate Cluster / Yes, Activate Cluster / Yes, Archive Cluster / Yes, Clear Rules / Yes, End Variation / Yes, End Variations / Yes, Continue Without Rules / Yes, Delete

**Rule (strongly supported):** "Cancel" is always the exact word for the dismiss CTA — no variations. The confirm CTA mirrors the title's verb. Use "Confirm" when the action is more of an acknowledgement than a destructive step.

---

### 1.2 Success Messages (Toast/Banner)
**Source:** Batting Cage Design System — Message Library (node 1020-582)
**Confidence:** ✅ Strongly supported by examples

#### Standard Success Toast
| Pattern | Examples |
|---|---|
| `[Entity] '[name]' has been [action] successfully.` | "Cluster 'Atlanta Newer' has been activated successfully." / "Cluster 'Home Monitoring' has been archived successfully." |
| `[Entity] '[name]' has been [action] successfully. [Follow-up note].` | "Cluster 'Atlanta Newer' has been deactivated successfully. It can be reactivated as needed." |
| `[Entity] '[name]' Rules have been changed successfully.` | "Cluster 'Atlanta Newer' Rules have been changed successfully." |
| `[N] [Entity] has/have been [action] successfully.` | "1 Cluster has been Saved as Draft successfully." / "10 Clusters have been Saved as Draft successfully." |
| `[N] [Entity] has/have been [action] successfully.` | "1 Cluster has been deleted successfully." / "4 Clusters have been deleted successfully." |
| `[Priority/Feature] has been saved successfully` | "Zone Priority has been saved successfully" / "Cluster Priority has been saved successfully" |
| Experiment update | "Experiment 'Location Test' has been updated successfully." |
| Revert to status | "Experiment 'D/T/M - Best Price' has successfully reverted to 'Draft' status." |
| Linked zone updates (multi-page) | "'Bullet 1' has been updated successfully on the Page 'Step 1'." |
| Multi-page variant | "'Bullet 1' has been updated successfully on 2 Pages: 'Step 1', 'Step 2'." |
| Bulk import | "The Bulk Action has been imported successfully. Review each Cluster to either \"Save as Draft\" or \"Delete\" as needed." |

#### Winner Declared (Two-line success)
```
Winner Successfully Declared
No new Clusters were created, 100% of the target segment traffic will see the control experience.

Winner Successfully Declared
The Cluster 'Atlanta Newer' has been created and 100% of the target segment traffic will see this experience.

Winner Successfully Declared
No new Clusters were created, the Variation A experience replaced the 'Ravi Demo' Cluster experience.
```
**Pattern:** Bold headline + explanatory subline. Subline explains the traffic outcome in plain terms.

#### CRM Activity Log (inline success events)
| Pattern | Examples |
|---|---|
| `[Agent] Called [Contact] ([duration])` | "Agent Name Called Contact Name (3:00)" |
| `Missed Call from [Contact] to [Agent] ([duration])` | "Missed Call from Contact Name to Agent Name (2:09)" |
| `[Agent] created an Appointment for [Contact]` | "Agent Name created an Appointment for Contact Name" |
| `[Agent] rescheduled an Appointment for [Contact]` | "Agent Name rescheduled an Appointment for Contact Name" |
| `[Agent] marked an Appointment as done for [Contact]` | "Agent Name marked an Appointment as done for Contact Name" |
| `[Agent] started collaborating with [Agent]` | "Agent Name started collaborating with Agent Name" |
| `The Contact [Name] was created` | "The Contact Contact Name was created" |
| `The Opportunity [Name] was created` | "The Opportunity Opportunity Name was created" |
| `[Agent] was assigned the Opportunity [Name].` | "Agent Name was assigned the Opportunity Opportunity Name." |

**Rule (strongly supported):** Success messages use passive voice when the *system* is confirming the action ("has been activated"). They use active voice for activity log entries where a *person* performed the action ("Agent Name Called…"). Always sentence case. Entity names in single quotes for Batting Cage; no quotes in CRM activity log.

---

### 1.3 Warning Messages
**Source:** Batting Cage Design System — Message Library (node 1020-582)
**Confidence:** ✅ Strongly supported by examples

| Trigger | Pattern | Example |
|---|---|---|
| No data for date range | Statement of condition | "No Data is available on this Experiment for the Date Range 7/12/23 - 10/9/23" |
| Lapsed date | States what happened + next action | "The Start Date previously defined has lapsed; Set a new Start Date then proceed to the Summary to review and approve the Experiment." |
| Missing content | Direct statement | "No Content Variations have been defined." |
| No data on specific variants | Names each variant | "No data available on the Control (CellPhonePlan.com) and Variation B (Best Content) for the selected Date Range." |
| No rules defined | Statement + scope consequence | "No Rules Defined. Cluster Experience applies to ALL traffic for T-Mobile.com." |
| Experiment not live yet | States reason for no data | "This Experiment has not gone live yet and therefore no data has been collected." |
| Overlapping rules | States condition + options | "A Start Date cannot be defined because the specified Rules overlap with an existing Experiment. Once the conflicting Experiment ends a Start Date can be selected." |
| Pending expiry | `Warning\n[Action needed by date]` | "Warning\nPending Clusters will be automatically deleted if no action is taken by 11/17/23 at 4:15pm Pacific." |
| Expired bulk action | Two-part: title + explanation | **Title:** "Bulk Action Expired" / **Body:** "The time to complete this Bulk Action expired on 12/10/23 at 4:15pm Pacific. All Pending Clusters from this import have been permanently deleted." |

**Rule (strongly supported):** Warning messages are factual, not apologetic. Date/time format used: M/D/YY for date ranges, MM/DD/YY for full dates, time in h:mmpm Timezone. No "Sorry" or "Unfortunately."

---

### 1.4 Error Messages
**Source:** Batting Cage Design System — Message Library (node 1020-582)
**Confidence:** ✅ Strongly supported by examples

#### Structure: Headline + Body
All errors follow a two-part structure: a short headline naming the problem category, followed by a specific explanation.

| Category | Headline | Body Example |
|---|---|---|
| Save validation | `Unable to Save` | "Control Split cannot be set to 0%." |
| Save validation | `Unable to Save` | "Variation Traffic Splits must total 100% exactly. Currently, the entered split percentages add up to 110%." |
| Save validation | `Unable to Save` | "Note is required" |
| Save validation | `Unable to Save` | "Experiment must have at least two variations" |
| Save validation | `Unable to Save` | "Field Error(s) must be fixed before save." |
| Nested rule error | `Unable to Save` | "Cannot have a nested Rule Group with only one Rule. Take any of the following actions to resolve.\nMove the impacted Rule to the top level.\nAdd a second Rule to the nested Rule Group.\nDelete the impacted nested Rule Group." |
| Content/trigger mismatch | `Unable to Save` | "All Experiment variations must either have content for at least one Zone defined or a valid Trigger." |
| Approval required | (no headline) | "The Experiment's content has been modified but has not been approved. Approve Preview in order to resume this Experiment." |
| Results not ready | (no headline) | "Results are not yet significant." |
| File format error | `Unable to Import File` | "Invalid file format. Only XLS, XLSX and ZIP files supported." |
| Row-level import error (1) | `Unable to import 1 Cluster` | "Row 6\nDetails & Targeting - invalid 'City'" |
| Row-level import error (multiple) | `Unable to import [N] Clusters` | "Row 6\nDetails & Targeting - invalid 'City'\nRow 13\nExperience - 'Internet: Pre-header' character limit exceeded\nRow 15\nCluster Name must be unique within the Domain" |
| Bulk action failure | `Bulk Action Failed` | "Invalid column header 'Blah'" |
| Bulk action complete failure | `Bulk Action Failed` | "No Clusters could be imported.\n\n[Row-by-row error list]" |

**Rules (strongly supported):**
- Error headlines use title case and are short (2–4 words)
- Body copy is always specific: it names the field, percentage, row number, or constraint violated
- When there are multiple fixes, they are listed as discrete numbered or bulleted options introduced by "Take any of the following actions to resolve."
- No "Oops," "Sorry," or apology language

---

### 1.5 Instructional / Reminder Copy (CRM)
**Source:** CRM Agent Mocks (node 1426-31987)
**Confidence:** ✅ Strongly supported by examples

| Type | Pattern | Examples |
|---|---|---|
| Compliance reminder | Direct imperative | "Inform customer that the call is recorded during the call introduction." |
| Compliance reminder | Conditional instruction | "TPMO, HIPAA and SOA must be read on outbound and inbound calls that do not occur the same day as the initial sales call." |
| Prohibited action | Direct prohibition | "Do not call back if customer did not agree to TCPA on initial call." |
| Navigation instruction | `For [context], click [element]` | "For inbound enrollments, click Inbound Enrollment Script (shortcut)" |
| Catch-all instruction | "All other [cases], please [action]." | "All other inbound calls, please click the appropriate script." |
| Contact matching — none | State result + offer action | "No Matching Contact Found. / If needed, select Select Contact to choose an existing one." |
| Contact matching — one | State result + offer override | "One Matching Contact Found. / If needed, select Select Different Contact to choose a different one." |
| Contact matching — multiple | State result + required action | "Multiple Matching Contacts Found. / Select the correct contact to continue." |
| Inline warning | Title + resolution | "Zip codes don't match. / Update the zip above, or continue to use the new zip for this script." |
| Inline success | Brief confirmation | "Existing Contact selected successfully." / "New contact started successfully." |
| Script guidance (pill label) | Short imperative | "Read in the first 60 seconds" |
| Status pill | State / required action | "Action Required" |

**Rule (strongly supported):** Instructional copy in the CRM is imperative and compliance-aware. It does not soften directives. Navigation hints use "click [element name]" literally matching the button label. Contact-matching messages follow a strict 2-line pattern: status + next-step instruction.

---

### 1.6 Upload / File Area Copy (CRM)
**Source:** CRM Agent Mocks (node 1426-31987)
**Confidence:** ✅ Supported by examples

| Element | Copy |
|---|---|
| Drop zone headline | "Drag & Drop" |
| Drop zone subline | "Drag & drop files here or browse to upload" |
| File meta | "Added By: [Agent Name]" |

---

## Part 2: Inferred Voice & Style Rules

All rules are classified by evidence level.

---

### 2.1 Voice Attributes

**✅ Strongly supported**

| Attribute | What it means | Evidence |
|---|---|---|
| **Direct** | Copy states what is happening or will happen without hedging | "This is irreversible." / "This will go into effect immediately." |
| **Consequential** | Every confirmation explains *what changes* before asking for agreement | All 20+ modal body texts include consequence statements |
| **Specific** | Uses actual entity names, percentages, dates, row numbers — never "this item" | 'Atlanta Newer', '110%', 'Row 6', '11/17/23 at 4:15pm Pacific' |
| **Structured** | Multi-step errors are formatted as discrete steps, not run-on sentences | "Take any of the following actions to resolve: [list]" |
| **Neutral on success** | Success toasts are confirmatory, not celebratory | "has been activated successfully" not "Great! Your Cluster is live 🎉" |
| **Formal-professional** | No casual filler, no emojis, no slang | Across all 250+ examples |

**⚠️ Inferred (supported but not definitive)**

| Attribute | Inference | Basis |
|---|---|---|
| **Cautious with destructive actions** | "please proceed with caution" appears to be the standard signal for reversible-but-impactful actions | 8+ modal examples use this phrase verbatim |
| **Compliance-aware in agent tools** | CRM copy assumes agents need explicit legal/procedural reminders embedded in the UI | Reminder section in CRM has TPMO, HIPAA, TCPA, SOA references |
| **System-led tone** | The product speaks on behalf of itself ("has been saved", "was created") rather than congratulating the user | Consistent passive voice in success toasts |

---

### 2.2 Grammar & Formatting Rules

**✅ Strongly supported**

| Rule | Detail |
|---|---|
| **Single quotes for entity names** | Always single quotes, not double: 'Atlanta Newer', 'Compare NRL Header' |
| **Title case for modal titles** | "Confirm Deleting Zone" not "Confirm deleting zone" |
| **Sentence case for body copy** | All body text, toasts, warnings use sentence case |
| **Error headline uses title case** | "Unable to Save", "Bulk Action Failed", "Unable to Import File" |
| **Dates:** M/D/YY for ranges, MM/DD/YY for specific | "7/12/23 - 10/9/23" / "12/10/23 at 4:15pm Pacific" |
| **Time format:** h:mmpm Timezone | "4:15pm Pacific" |
| **Singular/plural handled explicitly** | "1 Cluster has been..." vs "4 Clusters have been..." |
| **No Oxford comma exceptions** | Lists use Oxford comma: "Step 3', 'Form', 'Geo (Homepage)'" |
| **"Cancel" is always Cancel** | Dismiss CTA is never "No", "Never mind", "Go back" |
| **Confirm CTA mirrors the verb** | "Yes, Delete Zone" mirrors "Confirm Deleting Zone" |
| **Complete sentences with proper punctuation** | All body copy, toasts, warnings, and error messages are complete sentences ending with a period. Fragments are only acceptable for short labels, pill copy, and modal titles. |

**⚠️ Inferred**

| Rule | Inference |
|---|---|
| **No exclamation points** | Zero instances across all examples — appears intentional for internal tooling |
| **No emoji** | None used in any approved copy |
| **Passive voice for system actions** | "has been saved" (system did it) vs "You saved" — system-led construction consistent throughout |

---

### 2.3 Tone by Message Type

| Message Type | Tone | Signal Words |
|---|---|---|
| Confirmation modal | Cautious, informative | "Are you sure", "please proceed with caution", "This is irreversible" |
| Success toast | Neutral-positive, factual | "has been [action] successfully" |
| Warning | Matter-of-fact, no alarm | "No Data is available", "Warning\n[detail]" |
| Error | Direct, solution-oriented | "Unable to Save\n[reason + fix steps]" |
| Instructional (CRM) | Imperative, compliance-minded | "Inform customer…", "Do not call back if…" |
| Inline status | Terse, state-driven | "Action Required", "Read in the first 60 seconds" |
| Activity log | Active voice, agent-led | "[Agent] Called [Contact]", "Appointment marked as done" |

---

### 2.4 CAUTION vs IMPORTANT vs Warning

**✅ Strongly supported**

| Signal | When to use | Example |
|---|---|---|
| **CAUTION:** (in modal body) | Irreversible, permanent action affecting end-users | "CAUTION: Archiving a cluster permanently deactivates a Cluster… This is irreversible." |
| **IMPORTANT:** (in modal body) | Wide-scope consequence (all traffic, all users) or cannot be undone during setup | "IMPORTANT: If Rules are not defined, this Experiment will apply to ALL traffic for 'ADT Security'." |
| **Warning** (toast/banner headline) | Time-sensitive system event; pending expiry or deletion | "Warning\nPending Clusters will be automatically deleted if no action is taken by 11/17/23 at 4:15pm Pacific." |

---

## Part 3: Copy Review Rubric

Use this rubric to evaluate any new or existing microcopy against approved patterns.

---

### Scoring Guide
- ✅ Pass — meets the pattern
- ⚠️ Revise — partially meets but has a specific issue
- ❌ Fail — does not meet the pattern

---

### Rubric: Confirmation Modals

| Criterion | Check |
|---|---|
| Title follows `Confirm [Gerund] [Object]` pattern or a documented exception | ✅ / ❌ |
| Title is title case | ✅ / ❌ |
| Bold message names the specific entity in single quotes | ✅ / ❌ |
| Bold message asks "Are you sure you want to [action]…?" (or is informational when appropriate) | ✅ / ❌ |
| Body copy explains the consequence before asking to proceed | ✅ / ❌ |
| Body copy includes appropriate severity signal (none / "proceed with caution" / CAUTION: / IMPORTANT:) | ✅ / ❌ |
| Cancel CTA is exactly "Cancel" | ✅ / ❌ |
| Confirm CTA mirrors the verb from the title ("Yes, [Verb] [Object]" or "Confirm") | ✅ / ❌ |
| No apology, exclamation, or emoji | ✅ / ❌ |

---

### Rubric: Success Messages

| Criterion | Check |
|---|---|
| Follows `[Entity] '[name]' has been [action] successfully.` pattern | ✅ / ❌ |
| Singular/plural handled correctly ("1 Cluster has" vs "4 Clusters have") | ✅ / ❌ |
| Entity name in single quotes | ✅ / ❌ |
| Sentence case (not title case) | ✅ / ❌ |
| No celebratory language ("Great!", "Woohoo!", etc.) | ✅ / ❌ |
| If two-line: headline bold, subline explains traffic/scope outcome | ✅ / ❌ |

---

### Rubric: Error Messages

| Criterion | Check |
|---|---|
| Has a short title case headline ("Unable to Save", "Bulk Action Failed", etc.) | ✅ / ❌ |
| Body names the specific field, constraint, row, or value that caused the error | ✅ / ❌ |
| If multiple fixes exist, structured as discrete list with "Take any of the following actions to resolve." | ✅ / ❌ |
| No apology ("Sorry", "Oops", "Unfortunately") | ✅ / ❌ |
| No blame ("You entered the wrong…") | ✅ / ❌ |
| Includes specific values where applicable (percentages, row numbers, file types) | ✅ / ❌ |

---

### Rubric: Warning Messages

| Criterion | Check |
|---|---|
| States the condition factually (no alarm language) | ✅ / ❌ |
| If time-sensitive, includes exact date/time/timezone | ✅ / ❌ |
| If multi-part, includes specific entity names | ✅ / ❌ |
| Does not use "Warning!" with exclamation | ✅ / ❌ |
| Explains the consequence of inaction where relevant | ✅ / ❌ |

---

### Rubric: Instructional Copy (Agent/Internal Tools)

| Criterion | Check |
|---|---|
| Uses imperative voice for required actions | ✅ / ❌ |
| Navigation hints use "click [element name]" matching the actual UI label | ✅ / ❌ |
| Compliance-required language (TPMO, HIPAA, SOA, TCPA) is included where applicable | ✅ / ❌ |
| Contact-matching messages follow 2-line pattern: status + next-step | ✅ / ❌ |
| Sentence case throughout | ✅ / ❌ |

---

### Universal Rules (apply to all copy types)

| Criterion | Check |
|---|---|
| No emoji | ✅ / ❌ |
| Body copy is a complete sentence ending with a period (fragments only acceptable for labels, pills, and modal titles) | ✅ / ❌ |
| No exclamation points | ✅ / ❌ |
| Named entities in single quotes | ✅ / ❌ |
| No casual filler ("Hey", "Just", "Simply", "Basically") | ✅ / ❌ |
| Dates formatted correctly (M/D/YY ranges; MM/DD/YY specific; h:mmpm Timezone) | ✅ / ❌ |

---

## Part 4: Reusable Skill / Agent Prompt

Copy this prompt to use as a standalone skill, custom GPT system prompt, or reusable instruction block for Claude or any LLM.

---

```
# Centerfield UX Copy Agent

You are a UX copy specialist for Centerfield. You generate, review, and improve UI microcopy for internal tools (Batting Cage, CRM Agent) and customer-facing products.

## Your Source of Truth
All copy must conform to the voice, tone, and structural patterns documented in the Centerfield UX Copy Style Guide. The guide is derived from approved Figma examples. Do not invent brand rules beyond what the guide documents.

## Default Output Format
For every request, return:

1. **Recommended Copy** — the best option following approved patterns
2. **Why it fits** — cite the specific pattern or rule it follows
3. **Alternatives** (if useful) — 1–2 variations with brief notes on when to use each
4. **Tone/alignment notes** — flag anything that is inferred vs strongly supported by approved examples

---

## Voice & Tone Rules

**Always:**
- Direct: state what is happening, not what might be happening
- Specific: use actual entity names, numbers, dates — never "this item" or "the selected record"
- Consequential: in confirmations, always explain what changes before asking for agreement
- Structured: use discrete list formatting for multi-step errors or instructions
- Named entities in single quotes: 'Cluster Name', 'Zone Name'
- Sentence case for body copy and toasts; Title Case for modal titles and error headlines
- Passive voice for system-led success: "ha- Complete sentences with proper punctuation: all body copy, toasts, warnings, and error messages are complete sentences ending with a period. Fragments are only acceptable for short labels, pill copy, and modal titles.
s been saved successfully" not "You saved it"
- Active voice for agent/person-led activity logs: "Agent Name called Contact Name"

**Never:**
- No emoji
- No exclamation points
- No apology language: "Sorry", "Oops", "Unfortunately"
- No casual filler: "Hey", "Just", "Simply", "Basically"
- No generic entity references: never "the item", "the selected record", "this thing"

---

## Copy Patterns by Type

### Confirmation Modal
- **Title:** `Confirm [Gerund Verb] [Object]` — e.g. "Confirm Deleting Zone"
- **Bold message:** `Are you sure you want to [action] the [entity type] '[name]'?`
- **Body:** Consequence + severity signal
  - Reversible: ends with "please proceed with caution"
  - Irreversible: starts with "CAUTION:"
  - Wide scope: starts with "IMPORTANT:"
- **CTAs:** Cancel (always "Cancel") + `Yes, [Verb] [Object]` or "Confirm"

### Success Toast
- `[Entity] '[name]' has been [action] successfully.`
- Add follow-up: `It can be [action] as needed.` for reversible deactivations
- Plural: `[N] [Entities] have been [action] successfully.`
- Two-line winner: `Winner Successfully Declared\n[Traffic outcome explanation]`

### Error Message
- **Headline (title case):** "Unable to Save" / "Unable to Import File" / "Bulk Action Failed"
- **Body:** Specific field/constraint/row. If multiple fixes: "Take any of the following actions to resolve: [list]"

### Warning
- Factual statement of condition. No alarm.
- Time-sensitive: include exact date/time/timezone. Format: `h:mmpm Timezone`
- Expiry: `Warning\n[Action needed] by [date] at [time] [timezone].`

### Instructional (Agent/Internal Tools)
- Imperative voice: "Inform customer that…", "Do not call back if…"
- Navigation: "For [context], click [exact element label]"
- Contact matching: `[N] Matching Contact(s) Found. / [Next action instruction].`

### Inline Status / Pill
- Short state or required action: "Action Required", "Read in the first 60 seconds"

---

## Evidence Transparency
Always distinguish:
- **Strongly supported** — pattern appears 5+ times consistently in approved examples
- **Inferred** — consistent with the voice but only 1–3 examples, or extrapolated from context
```

---

## Part 5: Example Prompts & Outputs

---

### Example 1: New Confirmation Modal

**Prompt:**
> Write a confirmation modal for permanently deleting a scheduled report called "Weekly Revenue Summary." This is irreversible.

**Recommended Copy:**

> **Title:** Confirm Deleting Scheduled Report
> **Bold message:** Are you sure you want to permanently delete the Scheduled Report 'Weekly Revenue Summary'?
> **Body:** CAUTION: This will permanently delete the report and all associated schedule settings. This action cannot be undone.
> **CTAs:** Cancel | Yes, Delete Report

**Why it fits:** Title follows `Confirm [Gerund] [Object]`. Bold message uses single-quoted entity name and specific language. CAUTION: is used correctly — this is an irreversible action. Confirm CTA mirrors the title verb ("Delete").

**Alternative:** If the action is technically recoverable (e.g. via audit log):
> **Body:** Deleting this report will remove it and all schedule settings immediately. You will not be able to restore it from this view. Please proceed with caution.
> **CTA:** Yes, Delete Report

**Tone note:** The CAUTION: signal is *strongly supported* by approved examples (archiving cluster, ending variation). No emoji or exclamation.

---

### Example 2: Success Toast for CRM

**Prompt:**
> Write a success toast for when an agent successfully transfers a call to a specialist.

**Recommended Copy:**
> "Call has been transferred to [Specialist Name] successfully."

**Why it fits:** Follows `[Entity/action] has been [verb] successfully.` passive voice pattern. Sentence case. Entity name would be populated dynamically.

**Alternative (if agent-to-agent is logged as activity):**
> "Agent Name transferred the call to Specialist Name."

**Tone note:** The first version follows the *system-led success* pattern (strongly supported). The second follows the *activity log* pattern (strongly supported for agent actions). Choose based on where this message appears — toast vs. feed.

---

### Example 3: Copy Review

**Prompt:**
> Review this error message: "Oops! Something went wrong. Please try again later or contact your admin."

**Review:**

❌ **Fails 4 rubric criteria:**
1. "Oops!" — apology language, not permitted
2. "Something went wrong" — not specific; does not name the field, constraint, or cause
3. No error headline (title case label missing)
4. "Please try again later" — passive and vague; no actionable next step

**Recommended replacement:**
> **Unable to Save**
> Error connecting to the server. Please try again. If this error persists, contact IT.

**Why it fits:** Mirrors the approved error pattern. Headline is title case. Body is specific about the cause (server connectivity). Resolution steps are direct.

**Tone note:** "Unable to Save / Error connecting to AWS. Please try again, and if this error persists contact IT." is present verbatim in the approved Figma examples (node 1020:582) as an error label — strongly supported.

---

### Example 4: Inline Warning

**Prompt:**
> Write an inline warning for a CRM field where the entered zip code doesn't match the contact's zip code on file.

**Recommended Copy:**
> **Title:** Zip codes don't match.
> **Body:** Update the zip above, or continue to use the new zip for this script.

**Why it fits:** This is directly sourced from the approved CRM design (node 1426:31987). The pattern is: short factual title + two-option resolution instruction.

**Tone note:** Strongly supported — this exact copy exists in the approved source.

---

## Part 6: Decision Log Protocol

Every time a copy option is approved and used, log it to `ux-copy-decisions.json` in the same folder as this skill. This keeps the skill grounded in what Centerfield actually ships, not just what the Figma mocks contained.

### When to log
- A copy option from the skill was chosen and will be implemented
- A new copy example is approved by the team outside of a Figma source
- An exception to a documented pattern was approved (these are especially important to log)

### How to log
Append a new entry to the `decisions` array in `ux-copy-decisions.json` using this shape:

```json
{
  "date": "2026-04-02",
  "copy_type": "modal",
  "use_case": "Confirm deleting a scheduled report",
  "prompt": "Write a confirmation modal for permanently deleting a scheduled report called 'Weekly Revenue Summary'",
  "chosen_copy": {
    "title": "Confirm Deleting Scheduled Report",
    "body": "CAUTION: This will permanently delete the report and all associated schedule settings. This action cannot be undone.",
    "cta_cancel": "Cancel",
    "cta_confirm": "Yes, Delete Report"
  },
  "pattern_used": "Confirm [Gerund] [Object] / CAUTION: for irreversible actions",
  "notes": "First use of CAUTION: pattern for a non-Batting Cage context — pattern holds",
  "source": "generated"
}
```

### How the skill uses the log
When generating new copy, check `ux-copy-decisions.json` before finalizing a recommendation:
1. If a similar `use_case` exists in the log, surface the previously approved copy as the primary option
2. If a pattern appears 3+ times in the log without deviation, elevate it from ⚠️ Inferred to ✅ Strongly supported in future outputs
3. If a logged entry deviates from a documented pattern and includes a `notes` field explaining why, treat that deviation as a valid exception

---

## Part 7: Gaps — Where to Add More Examples

The following copy types are **not represented** in the current Figma sources. Future examples in these areas would strengthen the skill:

| Gap | Why it matters | Suggested source to add |
|---|---|---|
| **Empty states** | Zero examples found — no pattern for what to show when a list/table is empty | Batting Cage empty list states, CRM no-results screens |
| **Tooltip copy** | No tooltip examples extracted — unknown character constraints or tone | Design system tooltips, hover states |
| **Form field validation (inline)** | Only generic "Helper text" placeholder found — no real examples of field-level errors or hints | Any form flow with field validation |
| **Loading states** | No examples — unknown if Centerfield uses progress messages or just spinners | Any async operation UI |
| **Onboarding / first-run copy** | No examples — tone for new-user experience unclear | New user flows if they exist |
| **Navigation labels / breadcrumbs** | Some section headers found but no navigation-specific patterns | Side nav, breadcrumb trail |
| **CTA copy outside modals** | Many "Button Text" placeholders in CRM; no real examples for primary page-level actions | CRM action buttons, Batting Cage page CTAs |
| **Bulk Actions file (node 472-2239)** | This file returned 0 text nodes — it may be a visual-only mock or use a different structure | Re-check this file with a broader node scan |
| **Positive reinforcement** | No examples of encouraging/affirming copy — unclear if it's intentionally absent or just not covered | Any onboarding or completion step |
| **Multi-step wizard guidance** | Step indicators and progress guidance not captured | Experiment setup wizard, multi-step forms |
| **Accessibility / screen reader text** | No aria-label or alt-text conventions found | Design tokens, component specs |

---

## Appendix: Raw Source Summary

| File | Node | Label | Text Nodes Extracted |
|---|---|---|---|
| Batting Cage Design System 1.0 | 500:5331 | Modals Library | 105 |
| Batting Cage Design System 1.0 | 1020:582 | Message Library (ALIYA) | 71 |
| Bulk Actions | 472:2239 | Cluster Mocks | 0 (visual only) |
| CRM | 1426:31987 | Agent Mocks (FINAL) | 653 (filtered to ~150 meaningful) |

**Total unique approved examples analyzed:** ~326 meaningful text nodes
**Copy types represented:** Modals, success toasts, warning banners, error messages, activity logs, instructional reminders, contact matching, upload states, inline alerts, script guidance pills
