# Fragrance Index

A cover-led fragrance catalogue with sourced community ratings and alternative comparisons.

[Open the website](https://siguatepeque.github.io/fragrance-index/)

- 500 male and unisex fragrances from one combined Fragrantica popularity search.
- Community ratings, exact vote counts, sources and collection dates.
- 232 screened alternative pairs, kept separate from the base population.
- Search, house/category filters, pagination and comparison of up to three fragrances.
- Alternative sorting by similarity agreement, community rating, most rating votes, most similarity votes, rating difference and name.

## Hosting

This repository's `gh-pages` branch is the publishing source for GitHub Pages, using the root directory. The `.nojekyll` file serves the supplied static website directly. No build service, API key or application server is required.

`index.html` contains the interface, fonts and catalogue data. The sibling CSV, JSON and Markdown files provide downloadable evidence and methodology. Product photographs load from the public source CDN and have a readable fallback.

## Reading the data

The displayed figures are community ratings, not a validated overall-quality or female-preference ranking. The 232 alternative pairs passed a preliminary screen; their manual comparative review is incomplete. Similarity agreement, rating differences and reported price ranges answer different questions.

[Methodology](methodology.md) · [500-fragrance CSV](fragrantica-500.csv) · [Alternative CSV](dupe-candidates.csv)

Public factual extracts retain source URLs and provenance. No full copied reviews, credentials or private wear-testing records are included. The embedded fonts retain their SIL Open Font License notices in the HTML.

## Updating the site

Replace the static exports on `gh-pages` and push the branch. GitHub Pages republishes it automatically. Keep links relative so project-path hosting and direct entry links continue to work.
