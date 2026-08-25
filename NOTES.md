# Notes — requirements mapping and technical detail

## Project 1 — Bootstrap & Grid System (Restaurant)

`restaurant/index.html` + `restaurant/styles.css`

| Requirement | Where it is |
|---|---|
| Navbar: name left, links right (Home, Menu, About Us, Contact) | `.site-nav` — brand left, `.navbar-nav.ms-auto` pushes links right |
| Hero with image background, centered heading + button | `.hero` — background image with gradient overlay, centered content |
| Menu grid: 3+ items with image, title, description, price | `row row-cols-1 row-cols-md-2 row-cols-lg-3` — **6 dishes**, each a card with image, title, description and price badge |
| About Us: two-column layout, image one side, paragraph other | `row align-items-center gx-4 gy-5` with two `col-12 col-md-6` |
| Contact section with form (name, email, message, submit) | `#contact` — Bootstrap form controls inside a card |
| Footer with copyright + social icons | `.site-footer` — copyright left, four Bootstrap Icons right |

## Project 2 — Bootstrap Components (Travel Agency)

`travel-agency/index.html` + `travel-agency/styles.css`

| Requirement | Where it is |
|---|---|
| Navbar: agency name/logo left, links right (Home, Destinations, Tours, Contact) | `.site-nav` — logo mark + brand left, links `ms-auto` right |
| Hero with background image, heading, subheading, CTA button | `.hero` (jumbotron-style) — scenic background, heading, subheading, "Start exploring" CTA |
| Destinations: grid of 3+ cards with image, title, description, "Learn More" | `row row-cols-1 row-cols-md-2 row-cols-lg-3` — **6 destination cards**, each with image, title, description, price and a Learn More button |
| Tours: accordion with title, description, "View Details" link | `.accordion#toursAccordion` — 4 tour packages, each with badge, description, includes list and View Details link |
| Contact form: name, email, destination of interest, message | `#contact` — inputs, `form-select` for destination, textarea, checkbox, submit |
| Footer with copyright + social icons | `.site-footer` |

## Technical notes

- **Bootstrap 5.3.3** and **Bootstrap Icons 1.11.3** via CDN; `bootstrap.bundle.min.js`
  powers the navbar toggler and the accordion.
- **Grid classes used:** `container`, `row`, `col-12`, `col-md-4`, `col-md-6`, `col-lg-5`,
  `col-lg-7`, `col-lg-9`, `row-cols-md-2`, `row-cols-lg-3`, gutters `g-3`/`g-4`/`gx-4 gy-5`.
- **Custom theming:** each project has its own `styles.css` overriding Bootstrap variables
  and components — warm gold + Playfair Display for the restaurant, ocean teal + coral and
  Poppins for the travel agency.
- **Responsiveness tested** at 390px, 768px and 1360px: no horizontal overflow at any
  width, navbar collapses to a hamburger under `lg`, and all multi-column grids stack to a
  single column on mobile.

> Note on gutters: `g-5` on a row inside `.container` overflows the viewport by 12px on
> small screens (the row's negative margin is larger than the container's padding), so the
> two-column sections use `gx-4 gy-5` — same vertical spacing, no horizontal overflow.
