# CPBC Enquiry System — PRD v1

**The shared starting point for everyone's new system.**
Built from the Week 3 model answer, and written to fix what the Week 3 markup found in
`CPBC-PRD-v0`. Version 1.3.

S1 and S2 were built in Week 6. You build story S9 from this document in the Week 7
lab, and story S4 is the Week 7 homework. The backlog in §5 is the order we build in,
one story at a time.

---

## §0 What this document fixes

`CPBC-PRD-v0` is the Centre's original requirements document, the one you marked up in
Week 3 and saw the consequences of in Legacy. This version is written to the standard
that markup produced. Eight principles, and what each one fixed.

| Principle | What v0 did | What v1 does |
|---|---|---|
| **Every requirement can be tested** | "modern, intuitive and user-friendly" (R9); "the System shall be fast" (R30) | Each story carries acceptance criteria a stranger could check. Nothing is "user-friendly" |
| **The person the system serves is a user** | §3 listed five stakeholders and left out the enquirer | §2 names the enquirer first, and the front desk who acts for them |
| **Nothing contradicts anything else** | Triage in 2 minutes (R11) and a lawyer reviews every enquiry first (R12) | The backlog separates the suggestion (S3) from the human confirming it. One story, one decision |
| **Out of scope means a boundary, with a reason** | §5 was a list of what there was no budget for, and three deferrals contradicted requirements above them | §4 says what the system is not for, with a reason beside each line |
| **Only the data a story needs** | R3 "all information that may be relevant"; R5 took NRIC, date of birth, address and household income from everyone | §6 lists each field with the story that needs it, and names what is deliberately not collected |
| **Retention is decided, not assumed** | R26 kept everything indefinitely, "for audit purposes" | §7 says retention is settled with legal advice before anything real is stored |
| **Security is in the document** | Nothing. Not one security requirement anywhere | §9, from the start, including the parts that only apply once there is a server |
| **Somebody owns it after handover** | R29 asked for open source to save money, and said nothing about keeping it up to date | §7 names maintenance, including who keeps outside code current |

Two things v1 keeps from v0, because they were sound: the description of the problem
in §1, and the scope of one enquiry's journey in §3.

---

## §1 The problem

The Centre receives enquiries by walk-in, telephone and email. They are written on
paper and copied into a spreadsheet of more than four thousand records. Enquiries
are allocated to volunteers by hand.

Volunteers are given matters outside their practice area. Nobody knows whether an
enquiry is close to a limitation deadline until someone reads it. A person who
cannot afford a lawyer waits longer than they need to, and sometimes past the point
where their claim can still be brought.

The current system, CPBC Legacy, makes this worse for the people it exists to serve.
It turns away anyone without an email address. It demands an NRIC number and
household income before anyone can ask a question. It gives no reference number and
no idea of what happens next.

## §2 Who uses it

| Role | Who they are | What they need from the system |
|---|---|---|
| **The enquirer** | A member of the public asking the Centre for help | To ask for help easily, and to know it arrived |
| **The front desk** | Centre staff taking walk-in and phone enquiries | To submit an enquiry on someone else's behalf |
| **The Centre Manager** | Checks each enquiry and chooses the volunteer | To see what is new and what is urgent |
| **The volunteer lawyer** | Takes on matters in their area of practice | To know when they have been given a matter |

## §3 In scope

One enquiry's journey, end to end:

1. The enquiry is submitted, by the enquirer or by the front desk for them.
2. It is triaged to an area of law.
3. It is checked for a limitation period.
4. It is matched to the Centre's guidance for that area.
5. It is routed to a volunteer who works in that area.

## §4 Out of scope

| Not building | Why |
|---|---|
| Anything after the volunteer accepts the matter | That is case management — a different system |
| The Centre's timesheet | It exists and it works. Replacing it is not this problem |
| Reporting to the Board and to funders | It is about many enquiries. This system is about one |
| Volunteer recruitment and accreditation | A different journey with different people |
| An AI that answers volunteers' legal questions | It carries risks this document does not address, so it is left out on purpose |
| Enquirers checking their progress online | Useful, but the enquiry still reaches the right volunteer without it. Below the MVP line |

## §5 User stories — the backlog

Built in this order. Stories above the MVP line are the MVP.

