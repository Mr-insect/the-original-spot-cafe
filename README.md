# The Original SPOT Cafe — Next.js website

Next.js (App Router) + TypeScript + Tailwind setup. Supabase abhi nahi jodi hai.

## Chalane ka tarika
```bash
npm install
npm run dev      # http://localhost:3000
npm run build    # production build check
```

## Sab kuch kahan badalna hai
Sirf **`lib/config.ts`** kholo:

| Kya badalna hai | Kahan |
|---|---|
| Phone, address, Instagram | `SITE` |
| **Opening hours** | `SITE.hours` (format file ke comment mein) |
| Google Maps pin | `SITE.lat`, `SITE.lng`, `SITE.mapsLink` (abhi tumhara pin laga hai) |
| Menu items aur **prices** | `MENU` (`p: null` = price nahi dikhega) |
| Hero mouse-trail photos | `HERO_TRAIL` (on/off), `TRAIL_IMAGES` → `public/trail/t1.jpg … t10.jpg` |
| Purana 3D girta khana wapas | `HERO_3D = true` |
| Signature Dishes hover | `SHOWCASE` |
| Offers, Gallery | `OFFERS`, `GALLERY` |

## Photos lagana
1. Photos `public/photos/` (menu, gallery) aur `public/trail/` (hero) mein rakho. Pehle chhota/compress kar lo.
2. `lib/config.ts` mein path likho, jaise `img: "/photos/pizza.jpg"`.

## Structure
- `app/` — layout, page, global styles
- `components/` — Navbar, Hero (mouse trail), Showcase (hover effect), Menu, CartProvider/CartDrawer, Sections (Offers, Gallery, Party, Contact, Footer)
- Order aur party booking dono WhatsApp par jaate hain (`SITE.whatsapp`).

## Naye changes
- Hero: purana **mouse-trail** theme wapas (mouse chalao → khane ki photos peeche aati hain).
- **Real WhatsApp / Instagram logos** (`components/Social.tsx`) + **physics effect** (mouse se door bhaagte, takraate, spring se wapas; pakad ke phenk bhi sakte ho). Sirf in do icons par hai: floating kone wale buttons aur footer ke upar "Stay Connected" glass panel.
- "What's new at the SPOT": transparent **glass cards** (blur, mouse-spotlight, shine, photo bleed).
- Signature Dishes slider, Menu, Gallery, About — sab mein photos.

## Photos badalna (zaroori padhna)
`public/photos/` aur `public/trail/` ki photos abhi **temporary rendered images** hain (AI/photo-shoot nahi).
Real photos laane ke liye **same naam** se replace kar do — code nahi badalna. Naam aur AI-prompts `PHOTOS.md` mein hain.
