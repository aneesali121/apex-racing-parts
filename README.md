# APEX RACING PARTS

A premium motorsport-inspired storefront for performance and racing parts. This is a frontend prototype built as a portfolio project.

## Features
- Responsive layout for desktop, tablet and mobile
- Homepage hero, featured collections (Track Day, Street Performance, Drift) and promo banner
- Catalogue with search, category and brand filters, price range, in-stock toggle and sorting
- Product quick-view with photo, specs, fitment, quantity selector, Buy Now and related parts
- Cart with quantity controls, coupon codes (RACE20, APEX10), shipping rule and totals
- Checkout with validation, Cash on Delivery, and a clearly labelled demo payment option
- Order confirmation, order history and wishlist, all stored in the browser (localStorage)

## Project layout
```
index.html                       # the whole storefront (HTML, CSS, JS, images embedded)
public/images/
  hero/                          # homepage hero
  banners/                       # promo banner
  categories/                    # collection tiles
  products/                      # product photography (WebP)
  accessories/                   # accessory photography (WebP)
  attribution.json               # credit and source for every image
```

The page embeds its images as data URIs so it works as a single file. The `public/images` folder holds the same photos as separate WebP files, ready for a future Next.js build that loads them from the public directory.

## Running locally
Open `index.html` in any modern browser. No build step or server is needed.

## Enabling GitHub Pages (optional)
Settings → Pages → Deploy from a branch → `main` / root. The site will then be served at `https://<your-username>.github.io/apex-racing-parts-repo/`.

## Image licensing: read before making this repository public
- **Product and car photos supplied by the site owner** have no confirmed source or licence. They may be manufacturer or retailer photography, which is usually copyrighted. Do not publish them in a public repository or live site until you have the right to use them commercially, or replace them with licensed photos.
- **Pexels and Unsplash photos** are free to use under their licences, but check the terms for commercial and redistribution use.
- Brand names printed on photos (Brembo, Garrett, ATTC, BRIDE, Volk Racing, Action Clutch, Lumileds, Magnavaloy, KW, HKS, Sparco, Zestino) belong to their owners. The demo disclaimer on the page states there is no affiliation.
- Full per-image attribution is in `public/images/attribution.json`.

**Recommendation:** keep this repository private until the images are cleared.

## Admin dashboard
Open the site with `#admin` added to the address, or use the footer link. The dashboard has four sections in a sidebar:
- **Overview:** order count, revenue, open orders and products; a seven-day sales chart; a "needs attention" list; recent orders.
- **Orders:** search by order, customer or product; filter by status; change status (New, Packed, Shipped, Delivered); print receipts; delete orders; export all orders to CSV.
- **Products:** edit name, brand, price and stock; add new products; hide or permanently delete products.
- **Hidden:** restore products that were hidden from the store.

**Important:** this dashboard has no login. It reads the data saved in the current browser, so it is for demonstration only. A real admin area needs a server, a database and authenticated accounts (see the roadmap).

## Roadmap
- Next.js + TypeScript + Tailwind migration
- PostgreSQL with Prisma (products, categories, brands, orders, reviews, coupons)
- Authentication and user accounts
- Admin dashboard (sales overview, product, inventory and order management)
- Real payment integration

## Known issues
- Carbon Front Splitter has no photo yet and shows an illustration.
- Some fitment and specification text is placeholder content. Verify before any real use.
- The carbon dash trim photo shows a Porsche 911 interior. Check fitment before listing.

## Licence
No licence file yet. Add one (for example MIT) once you have decided, and only after the image licensing above is resolved.

## Repository description (for GitHub's "About" box)
**Description:** Premium motorsport-inspired performance parts storefront. Responsive catalogue, cart, checkout and order history built with HTML, CSS and vanilla JavaScript.

**Website (optional):** the GitHub Pages address, or the live demo link above.

**Topics:** `ecommerce` `automotive` `motorsport` `responsive-design` `javascript` `html-css` `portfolio` `shopping-cart` `frontend` `nextjs-ready`

## File guide
| Path | What it is |
|---|---|
| `index.html` | Complete storefront: styles, markup and script, with product photos embedded. Commented by section. |
| `public/images/README.md` | Explains what each image folder is for. |
| `public/images/attribution.json` | Source and credit note for every image file, keyed by path. |
| `public/images/hero/hero-race-cars.webp` | Homepage hero photograph (2000px wide). |
| `public/images/banners/promo-red-sports-car.webp` | Promotional banner photograph. |
| `public/images/categories/collection-track-day.webp` | Track Day collection tile. |
| `public/images/categories/collection-street.webp` | Street Performance collection tile. |
| `public/images/categories/collection-drift.webp` | Drift collection tile. |
| `public/images/products/*.webp` | One WebP photograph per product, named `brand-or-type-product.webp`. |
| `public/images/accessories/bucket-seat-and-steering-accessories.webp` | Seat and steering accessories photograph. |
| `tests/` | Automated checks for the storefront and admin (`npm test`). |
| `docs/` | Architecture and data documentation. |
| `CHANGELOG.md`, `CONTRIBUTING.md` | Version history and contribution guide. |
| `package.json`, `.editorconfig` | Project scripts and editor settings. |
| `.github/workflows/ci.yml` | Continuous integration: installs and runs the tests. |
| `README.md` | This file. |
| `.gitignore` | Files Git should not track (dependencies, build output, secrets). |


## Testing
```
npm install
npm test
```
The tests (`tests/`) run the page in a headless DOM and check the storefront and the admin dashboard. CI runs them on every push and pull request (`.github/workflows/ci.yml`).

## Documentation
- `docs/ARCHITECTURE.md`: how the single-file app is organised and the planned production stack.
- `docs/DATA.md`: every browser storage key and the order format.
- `CHANGELOG.md`: what changed in each version.
- `CONTRIBUTING.md`: how to make and test a change.

## Naming conventions
- Image files: lowercase, hyphen-separated, brand or product type first, e.g. `brembo-track-brake-pads.webp`.
- Folders follow the image types in the project spec: `hero`, `products`, `categories`, `banners`, `accessories`.
- Product names in the page match the product entries in the script (`RAW` table).
