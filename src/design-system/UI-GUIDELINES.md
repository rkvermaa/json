# UI guidelines — JSON for Modern C++

These rules describe how this product's screens look and behave. They were derived from the existing documentation site (`docs/mkdocs`) and its `brand.css`; they do not change it.

## Navigation

- The main navigation has exactly five sections, in this order: **Home** (`data-nav-key="home"`), **Features** (`features`), **Integration** (`integration`), **API Documentation** (`api`), **Community** (`community`) — because they mirror the site's top-level tabs, and readers already know that order.
- The navigation sits in the blue header band (`--md-primary-fg-color`) as a row of text links; it collapses behind the menu button below the tablet width — because every screen keeps the same single band and the content gets the full width on phones.
- Mark the current section with `aria-current="page"` on its link only; never mark more than one — the shell draws the marker (an underline on wide screens, a left bar in the collapsed list).
- Do not add account, saved or cart links — the product has no sign-in or purchase flow.
- Search is a field in the header, not a destination in the navigation — readers search from any page and the result replaces the page they are on.
- Deeper structure (a section's pages, a page's table of contents) belongs in the screen's content, never in the shell — because the shell must stay identical on every screen.
- The GitHub repository link (`nlohmann/json`) lives in the header (wide screens) and the footer, as an external link — it leaves the documentation.
- The footer carries the repository, releases, FAQ and contribution links plus the copyright line; do not put actions in it — it is reference material only.

## Layout and density

- Content sits in `.container` (up to 72rem wide) inside the shell's single column; use `.grid` for card overviews — because documentation reads best in one wide column that wraps to fewer columns on its own.
- Density is documentation-dense: 17 px body text, `--md-typeset-color` on the page surface, headings bold with tight negative tracking — because readers scan reference material and expect long pages.
- Group blocks with `.stack` (vertical) and `.cluster` (rows of buttons, badges, chips); do not invent margins — because one rhythm keeps pages consistent.
- Keep one primary action per view or dialog; everything else is `.btn-secondary` or `.btn-ghost` — because the primary button is the one place the solid brand blue appears.
- Corners are small (about 6 px on blocks, 4 px on inline elements) and borders are one hairline; avoid heavy shadows except on floating layers (`.dropdown-menu`, `.modal`, `.drawer`) — because the brand is flat and technical.

## Components — which class for which job

- Tabular reference data (parameters, return values, versions): `.table` inside `.table-wrap` — because wide tables must scroll sideways instead of breaking the page; numbers stay on one line.
- Code samples: `.code-block` with the syntax classes `.k .t .f .s .n .p .c` — they map to the `--nj-hl-*` tokens, so code reads the same as in the existing docs; inline code uses the code font only, without a box.
- Overview entries that link to a section: `.card` with `.card-interactive` — the blue border on hover is the site's established hover cue.
- Callouts inside a page (notes, caveats, removed or deprecated features): `.alert-info`, `.alert-warning`, `.alert-danger` — they keep the 3 px left border and soft fill of the site's admonitions; `.alert-success` confirms a result.
- Library or feature status (stable, deprecated, since version): `.badge-neutral`, `.badge-success`, `.badge-warning`, `.badge-danger` — a badge labels, it never acts.
- Filters and version or topic selectors: `.chip` with `aria-pressed`, or `.dropdown` with a checked `.dropdown-item` for a single choice such as the C++ standard or release — because a long list should not occupy the page.
- Switching between equivalent views of the same content (for example CMake / package manager / single header): `.tabs` and `.tab` — because the site already uses synced content tabs for installation variants.
- Optional detail (FAQ answers, long explanations): `.accordion` with `.disclosure` — because FAQ pages are long and most answers are not read.
- Forms (search refinement, feedback, filters): `.field` with `.input`, `.textarea`, `.select`, `.checkbox`, `.radio`, `.switch`; show the problem in `.field-error` and set `.is-invalid` — the error text is in `--nj-string`, never colour alone.
- Confirmations of a destructive step: `.modal` with `.backdrop` and a `.btn-danger` — only for steps that cannot be undone.
- Secondary detail beside a list (a release's changes, an item's properties): `.drawer` from the right — so the reader keeps the list in view.
- Short outcomes ("Copied"): `.toast`; hover explanations of an icon-only control: `.tooltip` — never put the only copy of important information in either.
- Loading and empty states: `.skeleton` for content that will take the page's shape, `.spinner` for a short action, `.empty-state` for a search or list with no result — and say what to do next.

## Theme

- Ship both colour schemes — light (`default`) and dark (`slate`) — following the reader's system preference, as the site does; every screen must work in both.
- Colour comes only from the tokens, never literal values — the schemes swap the token values, so components adapt without changes.
- Brand blue (`--nj-blue`) is the one action and link colour; red (`--nj-red`, with `--nj-red-soft`) means danger or removal only; green and orange (`--nj-hl-string`, `--nj-hl-number`) mark success and warning — because red is rare and must stay meaningful.
- Solid fills carry the page surface colour as text (white in light, near-black in dark), as `.btn-primary` does — keep that when composing new fills.
- Typography is Inter for text and JetBrains Mono for code, identifiers and version numbers (`--md-text-font`, `--md-code-font`) — the library's API names are the product's vocabulary and must always be recognisable.

## Voice and tone

- Write for C++ developers: precise, plain and short — they come to answer a specific question.
- Use sentence case for headings, buttons and labels ("API documentation" in prose; the navigation label stays **API Documentation** as in the site).
- Name things exactly as the API does, in the code font (`basic_json`, `json_view`); do not paraphrase identifiers.
- Buttons are verbs ("Copy", "Download"); errors say what is wrong and how to fix it, without blame or exclamation marks.
- Prefer a short example over a long explanation; link onward ("See also") instead of repeating.
