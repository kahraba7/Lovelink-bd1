Malak's Birthday Website
========================
Open index.html in a browser to preview (needs internet only for the Google Fonts).
All files are in one flat folder: index.html + the photos (cover.jpg, moment-1.jpg ...).

EDITING
  1) Names, date, place, map link: edit the CONFIG block at the bottom of index.html.
  2) Your letter: search for "Your message goes here" in index.html and replace the text.
  3) Photo captions: edit the <figcaption> and <p> texts next to each image.
  4) Swap a photo: replace the file with another one using the same name.
  5) Video: find data-slot="video-1" and replace that <div class="ph" ...>...</div> with:
       <video class="fill" src="video.mp4" controls playsinline poster="cover.jpg"></video>
     then put video.mp4 in the same folder as index.html.

PUBLISHING (free)
  - Netlify Drop (app.netlify.com/drop): drag the whole folder in, you get a link.
  - Or GitHub Pages / Cloudflare Pages.

3D GIFT BOX (intro)
  The opening box is a 3D model drawn with plain WebGL (no libraries, embedded in index.html).
  Model: "Gift Box" by Elias (https://sketchfab.com/elias.voet), CC BY 4.0
  https://sketchfab.com/3d-models/gift-box-eb72144b83bf43d98ec1d4fcd979660a
  Changes: split into lid + body so the lid can open. Credit is shown in the page footer - please keep it.
  Size: change --bw in the "v12" CSS block (clamp(170px,54vw,230px)).

INTRO BACKDROP + TURNING THE BOX (v14)
  The photo collage behind the gift is built from the PH list in the last <script> of index.html.
  Drag / swipe left-right (or use the arrow keys) to turn the box; tap without dragging opens it.

OPENING + "PICK YOUR SURPRISE" (v15)
  After the tap: bow lifts, lid opens, photos shoot out of the box (PH2 list in the 5th <script>), camera dives in.
  Inside: the book (tap = open the story) and the gift cards (tap = peek). Gifts are set in CONFIG.gifts.
