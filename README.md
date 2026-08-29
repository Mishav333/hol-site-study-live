# House of Longevity — The Site Study

Live landing page for `houseoflongevity.com.au/study` — the Phoenix mine-site campaign funnel.

## Structure

- `index.html` — root: redirects to `/study/`
- `study/index.html` — the landing page (locked build from 2026-08-26): entry, 7-question survey,
  optional attribution questions, invitation, name capture
- `CNAME` — `houseoflongevity.com.au` + `www.houseoflongevity.com.au`

## Back end

Submissions POST to a Google Apps Script web app and land in the **HOL - Mines Quiz** Google Sheet
(tab `Responses`): `Timestamp, Q1–Q7, Signed up, Name, Email, Mobile, Next home, Source, Seen screens, Feedback`.

The page also captures `utm_source / utm_medium / utm_campaign / utm_content / utm_term` and sends them
with every submission. To log them in the sheet, the Apps Script needs a small patch (append those keys
to the row it writes). GA4 can be switched on by setting `GA4_ID` at the top of `study/index.html`.

## Deploying

Any push to `main` redeploys. Do not edit the quiz or copy without sign-off — the content is locked.
