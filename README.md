# King J's Taxi Services & Tours — website

Static site. No build step. Open `index.html` to preview, or drag the folder onto Netlify
Drop / Cloudflare Pages / GitHub Pages to publish.

```
index.html      Overview — video slider, stats, quick book, filterable grid, island map,
                taxi, drivers, Instagram grid, reviews, booking
tours.html      The four tours in full
contact.html    Booking form + FAQ
assets/css/style.css
assets/js/main.js
assets/img/     Logo files + placeholder imagery
assets/video/   generated fallback loop (mp4 + webm)
```

Colours are sampled from the logo: cyan `#0FC1DD` → teal `#50C9B8` → green `#86CE9E`
→ lime `#B4D481` → yellow `#FBDF5A`, on black. Backgrounds stay white.

---

## 1. Media — what's real, what's stock, what's still placeholder

### The hero video

One video runs behind all three slides; the slides only change the text. The `<video>`
tries sources in order and plays the first that loads:

1. `assets/video/rainforest.mp4` — **your own footage.** Not shipped. Drop a file here
   and it wins automatically.
2. A real rainforest waterfall clip from **Pexels** (free for commercial use, no credit
   required): https://www.pexels.com/video/lush-jungle-waterfall-in-tropical-rainforest-33720041/
   Loaded from Pexels' servers. **Download it** ("Free download" on that page), save as
   `assets/video/rainforest.mp4`, and it becomes source 1 — so the site no longer depends
   on Pexels keeping the file where it is. It's Indonesian rainforest, not Grenadian. A
   ten-second phone clip at Annandale or Grand Etang would be better.
3. `rainforest-placeholder.mp4` / `.webm` — a generated loop, only if both above fail.

### Placeholder photos

Every picture frame is filled. They're real photographs of **Grenada** from Pexels (free
licence) — St. George's harbour, the bay from the air, Grand Anse, fishing boats, sunsets
— loaded from Pexels' image server, with a generated silhouette scene as a local fallback
if that ever fails. Photographers, for the record: G-Isle, Kenrick Baksh, 42 North,
Tanishq Patil. Attribution isn't required under the Pexels licence, but it's decent.

They are stand-ins. None of them show the van, the drivers, or a tour in progress.
**Replace by filename** — overwrite the local file and delete the Pexels URL from the
`src` attribute (the `onerror` fallback already points at the local name):

| Filename | Where |
|---|---|
| `card-chocolate` `card-island` `card-falls` `card-airport` `card-taxi` `card-events` | Services grid (1200×750) |
| `tour-chocolate` `tour-island` `tour-falls` `tour-custom` | Tours page (1200×900) |
| `ig-1` … `ig-6` | "Lately, on the road" grid (900×900) |
| `driver-joel` `driver-deshon` `driver-jahvon` | Drivers — currently initials tiles (1200×800) |

### Instagram and Tripadvisor

**Instagram cannot be read automatically**, so the "Lately, on the road" grid uses stock
Grenada photos for now. Save six squares from @kingjtours as `ig-1.jpg` … `ig-6.jpg` and
they replace the stock.

Two photos on the Tripadvisor listing were uploaded by the business itself (the van, and
a guide on tour). They're no longer hotlinked — Joel will have the originals on his phone.
Good candidates for `card-taxi.jpg` and `driver-joel.jpg`. The other photos on the listing
were uploaded by reviewers and shouldn't be reused without asking them.

## 2. Contact details

Phone from the logo is live everywhere: **+1 (473) 419 8788**, and `14734198788` for the
WhatsApp handoff. **Still placeholder:** `bookings@example.com`, marked `<!-- TODO -->` in
the contact panel and footer. Swap it or delete those lines.

## 3. The map

The outline is Grenada's actual coastline (Natural Earth 1:10m geometry), stroked with the
logo gradient. Nine stops plotted at true coordinates.

## 4. Content sources and things to check

From the public Tripadvisor listing and the GetYourGuide supplier page. Before launch:

- "4.9 from 65 travellers" and "#4 of 57" are hard-coded and will drift.
- Only the rum/chocolate/waterfall tour has a published price.
- Review quotes are short attributed excerpts.
- Deshon and Jahvon are named publicly based on reviews. They should agree, and confirm
  spellings.

## 5. Before launch

- [ ] Pexels clip downloaded and saved locally, or own footage in its place
- [ ] Stock photos swapped for real ones — van, drivers, tours
- [ ] Six Instagram photos saved as `ig-1.jpg` … `ig-6.jpg`
- [ ] Real email in place
- [ ] Prices confirmed; driver names approved
- [ ] Domain, hosting, Google Business Profile
