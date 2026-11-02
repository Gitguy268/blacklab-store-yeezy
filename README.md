# Blacklabspots storefront

A separate, buildless storefront inspired by Yeezy’s minimal product grid. Includes all 35 products observed on blacklabspotsshop.me on 22 October 2026.

<!-- run-steps:start -->
## Run it locally, step by step

1. **Get the code:**

   ```sh
   git clone https://github.com/Gitguy268/blacklab-store-yeezy.git
   cd blacklab-store-yeezy
   ```

2. **Start a local web server** on the `dist` folder (Python 3 comes with macOS and most Linux systems):

   ```sh
   python3 -m http.server 8000 --directory dist
   ```

3. **Open <http://localhost:8000/>** in your browser. Press `Ctrl+C` in the terminal to stop.
<!-- run-steps:end -->

## Run

Serve `dist/` using any static web server, for example `python3 -m http.server 4173 --directory dist`. Open http://localhost:4173.

## Edit

- `dist/products.json`: product names, displayed prices, category, image URL and original purchase URL.
- `dist/style.css`: layout, typography and responsive styles.
- `dist/app.js`: category filtering, search and product dialogs.

Product imagery is bundled locally from the original Printify product pages. Catalog and prices are a snapshot, not live inventory. Product options, personalization, availability and payments remain on the original store. No local cart or payment processing is implied. No tracking or subscription backend is included.

## Reference and REA limitations

REA (morluto/rea, official rea-agents npm package) was used with an isolated Chromium browser to list the Yeezy target and inspect its page. That browser received a Cloudflare block, so REA did not decompile or recover the storefront application. The in-app browser rendered the public storefront successfully: white canvas, monospace labels, three-column desktop product grid, sparse header and overlays. Public DOM link metadata identified SvelteKit modules, but direct asset downloads also returned HTTP 403.

This project is an independent implementation of those visible design patterns, using Blacklabspots products. It does not contain Yeezy’s source, imagery, branding or backend. Product codes are new display identifiers added for this project.

## Hosting

Deploy the contents of `dist/` to any static host. `.openai/hosting.json` identifies the private Sites preview. The existing blacklabspotsshop.me site has not been changed.
