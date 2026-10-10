# IOW Takeover 2027 photos

Drop photos from the 2027 Takeover in this folder.

## Adding a photo to the gallery

1. Resize it first so the page stays fast (about 1600px on the longest side, under 500KB).
   On a Mac you can use Preview > Tools > Adjust Size, or with ImageMagick:
   ```bash
   magick input.jpg -auto-orient -resize 1600x1600 -quality 80 iow2027-1.jpg
   ```
2. Save it here with a simple name, no spaces: `iow2027-1.jpg`, `iow2027-2.jpg`, ...
3. Open `index.html`, find the `PHOTOS` list near the bottom (in the SITE CONFIG block)
   and add a line for it:
   ```js
   { src: 'images/iow-2027/iow2027-1.jpg', alt: 'Short description of the photo' },
   ```
   Photos show in the order they're listed, so put your favourites first.

## Changing the hero (top of page) photo

Replace the `src` in the `<div class="hero-bg">` image near the top of `index.html`.
A landscape photo with the cars in the middle works best. Also update the
`og:image` and `twitter:image` tags in the `<head>` so link previews use it.

Older photos live in `images/iow-2025/`.
