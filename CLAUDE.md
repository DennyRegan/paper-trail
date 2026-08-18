# History archive — project instructions

## What this is

A history article website. Articles on specific, well-documented events and
subjects, written from primary sources and published with the evidence for
each claim visible to the reader.

The distinguishing feature of this site is not the writing — it is that a
reader can see how much weight each claim actually bears. Established fact,
strongly supported claim, allegation, disputed history and repeated myth are
shown as different things. Everything in the design should serve that.

Structure is deliberately simple: homepage → category → article.

## Stack

Plain HTML and CSS. No frameworks, no build step, no static site generator,
no package manager, no JavaScript unless a specific feature genuinely
requires it and I have agreed to it first.

Deployment is GitHub → Vercel.

If you think something needs a dependency, say so and explain why before
adding it. Do not add one unprompted.

## File structure

```
index.html              homepage — lists categories
style.css               all styling, single file
mafia/
  index.html            category page — lists articles
  apalachin-1957.html   article
  valachi-1963.html     article
ww2/
  index.html
  ...
```

Articles are flat files inside their category folder. They never go in
subfolders. This is deliberate: it means subcategories can be added later as
additional listing pages without moving any file or breaking any URL.

Do not create subcategory folders. Do not propose a taxonomy.

File names are lowercase, hyphenated, and end with the anchor year:
`apalachin-1957.html`, `battle-of-britain-1940.html`.

## Navigation

Every page below the homepage carries a back-link to its parent, styled as
`.site-link` and placed at the top of the page above the `h1`.

- Category pages link back to the homepage: `← The Paper Trail`
- Article pages link back to their category: `← Italian-American Mafia`

There is no navigation bar and no breadcrumb trail. The back-link is the
only navigation on the site.

## Category pages

Articles are listed in chronological order by anchor date — earliest at the
top, latest at the bottom. The year is shown next to each title.

The anchor date is the date of the event. For laws, institutions and bodies,
it is the date they came into being.

Articles too broad to place on a timeline go in a short "Background" group
above the chronological list.

A subsection grouping several related articles takes its position in the
chronological list from its earliest article. Within the subsection, the
articles are listed chronologically in the same way.

Where every article in a subsection falls in the same year, the year is
shown once, on the subsection heading, and each article inside it shows
its month instead.

A subsection is marked up as an `<li class="subsection">` in the outer
article list, containing an `h3.subsection-heading` with the year in a
`.year` span, and a nested `<ul class="article-list">` holding the
articles.

Ordering is maintained by hand in the HTML. Do not build sorting logic, do
not store dates as data, do not add JavaScript for this.

## Article pages

Every article has the same five parts:

1. **In brief** — short summary
2. **What happened** — the narrative
3. **Disputed and mythologised** — claims that are contested, unproven or false
4. **Gaps in the record** — what is genuinely unknown
5. **Sources** — numbered list, every entry with a URL or DOI

Claims in the narrative carry inline source markers in the form `[S1]`, `[S2]`,
linking down to the matching source list entry.

Section 3 is the most important part of the site and should be styled as a
substantial component in its own right, not as a footnote or an aside.

Each claim in section 3 carries one tag: **Myth**, **Overstated** or
**Unproven**.

Where a source has no accessible online text, it is still listed with a
complete citation and a note saying that no accessible copy was located.
Where a printed work has no accessible online text, link to a library or
publisher record for the edition rather than leaving the entry unlinked.
An entry stays unlinked only where no such record exists.

In the source list, the link text is the citation only. Access and
provenance notes — a redacted file, an untranslated foreign-language
document, testimony that is retrospective, whose opinion within a case a
citation refers to — sit outside the link, as plain text after it.

## Design direction

This is a site people read, not a portfolio and not a news site. Generous
line height, a comfortable reading measure, restrained colour, quiet
typography. Long-form reading comfort comes before visual interest.

It should not look like the personal site in the `personal-site` repo —
different property, different purpose.

British English throughout, including in the interface.

## How to work with me

I am learning. Building this correctly matters less than my understanding
what was built.

- Explain the structure of what you are about to write before writing it.
- Build only what I asked for in the current message. Do not build ahead.
- When you add something I did not ask for, say so explicitly.
- Keep changes small enough that I can read the whole diff.
- If I ask for something that adds complexity without clear benefit, say so.