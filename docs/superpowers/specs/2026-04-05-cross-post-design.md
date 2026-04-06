# Cross-Post Skill Design

## Summary

A user-level Claude Code skill that generates platform-specific promotional content for any project. Reads the current repo's README for context, asks the user a few questions, then generates tailored content for selected platforms.

## Location

`~/.claude/skills/cross-post/SKILL.md` — user-level, available across all projects.

## Flow

1. **Auto-read README** — Read the current repo's README to extract project name, description, features, and any other relevant info.
2. **Ask core questions** — Two questions, one at a time:
   - "What are the key highlights you want to promote?"
   - "Who is the target audience?"
3. **Ask platform selection** — Present available platforms, user picks one or more:
   - Juejin (掘金)
   - V2EX
   - Xiaohongshu (小红书)
   - X (Twitter)
   - Or describe a custom platform
4. **Generate content** — For each selected platform, generate content matching its preset tone and format.
5. **Write files** — Save to `./posts/<YYYY-MM-DD>-<platform>.md`
6. **Ensure .gitignore** — Automatically add `posts/` to `.gitignore` if not already present. No user confirmation needed.

## Platform Presets

### Juejin (掘金)
- **Tone**: Technical, structured, informative
- **Format**: Markdown article with heading hierarchy, code examples, clear sections
- **Length**: 800-1500 words
- **Style**: Like a tech blog post — problem → solution → how it works → how to use

### V2EX
- **Tone**: Community sharing, casual but substantive
- **Format**: Plain text leaning, concise, conversational
- **Length**: 300-600 words
- **Style**: Like telling a friend about something cool you built

### Xiaohongshu (小红书)
- **Tone**: Enthusiastic, colloquial, emoji-friendly
- **Format**: Short paragraphs, hashtags at the end
- **Length**: 200-400 words
- **Style**: Discovery and recommendation — "I found this amazing thing"

### X (Twitter)
- **Tone**: Punchy, hook-driven, concise
- **Format**: Single tweet (280 chars) or thread (5-10 tweets)
- **Length**: 280 chars per tweet
- **Style**: Strong opening hook, one idea per tweet, end with link

### Custom Platform
- If user names a platform not in the preset list, ask for a one-line tone description and generate accordingly.

## Output

- File path: `./posts/<YYYY-MM-DD>-<platform>.md`
- Platform names in filenames: `juejin`, `v2ex`, `xiaohongshu`, `x`
- Each file is standalone, ready to copy-paste to the platform
- Content is in the platform's native language (Chinese for 掘金/V2EX/小红书, English for X)

## Out of Scope

- Actual posting to platforms (manual copy-paste)
- Image generation
- Analytics or tracking
- Scheduling
