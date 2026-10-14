# AI Engineering Playbook — Full Blurred Image Preview

This static GitHub Pages site does **not** include the original PDF.

## Pages
- Page 1 is rendered as a clear image.
- Page 2 is permanently blurred in its image pixels and displays the newsletter embed.
- Pages 3–32 are included as permanently blurred images for a visually complete reader and sidebar.
- All pages after page 1 are blurred before upload; CSS is not used to conceal readable source pages.
- Original PDF file is excluded from this package.

## Run locally
Run a local server in this folder:
```bash
python -m http.server 8000
```
Open `http://localhost:8000`.

## Publish on GitHub Pages
Upload `index.html`, `style.css`, `app.js`, `README.md`, and the entire `pages/` folder to your repository root. Do **not** upload the original PDF. In GitHub, go to Settings → Pages → Deploy from a branch → `main` → `/ (root)` → Save.

## Popup design
The second-page card uses the earlier warm cream popup styling with an envelope icon and “KEEP READING” label, while preserving the requested headline and newsletter iframe.

## Security limitation
The original PDF is not in this repository, so visitors cannot download it directly from this site. Page 1 and the blurred images are public and can be saved, but pages 2–32 are already blurred in the image files. Screenshots of the visible cover can still be taken.


## Floating newsletter popup
The newsletter form is now a fixed modal overlay rather than being placed on page 2. It first appears after the visitor scrolls beyond the first page. Closing it animates the modal away; after another approximately two-page scroll distance, it can appear again. The popup uses the requested System Design newsletter iframe.


Popup repeat behavior: after the visitor closes the fixed popup, the next popup appears after scrolling another two page-heights. This repeats throughout the blurred pages.


Popup trigger direction: after closing the popup, it can reappear after scrolling approximately two page-heights either down or up. The popup stays fixed at the center of the viewport, not on a document page.


Background scrolling: the main viewer and thumbnail sidebar remain scrollable while the fixed newsletter popup is open. The popup itself stays fixed over the main viewing area.
