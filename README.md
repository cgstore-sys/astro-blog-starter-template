# Auto-Loading Multi-Brand Gallery

A photo gallery that automatically shows every image in every brand folder, with filter buttons for each brand.

## How it works

Every subfolder inside `public/images/` is treated as a brand. The gallery auto-discovers all brand folders at build time, loads their photos, and creates a filter button for each — **no code editing needed to add a brand**.

## Labels

- **Main photos** (`brand1.jpg`, `brand2.jpg`, ...) show a caption at the bottom: **BrandName 1**, **BrandName 2**, ...
- **Detail photos** (`brand1.1.jpg`, `brand1.2.jpg`, ...) show **no caption**.

The rule is simple: if the file number has a decimal point, it's a detail shot and gets no label. Otherwise it's a main photo and gets labeled.

## Folder layout

```
astro-blog-starter-template/
├── public/
│   └── images/
│       ├── LV/          ← LV photos (lv1.jpg, lv1.1.jpg, lv2.jpg, ...)
│       ├── Gucci/       ← Gucci photos (gucci1.jpg, gucci1.1.jpg, gucci2.jpg, ...)
│       └── Chanel/      ← Chanel photos (chanel1.jpg, chanel1.1.jpg, ...)
├── src/
│   └── pages/
│       └── index.astro  ← the gallery page (auto-loads all brands)
```

## To add photos to an existing brand

1. Drop the new JPGs into the brand's folder (e.g. `public/images/LV/`)
2. Push to GitHub — the site rebuilds and shows them automatically

## To add a NEW brand

1. Create a folder in `public/images/` named after the brand
   (e.g. `public/images/Gucci/` — **the folder name becomes the button label**)
2. Drop that brand's photos in it, numbered like `gucci1.jpg`, `gucci1.1.jpg`, `gucci2.jpg`, ...
3. Push to GitHub — the site rebuilds and the new brand button appears automatically

That's it. No need to edit any code.

## Photo order

Photos appear in natural order within each brand: `brand1.jpg`, `brand1.1.jpg`, `brand1.2.jpg`, `brand2.jpg`, ... `brand10.jpg`. No sorting needed on your end.

## Tips

- Supported formats: `.jpg`, `.jpeg`, `.png`, `.webp`, `.gif`
- The folder name is used as-is for the button label, so name it how you want it displayed (e.g. `Gucci`, not `gucci`)
- Resize very large photos to ~2000px wide before uploading so pages load fast
