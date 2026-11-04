# Worked records

Three proffer records, one per posture the instrument knows. Each one satisfies
every gate its posture applies, so each is the shortest path to seeing what a
complete record looks like before you write your own.

```text
python esquire_admissibility.py examples/civil.json            # seven gates
python esquire_admissibility.py examples/criminal.json         # nine gates
python esquire_admissibility.py examples/administrative.json   # seven gates, G10 in place of G6/G8/G9
```

All three report `READY` and exit 0. The records are fictional: the case names,
the people and the model versions are invented, and nothing here is a claim about
a real tool or a real proceeding.

## What each one demonstrates

| file | `proffer.forum` | gates applied | why it exists |
| --- | --- | --- | --- |
| `civil.json` | unstated | G1–G7 | the default reading. A record that names no forum is read as civil, and the report says so rather than leaving it implicit |
| `criminal.json` | `criminal` | G1–G9 | the confrontation pair. G8 and G9 apply only here, and they read a `confrontation` block the civil gate set never looks at |
| `administrative.json` | `arbitration` | G1–G5, G7, G10 | a forum that sets its own evidence law. G6 has no referent where the FRE hearsay rule does not apply, and the Sixth Amendment does not reach an arbitral tribunal, so both are dropped and G10 asks the question this forum does have |

The third file is the one worth reading closely. Its `forum` says `arbitration`,
the report says `forum: administrative (stated)`, and `forum_note` quotes
`'arbitration'` back — a posture label must never report a forum the record did
not invoke. Its `administrative` block is the whole of G10:

```json
"administrative": {
  "standard": "reliable, probative, and substantial evidence on the whole record",
  "standard_source": "5 U.S.C. 556(d); agency rule 1.33",
  "disclosed_to_opposing_party": true,
  "opportunity_to_respond": true
}
```

## Break one on purpose

A gate you have never seen fail is a gate you are trusting on faith. Each of these
edits turns one gate red, and the exit code follows.

| edit | gate | what the report says |
| --- | --- | --- |
| `civil.json`: set `review.authority_to_change` to `false` | G7 | `GAP — the reviewer had no authority to change the output`; verdict `GAPS`, exit 1 |
| `civil.json`: delete the `witness` block | G1 | `UNVERIFIABLE` — an omission, never a contradiction; verdict `INCOMPLETE`, exit 1 |
| `criminal.json`: set `confrontation.surrogate_analyst` to `true` | G9 | `GAP` naming *Bullcoming* |
| `administrative.json`: set `disclosed_to_opposing_party` to `false` | G10 | `GAP — the output was not disclosed to the opposing party, so there is nothing to contest`; exit 1 |
| `administrative.json`: delete the whole `administrative` block | G10 | `UNVERIFIABLE — the record does not state the evidentiary standard this forum applies to machine output`; verdict `INCOMPLETE`, exit 1 |
| any file: remove a comma | — | `BLIND`, exit 2. A record that does not parse is never a pass |

## What the examples deliberately do not show

A record that would be `READY` and still describe a fabrication. Every gate tests
the paperwork, and no arrangement of fields closes the gap between an authenticated
record and a true one — see §5 of the main document, "What this instrument cannot
see".
