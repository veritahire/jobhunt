# Job Hunt: your AI finds live jobs that fit your résumé

Ask your AI: **"Find me jobs like my résumé within 25 miles of Houston."**

It searches **2.5 million+ live US jobs read straight from the career sites of 19,000+ employers**
(Workday, iCIMS, Greenhouse, Lever, SmartRecruiters, UKG and more) and comes back with the jobs you
can actually get: the pay the employer posted, what each job asks for, how far it is, and the
employer's own apply link.

Works in **Claude Code** as a plugin, and in **Codex, Cursor, VS Code, Gemini CLI, Claude Desktop and
claude.ai** through the same MCP server. Free. No account, no key.

```
/plugin marketplace add veritahire/jobhunt
/plugin install veritahire@veritahire
```

## Why it's different

- **Every job is really open.** Each one is re-checked on the employer's own site and taken down within
  about 36 hours of the employer removing it. No ghost jobs, no "this job is no longer available".
- **Straight from the employer.** Apply links go to the employer's own posting, never through a job
  board, a reposter or a lead-gen form.
- **Reads like a recruiter.** Pay as posted plus an annual figure, the licences, education and years each
  posting asks for (required and preferred), the employment type, and the distance from you.
- **Built for your side of the table.** It ranks jobs by how well they fit you and never hides one over
  a "preferred" qualification.
- **Your résumé stays on your machine.** Only job titles, a place and your filters are sent to search.

## Use it

```
/veritahire:find resume.pdf Austin, TX
/veritahire:find resume.md remote, full time, $90k
/veritahire:watch you@example.com registered nurse, Houston, TX
/veritahire:check https://company.wd1.myworkdayjobs.com/en-US/careers/job/...
```

Or just talk to it: *"I'm a CDL-A driver near Dayton, what's hiring this week that pays at least $25 an
hour?"* The skill loads on its own when you ask about finding jobs.

| Command | What it does |
|---|---|
| `/veritahire:find` | Reads your résumé locally, runs 3 to 6 searches built from your experience, ranks the matches by fit, and goes deeper on the top three. |
| `/veritahire:watch` | Emails you new matching jobs every day (you confirm by clicking a link). |
| `/veritahire:check` | Is this posting still open, or a ghost job? Checked against the employer's own site. |

## What a search returns

A real search on 10 October 2026: registered nurse, within 25 miles of Houston, TX, at least $40 an
hour. 861 live jobs matched; here are the first five.

| Job | Employer | Where | Pay (as posted) | Asks | First seen |
|---|---|---|---|---|---|
| Per Diem RN II Infusion - Cancer Services - Kelsey Seybold Clinic: North Houston | UnitedHealth Group | Houston, Texas | $29.00 to $63.00 per hour | RN, 3 yr | Oct 10 |
| Infusion RN | CommonSpirit Health | Houston, TX | $44 per hour | RN, bachelor, 1 yr | Oct 10 |
| Field Based HSS Clinical Coordinator RN - Harris County, TX | UnitedHealth Group | Houston, Texas | $29.00 to $52.00 per hour | RN, 2 yr | Oct 9 |
| Main Emergency Services RN | CommonSpirit Health | Houston, TX | $35.45 - $55.36 per hour | RN, bachelor, 1 yr | Oct 9 |
| RN Coord - Endoscopy - Kelsey Seybold Clinics - Memorial Village. | UnitedHealth Group | Houston, Texas | $35 - $63 per hour | RN, bachelor, 3 yr | Oct 9 |

Each result also carries the employer's own apply link, the distance from you, the annual pay range, and
when it was last confirmed on the employer's site. `/veritahire:find` adds a fit rating for you and a short
read of the top postings.

## Other AI tools

The plugin is a thin layer over one MCP server: **`https://veritahire.com/mcp`** (streamable HTTP, no
auth). Point any MCP client at it. Setup for Codex, Cursor, VS Code, Gemini CLI, Claude Desktop and
claude.ai is in [docs/other-clients.md](docs/other-clients.md). Agents that read Agent Skills can use
[`skills/jobhunt/SKILL.md`](skills/jobhunt/SKILL.md) directly.

## For developers and heavy users

The free search allows about 30 searches an hour from one network. For more, and for bulk data:

- **Jobs API**: the same search over REST, 100 jobs a page with full descriptions, plus the bulk feed of
  every live US job. 2,000 free credits, then $3.95 per 1,000 jobs, or monthly plans.
  https://veritahire.com/verified-jobs-feed/
- **Docs**: https://veritahire.com/developers/docs/
- **Clients**: `pip install veritahire`, `npm install veritahire`
- **career-ops** users: [career-ops-plugin-veritahire](https://github.com/veritahire/career-ops-plugin-veritahire)
  adds these jobs to your career-ops pipeline.

## Privacy

Search requests carry job titles or keywords, a place and your filters. They never carry your résumé,
name, phone or email. `/veritahire:watch` sends the email address you give it, once you confirm, so the daily
email can reach you. VeritaHire's privacy policy: https://veritahire.com/privacy.php
Terms of service: https://veritahire.com/terms.php

## About

Built by [VeritaHire](https://veritahire.com), which reads US job postings straight from employers' own
career sites every day and publishes how fresh its data is at https://veritahire.com/jobdata.php.
Questions: data@veritahire.com or [open an issue](https://github.com/veritahire/jobhunt/issues).

MIT licensed.
