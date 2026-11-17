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

MYSTERY CARDS (v18): after the lid opens, black "?" cards come out of the box one behind the other; tap the front one to reveal the gift, it flies back into the box and the next moves up. The book is last and takes you inside.

GIFT CARDS FLY OUT OF THE BOX (v16)
  Tapping a gift (inside the box, or the corner box later) makes the card fly out of the box as a 3D card
  that follows your finger/mouse. Closing it sends the card spinning back into the box.

SCRATCH CARDS (v19)
  The gifts come out of the box as black cards. Scratch the front card with your finger / mouse. When it is revealed the card spins for 3s while its text is typed, holds still for 2s, then flies into the box by itself (no Next button).
  After the last gift the book appears by itself and takes you inside. Only gifts that have a card photo are in CONFIG.gifts.

CARD REVEAL ANIMATION (v21)
  After scratching: the card does one fast 3D flip while growing (~0.65s), the background dims, the text types in ~0.8s,
  then the card shrinks back into the box spinning (0.65s). Total on screen ~2.3s (was ~5.8s).
  To tune: in index.html search "v20: quick 3D flip" -> FL (flip ms), TOT (total ms before it flies back), the scale cap 1.32, dim opacity.

BOOK v22: richer leather cover, gold-foil name, striped spine, faster book sequence (~4.5s instead of ~8s). Look: <style id="v22">; timing: newOpen() in the 5th script.

PAGE 02 GLOW-UP (v27)
  - Captions: each photo has a title (.ct) + a short personal line (.sub). Edit them in the page 02 <figcaption>s.
  - Want dates/places? Add them inside the .sub text, e.g. "Nice · Nov 2026 - The whole sky showed off."
  - "Make a wish" lines: search for var W=[ in the last <script> of index.html.
  - Warm colour grade for page 02 photos: --grade in the v27 CSS block.

v30: corner gift box turns see-through (opacity .3) when it overlaps content (style/script id v30). Gift codes in CONFIG.gifts are TEST codes - replace before sending. Pages numbered 01-08.

v32
  - SKIP button (top right of the intro): jumps straight to the page, the corner box lands and the music starts. Works at any moment of the intro.
  - MY GIFTS page: tap the small open box in the bottom-left corner. It lists every gift (card photo, title, note, code + Copy, and an Open button if CONFIG.gifts[i].url is set). Tap a card photo to see it big. The badge on the box = number of gifts.

v33
  - REDEEM button on every gift card (My gifts page). Opens a sheet with: the big code + Copy, "How to use it" steps, an optional expiry line, and an "Open the store" button if CONFIG.gifts[i].url is set.
    Optional per-gift fields: steps:["...","..."]  expires:"30 Jun 2027"
  - THE BIG ONE: her birthday night, shown at the top of My gifts as a locked card with a live countdown to CONFIG.date. Before that date, tapping Redeem just shakes.
    From the date on, it opens the full program (timeline) + map + add-to-calendar. Edit it in CONFIG.main (title, note, program[]). The program in the file is SAMPLE text: replace it with the real plan.
    Optional: CONFIG.main.opens:"2027-04-25T19:00:00" to unlock at a different moment than the party time.
    To preview the opened state yourself, add ?unlock to the link (e.g. .../index.html?unlock).
