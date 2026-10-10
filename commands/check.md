---
description: Is this job posting still open, or a ghost job? Checks it against the employer's own career site. Example - /jobhunt:check https://company.wd1.myworkdayjobs.com/...
argument-hint: "<job posting URL>"
---

Check whether this job posting is still open: $ARGUMENTS

Call `is_job_still_open` with the URL. Tell me plainly whether it is still live on the employer's own
site, when it was last confirmed there, and how long it has been posted. If it is open, offer to read the
whole posting with `get_job` and tell me what the employer is really asking for. If it is closed, offer to
find similar open jobs nearby with `search_live_jobs`.