| # | Role | Story | Sprint |
|---|---|---|---|
| S1 | Enquirer, front desk | As an enquirer, or the front desk acting for one, I want to submit an enquiry with only the details the Centre needs, and get a reference, so that I can ask for help without an email address and know it arrived | Week 6 lab — done |
| S2 | Centre Manager | As the Centre Manager, I want to see every new enquiry in one list, with any time-critical enquiry at the top, so that urgent matters reach a volunteer first | Week 6 homework — done |
| **S9** | Centre Manager | As the Centre Manager, I want every enquiry, from any computer, kept by the Centre in one list, so that no enquiry stays on the computer it was typed on | **Week 7 lab** |
| **S4** | Centre Manager | As the Centre Manager, I want an enquiry with a limitation deadline inside thirty days marked time-critical by the Centre's server, so that it reaches a volunteer while something can still be done | **Week 7 homework** |
| S3 | Centre Manager | As the Centre Manager, I want each enquiry given a suggested area of law, which I confirm or change, so that no enquiry is routed on a guess nobody checked | Later |
| S5 | Centre Manager | As the Centre Manager, I want to assign an enquiry to a volunteer who works in its area of law, so that nobody is given a matter outside their practice | Later |
| S6 | Volunteer lawyer | As a volunteer lawyer, I want to be told when I have been assigned a matter, so that nothing waits for me without my knowing | Later |
| S7 | Volunteer lawyer | As a volunteer lawyer, I want to see the Centre's guidance for the matter's area of law, so that I start from what the Centre already knows | Later |

S9 is new in version 1.3. It was added when the Week 6 build showed that S1 and S2
keep every enquiry in one browser, where nobody at the Centre can see it. A story
added later takes the next free number, so S9 sits above S3 in the build order.

--- MVP line ---

| # | Role | Story | Sprint |
|---|---|---|---|
| S8 | Enquirer | As an enquirer, I want to check my enquiry's progress online, so that I do not have to phone the Centre | Not in the MVP |

### S1 — acceptance criteria

Each criterion can be checked by someone who was not in the room.

1. The form can be submitted with a phone number and no email address, and with an
   email address and no phone number. It cannot be submitted with neither.
2. The form asks for these fields only: full name, phone number, email address,
   preferred language, a description of the problem, whether a deadline or court
   date is known (and if so, the date), and who is submitting it (the enquirer, or
   the front desk for them).
3. The form does not ask for an NRIC number, date of birth, address, income or
   documents.
4. Before the enquirer submits, the form shows a short notice saying what the
   details are used for and that the Centre does not give legal advice through the
   form. The notice is above the Submit button, in the same size of text as the
   form.
5. After submitting, the page shows a reference number in the form `CPBC-` followed
   by four digits. Each enquiry gets a different number.
6. After submitting, the page says the Centre will make contact within three
   working days, and gives the Centre's phone number, 6000 0000, to call if nobody
   has.
7. The page shows how many enquiries have been submitted in this browser. After the
   page is reloaded, the number still includes every enquiry submitted before. The
   form never shows anyone's details. Enquiries are kept in this browser, on this
   computer, only (see §7).
8. All text meets a contrast ratio of at least 4.5 to 1 against its background.

### S2 — acceptance criteria

Each criterion can be checked by someone who was not in the room.

The Centre has decided what "time-critical" means: a deadline or court date that is
today or within the next 30 days. S2 shows it in the browser. S4 makes the server
decide it, from Week 7.

1. The page has a link labelled "Centre Manager's list". It opens the list. The list
   has a link back to the enquiry form. The form and the list are never on screen at
   the same time.
2. The list shows every enquiry submitted in this browser, one per row. Each row shows
   the reference, the full name, the date and time submitted, and the deadline or court
   date if one was given.
3. An enquiry whose deadline or court date is today, or within the next 30 days, is
   marked "Time-critical". Time-critical enquiries appear above all enquiries that are
   not, earliest deadline first.
4. An enquiry whose deadline or court date has already passed is marked "Deadline
   passed". These appear at the very top of the list, above the time-critical ones.
5. All other enquiries appear below, newest first.
6. When no enquiries have been submitted in this browser, the list says "No enquiries
   yet."
7. S1 still works: S1's criteria 1 and 5 still pass after S2 is added.

### S9 — acceptance criteria

Each criterion can be checked by someone who was not in the room. §7 says how the
system is built from Week 7.

1. An enquiry submitted in one browser appears in the Centre Manager's list when the
   list is opened in a private window, or in a different browser.
2. The server gives each enquiry its reference, in the form `CPBC-` followed by four
   digits. No two enquiries ever get the same reference, whichever browser they came
   from.
3. The server checks that a phone number or an email address was given. If neither
   was, the server refuses the enquiry, saves nothing, and the page shows the server's
   message.
4. For testing, the page skips its own checks when its address ends in `?nocheck`.
   The server's check still applies. This is how criterion 3 is tried.
5. Every enquiry the server accepts is saved in `enquiries.json`, which can be opened
   and read.
6. The server listens only to this computer, at `http://127.0.0.1:8000`.
7. S1 and S2 still work. S1's criteria 1 to 6 and S2's criteria 1 to 6 still pass. The
   count in S1 criterion 7, and the list in S2, now show every enquiry the server
   holds, not only those from this browser. The form still never shows anyone's
   details.

