# Hearts & Minds NYC: design decisions

## What it is

The Radar is a single live screen for the NYS Office of Customer Experience and agency program teams. It shows the biggest problems New Yorkers hit with Medicaid, how many people each one affects, and what it sounds like in their own words. Everything else comes after that one view.

## Built on the NYS Design System

We used the [NYS Design System](https://designsystem.ny.gov/) rather than a custom style, so the demo reads as a New York State product from the first glance.

- **Colors come from the system's tokens.**
  - The heat scale runs through the NYS theme blues, from `theme-weaker` up to `theme-stronger` (around the primary `#154973`).
  - Text uses `ink` and `text-weak`.
  - Keyboard focus outlines use the system focus blue, `#004dd1`.
- **The yellow accent (`#face00`) is used only twice:** on the selected box and on the "Spiking" tag. Keeping the strongest color for the two things that need attention stops it from becoming noise.
- **Type follows the system.** Its primary typeface, Proxima Nova, needs a license we don't have here, so Montserrat stands in. Oswald, the system's supporting typeface, is used for the small uppercase labels and stage numbers.
- **The NYS universal header** ("An official website of New York State") sits on top, as on any state site.
- **A one-color heat scale** stays readable for colorblind users and still works printed in grayscale, which matters when the output ends up in a brief.
- **A Lo-fi toggle** switches to grayscale wireframes that match the Paper file, which is useful for design reviews.

## Why it looks the way it does

**1. A tool, not a report.** The early versions read like documents and felt too busy. We cut the KPI strip, score bars, filter rows and side panel. What's left is one headline, one heatmap and one feed, so the largest issues are obvious within seconds.

**2. Organized by the Medicaid journey.** Columns run Apply → Verify → Enroll → Use care → Renew, and Renew loops back to Verify. Agencies think in process steps, so this shows *where* pain piles up and makes the handoffs between agencies visible. Labels on individual groups were removed; the sequence bar alone carries the order.

**3. Size and shade answer different questions.**

- **Box size is New Yorkers affected.** That's estimated from enrollment data, not from posts.
- **Shade is mentions in the last 30 days.** That signals what's heating up right now.
- **The trend line shows the last 90 days.**

Keeping these separate is the point. A big but quiet box (renewals) and a small but fast-rising one (home-care aide pay) need different responses. The legend says exactly what the shade encodes.

**4. Mentions show attention, not rank.** Ranking still uses the Harm Score (severity, reach, equity, velocity). Views, likes and how angry a post sounds never raise a problem's rank, so quiet harms, like seniors who don't post, aren't drowned out by viral ones.

**5. One number per box.** Each box shows a single figure and a trend line. The detail lives in the selected panel.

**6. Agency filters instead of labels.** Agencies are the main users, and their first question is "what's mine?" Filtering fades other agencies' boxes rather than hiding them, so the whole journey stays in view. Tooltips explain what each agency actually handles.

**7. Real voices in every box.**

- **Real videos are embedded** in the boxes and in a scrolling feed tied to the selected problem.
- **Real is never mixed up with made-up.** Real videos carry a "Real story" or "News" badge. Videos that relate only loosely to a problem are marked as context.
- **No invented quotes for real people.** We only quote what they actually said; otherwise we use a plain description.

**8. Built for trust.** Government users won't act on something they can't check:

- each problem names its owner and explains why
- the content audit corrected the agency owners (for example, the Medicare Savings Program is processed by HRA, not HIICAP)
- a "Sample data" label marks what's illustrative
- the ranking method is one click away

## How we got here

We started lo-fi and explored three directions:

- **Top-3 cards:** the three biggest problems as large cards with clips.
- **Explorable heatmap:** the direction we chose.
- **Story mode:** one story at a time, video first.

We also tried driving the heatmap directly from the 55-area (PUMA) work-requirement dataset. That was too cluttered, so the heatmap went back to problem-level boxes. Story mode and the neighborhood map remain options for drilling into a single problem.

## Known gaps

- The counts, Harm Scores and trends are sample data.
- Some names and quotes in the real videos still need a manual check, because transcripts couldn't be pulled.
- The Proxima Nova license is needed for an exact match to the design system.
