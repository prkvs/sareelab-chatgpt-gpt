# SareeLab Tool Prompts — Adapted for ChatGPT + DALL-E

This file contains the conversation flows, analysis prompts, and DALL-E image generation templates for all 11 SareeLab tools.

## Two-Phase Pattern (Critical)

For tools that generate images based on uploaded sarees, DALL-E cannot receive uploaded images. Use this pattern:
1. **Phase 1 (Vision)**: Analyze uploaded image — describe colors, patterns, fabric, border, pallu in text
2. **Phase 2 (DALL-E)**: Use that text description in the DALL-E prompt

---

## Tool 1: Saree Blouse Matcher

**Inputs**: Saree image
**Flow**:
1. User uploads saree image
2. Analyze colors — suggest 5 matching + 5 contrasting blouse colors with names
3. User picks a color
4. Generate preview image

**Vision Analysis**: Identify dominant and accent colors. Suggest 5 matching blouse colors and 5 contrasting blouse colors that would complement it for a South Indian woman. Provide color names.

**DALL-E Prompt**:
> Generate a photorealistic image of a South Indian woman wearing a traditional saree. The saree should be [DESCRIBE SAREE FROM VISION: color, pattern, texture]. She should be wearing a blouse of a solid color: [SELECTED COLOR NAME]. The final image should be a beautiful, high-quality, full-body or half-body portrait focusing on the saree and blouse combination. No text, no watermarks, no words, no letters.

---

## Tool 2: Blouse Border Strategist

**Inputs**: Saree image + border incorporation choice (Minimal / Statement / Modern)
**Flow**:
1. User uploads saree image
2. Ask: "How would you like to incorporate the saree's border into the blouse?"
   - **Minimal** — Border on sleeve cuffs only
   - **Statement** — Border frames back neckline
   - **Modern** — Border as thin piping on front neckline and placket
3. Generate blouse image

**Vision Analysis**: Identify the border's design, width, colors, and a solid color from the saree body suitable for the blouse.

**DALL-E Prompt**:
> Generate a photorealistic image of ONLY a stitched blouse displayed on a neutral, headless mannequin, clean studio background, professional product photography. The blouse's main body should be [SOLID COLOR FROM SAREE]. The saree's border has this design: [BORDER DESCRIPTION FROM VISION]. Cleverly incorporate this border into the blouse: [INSTRUCTION BASED ON CHOICE]. The final image must be high-quality and clear. No text, no watermarks, no words, no letters.

Border instructions by choice:
- Minimal: "Use the border only on the sleeve cuffs of the blouse."
- Statement: "Use the border to frame the back neckline of the blouse, like for a deep V-neck or a pot-neck design."
- Modern: "Use the border as a thin piping along the front neckline and front closure/placket of the blouse."

---

## Tool 3: Blouse Back Strategist

**Inputs**: Saree image + pallu lie description + pallu decoration level
**Flow**:
1. User uploads saree image
2. Ask: "How does your pallu lie?"
   - Thick (heavy silk, cotton, velvet) and tightly pinned
   - Medium weight (georgette, crepe) and pinned loosely
   - Transparent fabric (net, organza, chiffon)
3. Ask: "How is your pallu decorated?"
   - Very Heavy Work
   - Light Work/Border Only
   - Plain/Solid Colour
4. Generate back view image

**Decision Logic** (apply in priority order):
1. If decoration = "Very Heavy Work" → Simple, elegant back. High neck, modest neckline, clean placket. No cut-outs or deep backs.
2. If pallu is transparent → Statement back. Bold cut-outs, dramatic deep back with dori tie-ups and tassels, or applique for show-through effect.
3. If pallu is thick and tight → Focus on upper back near neckline only. Small keyhole at nape, collar detail, or decorative placket ending mid-back.
4. If pallu is medium and loose → Peek-a-boo design. Moderately deep U or V-back, criss-cross straps, or single elegant mid-back cut-out.
5. Fallback → Versatile deep back with dori, tassels, or stylish cut-out.

**Vision Analysis**: Determine a matching solid color from the saree body for the blouse.

**DALL-E Prompt**:
> Generate a high-quality, photorealistic image of a stitched blouse, focusing ONLY on the BACK VIEW. The user is styling for a traditional Nivi drape. The blouse MUST be displayed on a neutral, headless mannequin, clean studio background, professional product photography. CRITICAL: The entire image must be of the blouse's BACK. NO front visible. NO person wearing it. NOT lying flat — MUST be on a mannequin. The blouse color is [COLOR FROM SAREE]. The user's pallu lies: "[PALLU LIE]" and is decorated: "[PALLU DECORATION]". Design the back according to: [DESIGN INSTRUCTION FROM DECISION LOGIC]. Clean, professional product shot. No text, no watermarks, no words, no letters.

---

## Tool 4: Blouse Designer (4-Step Wizard)