### S4 — acceptance criteria

Each criterion can be checked by someone who was not in the room.

S2 marks time-critical enquiries in the browser. S4 moves that decision to the server,
where the Centre controls it. "Time-critical" still means a deadline or court date
that is today or within the next 30 days.

1. The server decides each enquiry's mark: "Deadline passed", "Time-critical", or no
   mark. The page shows the mark the server decided. It does not work out the mark
   itself.
2. The server decides the mark each time the list is shown, not once when the enquiry
   is saved. An enquiry becomes time-critical on the day its deadline comes within 30
   days.
3. "Today" means today in Singapore.
4. An enquiry with no deadline or court date is never marked.
5. The list is in the same order as S2's criteria 3 to 5 describe.
6. S1, S2 and S9 still work: their criteria still pass.

## §6 Data

What the system holds about a person, and which story needs each field.

| Field | Needed by | Kept for |
|---|---|---|
| Full name | S1 — to know who is asking; S5 — to route it | See §7 |
| Phone number, or email address, or both | S1 — at least one way to make contact | See §7 |
| Preferred language | S1 — so the Centre contacts them in a language they can use | See §7 |
| Description of the problem | S1; S3 — to suggest an area of law | See §7 |
| Known deadline or court date | S1; S4 — to mark time-critical enquiries | See §7 |
| Submitted by (enquirer or front desk) | S1 — so the Centre knows who to go back to | See §7 |
| Reference number | S1 — so the enquirer can quote it | See §7 |
| Date and time submitted | S2 — to order the list | See §7 |

**Not collected, on purpose:** NRIC number, date of birth, residential address,
employment status, household income, household size, and documents. No story in this
backlog needs them. If a later story needs one, it is added here with that story
named.

## §7 Constraints

- **Built by an AI agent, one story at a time.** Each story is checked against its
  criteria before the next one starts.
- **Weeks 6 and 7 — from one file to a small server.** In Week 6 the system was a
  single HTML file, with enquiries kept in one browser. From Week 7 it is a small
  server built with Flask, in these files:

  | File | What it is |
  |---|---|
  | `app.py` | The server. It answers each request, checks what arrives, and saves it |
  | `templates/index.html` | The page the server sends to the browser — the S1 form and the S2 list |
  | `enquiries.json` | The enquiries the server has accepted. It is a prototype of the Centre's record, not the record itself |
  | `requirements.txt` | The outside code the server needs: Flask. See §9 item 5 |

  The server starts with the command `python app.py` (`python3 app.py` on macOS). It
  listens only to this computer, at `http://127.0.0.1:8000`, until §9's sign-in is
  built in Week 12. From Week 8, enquiries move from `enquiries.json` into a database.
- **Records stay out of the repository.** `enquiries.json` is never committed. The
  starter's `.gitignore` file keeps it out. The repository holds the system, not the
  people who used it.
- **Synthetic data only.** No real person's details are ever entered.
- **Retention.** How long enquiries are kept, and when they are deleted, is to be
  decided by the Centre with legal advice before any real enquiry is stored. Until
  then, nothing real is stored.
- **Budget and maintenance.** Whoever maintains the system after handover is named
  before it goes live, including who keeps outside code up to date.

## §8 Done

A story is done when every one of its acceptance criteria has been checked and
recorded as met, and the record is committed with a tag. A criterion that cannot be
checked yet is recorded as not met, with the reason, and stays on the backlog.

The MVP is done when S1 to S7, and S9, are done.

## §9 Security

`CPBC-PRD-v0` had no security requirement at all. This one does, from the start,
even though some of it only applies once there is a server.

1. Only signed-in Centre staff and volunteers can see enquiries. Each person signs in
   as themselves — no shared accounts. *(From Week 12.)*
2. A volunteer sees only the matters assigned to them. *(From Week 12.)*
3. The system records who opened which enquiry, and when. *(From Week 12.)*
4. Nothing an enquirer types is ever run as code, in the browser or on the server.
   *(From S1, and checked again in Week 12.)*
5. Outside code the system depends on is listed, and checked against published
   security advisories before each release. *(From Week 7.)*

---

## Changes

| Version | Date | What changed |
|---|---|---|
| 1.0 | 26 Sep 2026 | First version, for the Week 4 lab |
| 1.1 | 2 Oct 2026 | S1 and S2 move to Week 5, because the Week 4 build did not run. Nothing else changed |
| 1.2 | 13 Oct 2026 | S1 and S2 move to Week 6. S2's acceptance criteria written, including what "time-critical" means. The server arrives in Week 7 |
| 1.3 | 22 Oct 2026 | S1 and S2 done. New story S9 — the Centre keeps every enquiry on its server — for the Week 7 lab, with its criteria. S4's criteria written, for the Week 7 homework. §7 describes the server's files and says records stay out of the repository |
