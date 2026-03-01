# Selection Options & Scoring Rubrics

This file contains all the selection options and scoring algorithms used across SareeLab's tools.

---

## Occasion Matcher Options

### Fabric Types
1. Silk (Kanjivaram, Banarasi)
2. Art Silk
3. Cotton
4. Chiffon
5. Georgette
6. Organza
7. Crepe
8. Net
9. Linen
10. Other

### Work & Embellishment
1. Plain (No work)
2. Printed
3. Light Embroidery/Threadwork
4. Heavy Zari/Zardozi
5. Sequin/Stone Work
6. Woven Border

### Primary Event Types
1. Wedding
2. Festive
3. Formal Party
4. Work Event
5. Casual Gathering
6. Temple/Religious Function

### Wedding Sub-Events (only ask if Primary Event = "Wedding")
1. Haldi
2. Mehendi
3. Sangeet
4. Cocktail Party
5. Main Ceremony (Pheras)
6. Reception

### Time of Day
1. Day Event
2. Evening Event
3. All-Day Function

### Venue/Scale
1. Large (Banquet Hall / Hotel)
2. Intimate (At Home / Small Venue)
3. Outdoor (Lawn / Beach)

---

## Pleating Guide Options

### Fabric Types
1. Stiff Silk
2. Soft Silk
3. Cotton
4. Linen
5. Chiffon
6. Georgette
7. Organza

### Weight/Work Categories
1. Light
2. Heavy
3. Heavy Border
4. All-over Embroidery

---

## Hairstyle Advisor Options

### Neckline Categories
1. High Neck / Closed
2. Wide / Open Shoulder
3. Deep / Plunging
4. Strappy / Halter
5. Classic (Round, Square, etc.)

### Occasion
1. Formal / Wedding
2. Semi-Formal / Festive
3. Casual / Day Event

---

## Mehndi Designer Options

### Skin Tone
1. Light
2. Medium
3. Dark

### Required Image Uploads
- Pallu close-up image
- Border close-up image

---

## Embroidery Suggestion Options

### Suggestion Type
1. **Harmonious** — Pattern that copies or complements the saree's existing work
2. **Statement** — Pattern or color that provides dynamic visual contrast

---

## Border Strategist Options

### Border Incorporation Style
1. **Minimal** — Border on sleeve cuffs only
2. **Statement** — Border frames back neckline
3. **Modern** — Border as thin piping on front neckline and placket

---

## Back Strategist Options

### How the Pallu Lies
1. "The pallu is thick (e.g., heavy silk, cotton, velvet) and tightly pinned"
2. "The pallu is of medium weight (e.g., georgette, crepe) and pinned loosely, allowing some movement."
3. "The pallu is made of a transparent fabric (e.g., net, organza, chiffon)."

### Pallu Decoration Level
1. Very Heavy Work
2. Light Work/Border Only
3. Plain/Solid Colour

### Back Design Decision Logic
Apply these rules in priority order:

1. **If decoration = "Very Heavy Work"** → Simple, elegant back. High neck, modest round/square neck, or clean button placket. No cut-outs, deep backs, or busy tie-ups.

2. **If pallu is transparent** → Statement back piece. Bold cut-outs, dramatic deep back with dori tie-ups and tassels, or delicate applique/embroidery for a "show-through" effect.

3. **If pallu is thick and tight** → Focus on upper back near neckline only. Small keyhole at nape, interesting collar detail, or decorative button placket ending mid-back. Lower back should be simple.

4. **If pallu is medium weight and loose** → "Peek-a-boo" design. Moderately deep U or V-back, criss-cross straps, or single elegant cut-out in mid-back.

5. **Fallback** → Versatile and elegant. Deep back with dori, decorative tassels, or stylish cut-out pattern.

---

## Blouse Matching Indicator — Scoring Rubric

When comparing a saree image and a blouse image, use this algorithm:

| Score Range | Criteria |
|-------------|----------|
| **90-100%** | Direct or near-direct match with one of the saree's primary or secondary colors |
| **85-95%** | Perfect match with a minor but distinct accent color (like a "running thread" color in border or pallu) |
| **70-85%** | Strong "contrast match" based on color theory — complementary, triadic, or split-complementary colors relative to the saree's dominant color. Must look intentional and stylish. |
| **50-70%** | "Neutral match" — blouse in beige, black, white, gold, or silver that doesn't clash but isn't a direct or contrast match |
| **Below 50%** | Colors don't harmonize, clash, or compete for attention in a displeasing way |

### Analysis Steps
1. Extract 3-5 dominant and accent colors from the saree (especially pallu and border)
2. Identify primary color(s) of the blouse
3. Compare using the scoring table above
4. Provide a one-sentence explanation justifying the score

---

## Occasion Matcher — Scoring Guide

### Analysis Steps
1. Analyze saree formality from image (color, print vs woven, border size), fabric, and embellishment
2. Determine required dressiness from event type, sub-event, time of day, and venue
3. Compare and score out of 10 with encouraging title (e.g., "8/10 (Great Choice!)")
4. Write brief evaluation paragraph explaining reasoning
5. Provide 3 styling suggestions connecting to other SareeLab tools:
   - Blouse embroidery suggestion
   - Blouse design suggestion
   - Draping/pleating style suggestion