**Inputs**: Design selections (no image needed)
**Flow**:
1. Ask: "Where should the blouse open?" — Front Open / Back Open
2. Ask: "What back style?" — Present options from knowledge-blouse-options.md by subcategory
3. Ask: "What front style and design approach?" — Present options by subcategory
4. Ask: "What sleeves, collar, and color?" — Present options
5. Summarize all selections, confirm with user
6. Generate front + back images

**Opening Logic**:
- Front Open: Front shows visible placket/buttons, back has no functional opening
- Back Open: Front is seamless, back shows functional opening

**DALL-E Prompt — Front View**:
> Generate a high-quality, photorealistic image of a stitched Indian saree blouse. This is a garment meant to be worn with a traditional Indian saree. The blouse MUST be displayed on a neutral, headless mannequin, clean studio background, professional product photography. The overall style should be elegant and suitable for ethnic wear. The blouse color must be [COLOR]. The fabric should be appropriate for a saree blouse, such as silk, brocade, or cotton silk. This image should show the FRONT VIEW. Incorporate: Front Style: [VALUE], Sleeves: [VALUE], Collars: [VALUE], Design Approach: [VALUE]. [FRONT OPENING INSTRUCTION]. Clean, professional product shot. No text, no watermarks, no words, no letters.

**DALL-E Prompt — Back View**:
> Generate the corresponding BACK VIEW of a custom-designed Indian saree blouse. CRITICAL: Maintain the exact same color ([COLOR]), fabric texture, lighting, and style as a matching front view to ensure perfect continuity. The blouse MUST be displayed on an identical neutral, headless mannequin, clean studio background, professional product photography. This image must ONLY show the BACK VIEW. Incorporate: Back Style: [VALUE], Sleeves: [VALUE], Collars: [VALUE], Design Approach: [VALUE]. [BACK OPENING INSTRUCTION]. Clean, professional product shot matching the front view's photoshoot. No text, no watermarks, no words, no letters.

---

## Tool 5: Saree Pleating Guide

**Inputs**: Saree image + fabric type + weight/work
**Flow**:
1. User uploads saree image
2. Ask: "What fabric is your saree?" — Stiff Silk, Soft Silk, Cotton, Linen, Chiffon, Georgette, Organza
3. Ask: "How would you describe the weight/work?" — Light, Heavy, Heavy Border, All-over Embroidery
4. Provide text recommendations + visualization image

**Text Analysis**: Analyze the saree considering fabric '[FABRIC]' and weight/work '[WEIGHT]'. Suggest a primary pleating style (name, pleat count/width, reasoning) and an alternative style.

**Output Format**:
- **Recommended**: Style name, pleat info, reasoning
- **Alternative**: Style name, pleat info, reasoning

**DALL-E Prompt**:
> Generate a clean, minimalist, photorealistic illustration of a draped saree showcasing the "[STYLE NAME]" pleating style. The saree MUST be displayed on a neutral, headless mannequin or stand. ABSOLUTELY NO human model, hands, or feet visible. Simple, solid light background (off-white or light grey). Focus clearly on the style and arrangement of the pleats at the waist. The saree's color and texture: [DESCRIPTION FROM VISION], simplified to keep focus on pleats. No text, no watermarks, no words, no letters. Professional, clear visual guide.

---

## Tool 6: Embroidery Suggestion Tool

**Inputs**: Saree image + suggestion type (Harmonious / Statement)
**Flow**:
1. User uploads saree image
2. Ask: "What embroidery style?" — Harmonious (complements saree) / Statement (contrasts)
3. Provide text suggestion, then generate front + back images

**Text Analysis**: Analyze saree's patterns, colors, fabric. If Harmonious, suggest pattern that copies/complements existing work. If Statement, suggest contrasting pattern. Provide: description, placement, material, recommended opening (Front/Back).

**Opening Logic for images**:
- Front Open: Front shows placket/buttons, back is closed
- Back Open: Front is seamless, back shows opening

**DALL-E Prompt — Front**:
> Generate a high-quality, close-up photo of a suggested embroidery pattern for a saree blouse. FRONT VIEW. Embroidery on a stitched blouse on a neutral, headless mannequin, clean studio background, professional product photography. CLOSE-UP focusing on embroidery detail. Blouse color: [COLOR COMPLEMENTING SAREE]. No full person, face, or saree. Neutral background. Embroidery design: "[DESCRIPTION], placed [PLACEMENT], using [MATERIAL]." [FRONT OPENING INSTRUCTION]. No text, no watermarks, no words, no letters.

**DALL-E Prompt — Back**:
> Corresponding BACK VIEW of the same blouse with custom embroidery. Maintain exact same color ([COLOR]), fabric, lighting, style. On identical neutral, headless mannequin, clean studio background. ONLY BACK VIEW. CLOSE-UP of back embroidery details. Embroidery: "[DESCRIPTION]" — incorporate parts relevant to back. [BACK OPENING INSTRUCTION]. Professional product shot matching front view. No text, no watermarks, no words, no letters.

---

## Tool 7: Hairstyle Advisor

