# SareeLab — ChatGPT Custom GPT

An open-source ChatGPT Custom GPT that provides 11 AI-powered saree styling tools for Indian women. Upload your saree photo and get blouse design suggestions, color matching, embroidery ideas, hairstyle recommendations, mehndi patterns, and more.

## What is SareeLab?

SareeLab is an AI saree styling assistant built as a [ChatGPT Custom GPT](https://openai.com/index/introducing-gpts/). It uses ChatGPT's vision capabilities to analyze your saree photos and DALL-E to generate blouse designs, hairstyle previews, and mehndi patterns.

**No API keys needed** — if you have access to ChatGPT, you can use SareeLab.

## The 11 Tools

| # | Tool | What It Does | Output |
|---|------|-------------|--------|
| 1 | Saree Blouse Matcher | Suggests 5 matching + 5 contrasting blouse colors | Colors + preview image |
| 2 | Blouse Matching Indicator | Scores saree-blouse compatibility (0-100%) | Score + explanation |
| 3 | Blouse Border Strategist | Incorporates saree border into blouse design | Blouse image |
| 4 | Blouse Back Strategist | Designs blouse back based on pallu style | Back view image |
| 5 | Blouse Designer | Step-by-step custom blouse design (50+ options) | Front + back images |
| 6 | AI Blouse Designer | Upload saree, get AI-suggested blouse design | Design + front/back images |
| 7 | Saree Pleating Guide | Recommends pleating style for your fabric | Recommendation + visual |
| 8 | Embroidery Suggestion | Harmonious or statement embroidery ideas | Suggestion + front/back images |
| 9 | Hairstyle Advisor | Hairstyle recommendations by neckline & occasion | Suggestions + images |
| 10 | Mehndi Designer | Generates mehndi patterns from saree motifs | Hand with mehndi image |
| 11 | Occasion Matcher | Checks if your saree fits a specific occasion | Score + styling suggestions |

## How to Create Your Own GPT

1. Go to [ChatGPT GPT Builder](https://chatgpt.com/gpts/editor)
2. Switch to the **Configure** tab
3. Set **Name** to `SareeLab` (or your preferred name)
4. Copy the contents of [`sareelab-gpt-instructions.md`](sareelab-gpt-instructions.md) into the **Instructions** field
5. Upload these 3 files under **Knowledge**:
   - [`knowledge-blouse-options.md`](knowledge-blouse-options.md)
   - [`knowledge-tool-prompts.md`](knowledge-tool-prompts.md)
   - [`knowledge-selection-data.md`](knowledge-selection-data.md)
6. Enable **DALL-E Image Generation**, disable Web Browsing and Code Interpreter
7. Add conversation starters:
   - "I want to find a matching blouse color for my saree"
   - "Help me design a custom blouse step by step"
   - "Is my saree right for a wedding reception?"
   - "Generate a mehndi design inspired by my saree"
8. Save and publish!

## Files

| File | Purpose |
|------|---------|
| `sareelab-gpt-instructions.md` | The system prompt — paste into GPT Builder Instructions |
| `knowledge-blouse-options.md` | Blouse design options (50+ choices across 6 categories) |
| `knowledge-tool-prompts.md` | DALL-E prompt templates and conversation flows for all 11 tools |
| `knowledge-selection-data.md` | Selection options, scoring rubrics, and decision-tree logic |

## Customization Ideas

- **Add languages**: Translate the system prompt for Hindi, Tamil, Telugu, or other languages
- **Add tools**: Extend with jewelry matching, footwear suggestions, or makeup advice
- **Adjust scoring**: Tweak the matching rubrics in `knowledge-selection-data.md`
- **Change persona**: Edit the tone in `sareelab-gpt-instructions.md`

## Related

- [SareeLab Web App](https://github.com/prkvs/SareeLab) — The original React + Gemini AI web app

## License

MIT — use it, fork it, make it your own.
