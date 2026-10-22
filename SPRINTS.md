# Sprint record

Name:

## What this file is for

This file is the record of each sprint: what you asked the agent for, what you checked,
and what you found. The stories come from the backlog in §5 of `prd.md`.

It matters for three reasons.

1. **It is how you review what you cannot read line by line.** You cannot check every
   line the agent wrote. You can check every criterion, and write down what happened.
2. **It is evidence.** "We tested it" is a claim. A record that names each criterion,
   how it was checked, and what was still not met, is evidence that someone reviewed
   the work.
3. **It is what the Centre accepts.** Under §8 of `prd.md`, a story is done when every
   criterion has been checked and recorded as met, and the record is tagged. This file
   is that record.

Write it as you go, not afterwards. A criterion marked "not met", with the reason, is
worth more than six ticks nobody can stand behind.

---

## Sprints 1 and 2 — stories S1 and S2 (Week 6)

Done in Week 6. Your own record is in your `week6` repository.

This starter's `index.html` is your facilitator's build of S1, checked against every
criterion. Everyone starts Week 7 from the same file.

---

## Sprint 2 again — story S2 (practice, in the Week 7 lab)

You built S2 at home in Week 6. Today you build it again, in the room, with the same
prompt. S9 builds on S2's list, so everyone needs a working S2 first.

### The prompt I gave the agent

### The quick check

Use a private window, so the list starts empty. Submit three enquiries: Tan Mei Ling
(deadline 7 days ago), Lim Ah Kow (14 days from today) and Priya Nair (91 days from
today).

| What I checked | What I saw |
|---|---|
| The list said "No enquiries yet." before I submitted | |
| The order: Tan Mei Ling, Lim Ah Kow, Priya Nair | |
| Tan Mei Ling marked "Deadline passed"; Lim Ah Kow marked "Time-critical" | |
| Priya Nair not marked | |

No tag. S2 goes into `v0.3`, with S9.

---

## Sprint 3 — story S9 (in the Week 7 lab)

### The story

As the Centre Manager, I want every enquiry, from any computer, kept by the Centre in
one list, so that no enquiry stays on the computer it was typed on.

### The prompt I gave the agent

### The files the agent said it would create or change

### The assumptions the agent listed

Write down any you did not expect. Each one is a place where the PRD was silent.

### The acceptance criteria

The full criteria are in §5 of `prd.md`. Try each one. Write met or not met, and how
you checked it.

| # | Criterion (short) | Met? | How I checked |
|---|---|---|---|
| 1 | An enquiry from one browser appears in the list in a private window | | |
| 2 | The server gives the reference, `CPBC-` and four digits, never the same twice | | |
| 3 | The server refuses an enquiry with no phone and no email, and saves nothing | | |
| 4 | `?nocheck` skips the page's own checks | | |
| 5 | Accepted enquiries are in `enquiries.json` | | |
| 6 | The server listens only at `http://127.0.0.1:8000` | | |
| 7 | S1 and S2 still work, now from the server | | |

### What I found

Anything the agent did that nobody asked for:

Tag: `v0.3`

---

## Sprint 4 — story S4 (homework)

### The story

As the Centre Manager, I want an enquiry with a limitation deadline inside thirty days
marked time-critical by the Centre's server, so that it reaches a volunteer while
something can still be done.

### The prompt I gave the agent

### The files the agent said it would change

### The assumptions the agent listed

### The acceptance criteria

The full criteria are in §5 of `prd.md`. Try each one, using the seven test enquiries
on the lab page. Write met or not met, and how you checked it.

| # | Criterion (short) | Met? | How I checked |
|---|---|---|---|
| 1 | The server decides each mark; the page only shows it | | |
| 2 | The server decides each time the list is shown | | |
| 3 | "Today" is today in Singapore | | |
| 4 | No deadline, no mark | | |
| 5 | Same order as S2 | | |
| 6 | S1, S2 and S9 still work | | |

### What I found

Anything the agent did that nobody asked for:

Tag: `v0.4`