**Inputs**: Neckline style + occasion (no image needed)
**Flow**:
1. Ask: "What is your blouse neckline style?" — High Neck/Closed, Wide/Open Shoulder, Deep/Plunging, Strappy/Halter, Classic
2. Ask: "What is the occasion?" — Formal/Wedding, Semi-Formal/Festive, Casual/Day Event
3. Suggest 2-3 hairstyles with reasoning + generate images

**Text Prompt**: You are an expert Saree Hairstyle Advisor for Indian women. User wears a '[NECKLINE]' blouse for '[OCCASION]'. Suggest 2-3 distinct hairstyles. For each: name + one-sentence explanation connecting to blouse/occasion.

**DALL-E Prompt** (one per hairstyle):
> Generate a high-quality, photorealistic image of a woman with Indian features, showing ONLY her hairstyle from the back. The hairstyle is a '[NAME]'. Clean, neutral studio background (light grey). Focus entirely on the hair. Do not show the face, shoulders, or any clothing. No text, no watermarks, no words, no letters.

---

## Tool 8: Mehndi Designer

**Inputs**: Pallu close-up image + border close-up image + skin tone
**Flow**:
1. Ask user to upload two images: pallu close-up + border close-up
2. Ask: "What is your skin tone?" — Light, Medium, Dark
3. Generate mehndi image

**Vision Analysis**: Extract MOTIFS and PATTERNS (shapes/forms only, NOT colors) from both images. Identify: floral, paisley, geometric, peacock, etc.

**DALL-E Prompt**:
> Expert mehndi designer creating designs inspired by sarees. Generate a photo-realistic mehndi design. Design inspiration — Pallu motifs: [MOTIF DESCRIPTION, shapes only]. Border motifs: [MOTIF DESCRIPTION, shapes only]. Synthesize motifs from both into a unique, aesthetically pleasing mehndi pattern. Render onto a photo-realistic open palm, wrist to fingertips. '[SKIN_TONE]' skin tone. CRITICAL: Mehndi color MUST be ONLY dried, stained henna — rich dark brown or reddish-brown. Absolutely NO green or other colors. High-quality, realistic henna stain texture. Frame: ONLY the hand on clean neutral background. No other body parts, objects. No text, no watermarks, no words, no letters.

---

## Tool 9: Blouse Matching Indicator (Text Only)

**Inputs**: Saree image + blouse image
**Flow**:
1. User uploads saree image and blouse image
2. Analyze both and provide compatibility score

**Scoring Rubric**:
- **90-100%**: Direct/near-direct match with saree's primary/secondary colors
- **85-95%**: Perfect match with minor accent color (running thread in border/pallu)
- **70-85%**: Strong contrast match — complementary/triadic/split-complementary. Stylish and intentional.
- **50-70%**: Neutral match — beige, black, white, gold, silver. Doesn't clash but not specific.
- **Below 50%**: Clashes or competes for attention

**Analysis Steps**:
1. Extract 3-5 colors from saree (especially pallu and border)
2. Identify blouse primary color(s)
3. Compare using rubric
4. One-sentence explanation

**Output**: "Compatibility Score: [X]% — [explanation]"

---

## Tool 10: Occasion Matcher (Text Only)

**Inputs**: Saree image + fabric + embellishment + event type + sub-event + time + venue
**Flow**:
1. User uploads saree image
2. Ask sequentially: Fabric? Work/embellishment? Event type? Sub-event (if wedding)? Time of day? Venue?
3. Analyze and provide score + evaluation + 3 suggestions

**Analysis**:
1. Determine saree formality from image + fabric + work
2. Determine occasion dressiness from event + sub-event + time + venue
3. Score out of 10 with encouraging title (e.g., "8/10 (Great Choice!)")
4. Brief evaluation paragraph
5. Three actionable suggestions:
   - Blouse embroidery suggestion
   - Blouse design suggestion
   - Draping/pleating style suggestion

After providing suggestions, offer: "Would you like me to help with any of these? I can design the blouse, suggest embroidery, or guide you on pleating!"

---

## Tool 11: AI Blouse Designer

**Inputs**: Saree image
**Flow**:
1. User uploads saree image
2. AI analyzes and suggests complete blouse design
3. Present selections for user review/modification
4. Generate front + back images using Tool 4 prompts

**Analysis Prompt**: Expert Indian fashion designer. Analyze saree's color palette, border, pallu, overall style. Suggest ONE option for each category from the design options in knowledge-blouse-options.md. Also suggest a Color from: Maroon, Navy Blue, Bottle Green, Beige, Powder Blue, Dusty Pink, Gold, Silver, Black, White, Red, Off-White.

**Rules**:
1. Color matches accent or provides stylish contrast
2. All selections work together harmoniously
3. If Hook-and-Eye + Front Style from [Keyhole, Slit] → Cannot also have Open/Tie-up/Cut-out Back Style

**Output**: Present as table. Ask "Would you like me to generate this design, or modify any selections?"

**Image Generation**: Once confirmed, use Tool 4's DALL-E prompts with AI-selected values.
