# Stillflow — Design System

Extracted from the Stillflow marketing site. Values are given twice where scale matters: **Web** (as built) and **Slide** (1920×1080 deck usage).

---

## 1. Brand character

Quiet, editorial, engineered. Ultra-light large type against a warm off-white ground, with one deep green as the only saturated color. Photography and video carry all the visual energy; the UI recedes. No gradients, no accent borders, no emoji, no icon soup.

Rules of thumb:
- One idea per surface. Generous whitespace is the design.
- Headlines are light weight and tightly tracked; body copy is plain and unstyled.
- Green is for action and emphasis only — never a background wash for text-heavy areas.
- Corners are soft (16–24px on web; 24–32px on slides). Shadows are rare and very diffuse.

---

## 2. Color

| Token | Hex | Use |
|---|---|---|
| Canvas | `#F5F5F5` | Primary page / slide background |
| Canvas Warm | `#EAEAE6` | Media placeholder fill, secondary panel |
| Panel | `#ECECE9` | Comparison table shell, inset groups |
| Card Warm | `#E6E6E1` | Image card base color |
| Surface White | `#FFFFFF` | Form cards, elevated panels |
| **Deep Green** | `#0E3B38` | Primary buttons, footer, dark sections, links |
| Green Text | `#F5F6F4` | Type on Deep Green |
| Ink | `#000000` | Headlines, primary text |
| Ink Muted | `#374151` | Nav links, secondary UI text |
| Near Black | `#050608` | Full-bleed dark image sections |

Opacity ramp on light backgrounds (use instead of grey hexes):
- `rgba(0,0,0,0.70)` — lead paragraph
- `rgba(0,0,0,0.60)` — body copy
- `rgba(0,0,0,0.55)` — supporting / list copy
- `rgba(0,0,0,0.50)` — captions
- `rgba(0,0,0,0.45)` — eyebrow labels
- `rgba(0,0,0,0.08)` — hairline rules

On Deep Green: `#F5F6F4` for type, `rgba(245,246,244,0.55)` for secondary, `rgba(245,246,244,0.15)` for rules.
On imagery: `#fff` for type, `rgba(255,255,255,0.80)` for body.

Max two background colors per deck: **Canvas** plus **Deep Green** (or a full-bleed image).

---

## 3. Typography

**Typeface:** TT Norms Pro. Fallback stack: `'TT Norms Pro', 'Helvetica Neue', Helvetica, Arial, sans-serif`.

Weights in use: **200** (all display type), **400** (body), **500** (nav, buttons, labels), **600** (eyebrows).

Two hard rules: display type is always weight 200 with negative tracking; body type is always weight 400 with no tracking.

### Web scale

| Role | Size | Weight | Line height | Tracking |
|---|---|---|---|---|
| Hero H1 | 60px | 200 | 1.08 | −0.04em |
| Section H2 | 48px | 200 | 1.15 | −0.03em |
| Card H3 | 32px | 200 | 1.30 | −0.02em |
| Footer statement | 36px | 200 | 1.30 | −0.01em |
| Wordmark | 24px | 200 | — | −0.03em |
| Lead paragraph | 24px | 400 | 1.50 | — |
| Body | 16–18px | 400 | 1.60 | — |
| Small / caption | 15px | 400 | 1.55 | — |
| Eyebrow | 13px | 600 | — | 0.12em, uppercase |
| Nav / button | 15–18px | 500 | — | — |

Fluid pattern used throughout: `clamp(min, vw, max)` — e.g. H1 `clamp(34px,7.6vw,60px)`, H2 `clamp(30px,5.6vw,48px)`.

### Slide scale (1920×1080)

Roughly 2.2× the web scale. Never below 24px.

| Role | Size | Weight | Line height | Tracking |
|---|---|---|---|---|
| Cover title | 132px | 200 | 1.02 | −0.045em |
| Section divider | 108px | 200 | 1.05 | −0.04em |
| Slide title | 84px | 200 | 1.10 | −0.03em |
| Subhead | 48px | 200 | 1.25 | −0.02em |
| Lead paragraph | 40px | 400 | 1.45 | — |
| Body | 32px | 400 | 1.55 | — |
| Caption / label | 26px | 400 | 1.50 | — |
| Eyebrow | 24px | 600 | — | 0.14em, uppercase |
| Big stat | 200px | 200 | 0.95 | −0.05em |

---

## 4. Spacing & layout

Scale: **4 / 8 / 12 / 16 / 20 / 24 / 32 / 40 / 48 / 64 / 80 / 96 / 120**.

**Web**
- Content max width `88rem`; text columns `24–40rem`.
- Section padding `96px 24px`, fluid to `56px 16px`.
- Grid gap `32–48px`; card gap `16px`.
- Nav: sticky, `20px 24px`, 1px bottom hairline at `rgba(0,0,0,0.08)`.

