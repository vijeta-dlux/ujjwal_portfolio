# Ujjwal Golwara | Portfolio (one HTML file per page)

Each page is its own self-contained file (Poppins and all content built in). Keep all the
HTML files and the `assets/` folder together in one folder: every link between pages is relative.

| File | Page |
|---|---|
| index.html | Homepage |
| case-studies.html | Case Studies (banner + all projects) |
| case-study-stan.html | STAN: Brand Identity & Visual System |
| case-study-tanishq-mothers-day.html | Tanishq: Mother's Day USA |
| case-study-designlensux.html | DesignLensUX: Brand Identity |
| case-study-tanishq-rivaah.html | Tanishq: Rivaah |
| case-study-stanfest-2024.html | STANFest 2024: Event Identity |
| case-study-tanishq-akshaya-tritiya-2025.html | Tanishq: Akshaya Tritiya 2025 |
| case-study-boat-nirvana-series.html | boAt: Nirvana Series |
| visual-archive.html | Visual Archive |
| branding.html | Branding (brand boxes) |
| brand-stan.html | STAN branding |
| brand-designlensux.html | DesignLensUX branding |
| brand-stanfest-2024.html | STANFest 2024 branding |

## Editing content (important)

Every file carries the same content block: search for **START HERE**. Because each file is
self-contained, a content change must be made in **every** file or the pages will disagree.
Safest way: edit the block in `index.html`, then copy everything from `const PORTFOLIO_CONTENT = {`
down to `END OF EDITABLE CONTENT` and paste it over the same block in the other files.
Never change the `window.__PAGE = ...` line under it: that line decides which page a file shows.

Links in the content keep their short form (`#/case/stan`, `#/branding/stan`, `#/case-studies`,
`#/archive`, `#work`). The pages turn them into the right file names automatically.

## Adding a page

- **New case study:** add the project to `featuredProjects` (in every file), duplicate any
  `case-study-....html`, rename it `case-study-<id>.html`, and set its `window.__PAGE` line to
  `{"view": "case", "id": "<id>"}`. Update its `<title>` at the top.
- **New brand:** add it to `branding` (in every file), duplicate any `brand-....html`, rename it
  `brand-<id>.html`, and set `window.__PAGE` to `{"view": "brand", "id": "<id>"}`.
- **Branding content:** add `blocks` to a brand (text, image, gallery, colours, type). Examples
  are written just above the `branding` list.

## Handy settings (in the content block)

- `workSection.show`: `"all"` projects in the Selected Work slider, or `"featured"` only.
- `workSection.imagesFirst`: projects with images lead the slider and the Case Studies page.
- `testimonialsSection.secondsPerCard`: testimonial scroll speed (higher is slower).
- `explore.caseStudies.banner`: the Case Studies page banner image.
- `SECTION_SETTINGS`: show or hide homepage sections.
- Colours: the `--color-...` tokens at the top of the `<style>` tag.

## Images

`assets/FILES-NEEDED.txt` lists every image path. Images already on your Framer site load from
there as a backup until you save local copies.

## Deploying

Upload the whole folder to Netlify (drag and drop), Vercel or GitHub Pages. Set your real domain
in each file's `canonical` and `og:url` tags (currently `https://your-domain.com/...`).
