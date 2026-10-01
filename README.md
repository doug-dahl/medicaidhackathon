# Hearts & Minds NYC

A prototype for the NYS Office of Customer Experience. It brings together open data and public social media posts so agencies can see the biggest problems people hit with Medicaid, how many New Yorkers each one affects, and what it feels like in their own words.

This first version is the **Radar**: a heatmap of problems laid out in the order people move through Medicaid (Apply → Verify → Enroll → Use care → Renew). Box size is people affected and shade is harm. Selecting a box shows its 90-day trend and a scrollable feed of video clips.

The second view is **Design impact** (side nav, or `#impact`). It scores agency fixes against the standards the NYS Office of Customer Experience has published (three pillars, Digital First Standards, NYX Playbook, NYS Design System), tags each fix to a Radar problem, and shows neighborhood risk before and after, with public YouTube success stories. Published results link to their NY.gov source. Pilot neighborhoods and risk numbers are sample data.

## Run locally

It's a single static file. Serve it rather than opening it directly, since YouTube embeds don't play from `file://`:

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Data

- Problem counts, Harm Scores, and 90-day trends are **sample data** for the demo.
- Clips marked **Real story** or **News** are public YouTube videos shown with their original attribution. All other clips are placeholders.
- Styling follows the [NYS Design System](https://designsystem.ny.gov/). Montserrat stands in for Proxima Nova.

## Deploy

There's no build step. On Vercel, import the repo with the framework preset set to "Other" and leave the build command empty.