**Slide (1920×1080)**
- Outer margin `120px` left/right, `96px` top/bottom. Never place type outside this.
- 12-column grid, `48px` gutters. Common splits: 6/6, 5/7, 7/5, 4/8.
- Baseline rhythm: `48px` between title and body, `32px` between body blocks, `80px` between stacked content groups.
- Full-bleed media: edge to edge, type inset `96px` from the media edge.

---

## 5. Radius, elevation, motion

- Radius: media & cards `16px` (web) / `32px` (slide); large panels `24px` / `40px`; pills `9999px`.
- Elevation: only one shadow in the system — `0 24px 60px rgba(0,0,0,0.06)` on white form cards. Everything else is flat.
- Hairline: `1px solid rgba(0,0,0,0.08)` light, `rgba(245,246,244,0.15)` on green.
- Transitions: `200ms` for color/hover, `600ms` ease-out for reveals.
- Entrance: fade + `translateY(8px)` up. On slides, stagger children by `80ms`.
- Blur: `backdrop-filter: blur(28–50px)` with a linear or radial mask, used to soften one edge of a video/photo so light type stays legible. Signature move — use sparingly.

---

## 6. Components

**Primary button** — Deep Green `#0E3B38`, white text, weight 500, pill radius, `12px 52px` padding, with a white circular arrow chip that slides left→right on hover.
Slide equivalent: `24px 96px` padding, `32px` text, `40px` arrow chip.

**Inverse button** — White fill, `#0E3B38` text, green arrow chip. Used on green or dark imagery.

**Text link** — `#0E3B38`, underlined, weight 500, 14px (web) / 26px (slide).

**Eyebrow label** — 13px/24px, weight 600, `0.12em` uppercase tracking, `rgba(0,0,0,0.45)`. Sits `20px` above the headline. One per surface.

**Image card** — Rounded rect, photo or `#E6E6E1` fill, `28px` padding, H3 top-left, supporting copy pinned bottom via `justify-content: space-between`. Type is white over imagery.

**Stat panel** — Deep Green fill, big number in weight 200, label in `rgba(245,246,244,0.55)` caption size.

**Comparison table** — `#ECECE9` shell, `24px` radius, `8px` inner padding, columns as separate cells with `8px` gaps. First column is 1.3× the others. Horizontally scrollable below 660px on web; on slides cap at 4 columns.

**Accordion / list row** — `24px 0` padding, hairline divider, 20px/40px weight-500 label, chevron or plus at the right edge.

**Form field** — White fill, hairline border, `12px` radius, label in caption size above at `rgba(0,0,0,0.55)`. Cards centered at `48rem` max width.

**Oversized wordmark** — "Stillflow" at `21vw`, weight 200, `-0.05em`, `line-height: 0.82`, bleeding off the bottom edge of a Deep Green footer. Deliberate clipping. Slide equivalent: closing slide with the wordmark at ~`420px`, cropped by the bottom edge.

---

## 7. Slide layout library

Use these seven and vary the order; don't invent a new layout per slide.

1. **Cover** — Full-bleed video/photo, blur-masked left edge, cover title + one line of body bottom-left inside the `120px` margin, primary button below.
2. **Section divider** — Deep Green field, divider title centered or bottom-left, eyebrow above. No other content.
3. **Statement** — Canvas ground, one sentence at subhead size, max 20 words, centered with `40rem`-equivalent measure. Nothing else on the slide.
4. **Split** — Title + body in the left 5 columns, one rounded image or panel filling the right 7. Reverse on alternate slides.
5. **Card row** — Title across the top, 2–3 image cards or stat panels in a row with `48px` gaps.
6. **Data** — Title, one-line subtitle, comparison table or a single big stat. Max one data object per slide.
7. **Closing** — Deep Green, statement line, inverse button, oversized wordmark clipped by the bottom edge.

Rhythm: never two consecutive slides with the same layout; place a Section divider or Statement every 4–5 slides; make at least one in four slides image-led.

---

## 8. Copy voice

Short declaratives. Present tense. Lowercase in body, sentence case in headlines, periods on headlines ("Meet Stillflow.", "Join the waitlist."). Concrete nouns over abstraction. No exclamation marks, no rhetorical questions, no "unlock/empower/revolutionize", no "this, not that" constructions.

Headline length: 3–8 words. Supporting line: one sentence, under 20 words.

---

## 9. Don't

- Gradient backgrounds or colored text on colored backgrounds beyond the pairs listed.
- Bold display type — display is always weight 200.
- More than one accent color, or green as a large background behind long body copy.
- Drop shadows on anything but the white form card.
- Text under 24px on a 1920×1080 slide.
- Icon sets, emoji, decorative SVG illustration. Use photography or leave it empty.
