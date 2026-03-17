You are creating a new blog post for this Hugo site. The user has provided a markdown file path (relative to the project root) as input: $ARGUMENTS

Follow these steps:

1. **Read the input file** at the given path relative to the project root.

2. **Analyze the content** to determine:
   - A concise, compelling post title (matching the tone and style of existing posts — conversational, often with a question or punchy phrase)
   - A URL-friendly slug derived from the title (lowercase, hyphens, no special characters — e.g., "But Where Does Discernment Come From?" becomes `but-where-does-discernment-come-from`)
   - Appropriate categories from this list (pick 1-2 that fit best):
     - `Orthodoxy` — anything related to Orthodox Christianity, theology, Church Fathers, saints' teachings
     - `Saints` — posts that focus on or heavily reference specific saints or ascetics
     - `Unity` — posts about Christian unity, ecumenism, reconciliation
     - `General` — general musings not strongly tied to a specific theological topic
     - `Rambling` — stream-of-consciousness or exploratory writing
     - `Faith` — general faith topics, spiritual life, prayer
   - A brief, descriptive alt text for the cover image (in the style of existing posts — short, evocative, often referencing byzantine art style)

3. **Create the post file** at `content/posts/YYYY-MM-DD-SLUG.md` where:
   - `YYYY-MM-DD` is today's date
   - `SLUG` is the URL-friendly slug from step 2

4. **Use this exact front matter format** (TOML with `+++` delimiters):
   ```
   +++
   date = 'YYYY-MM-DD'
   draft = false
   title = "Post Title Here"
   categories = ['Category1', 'Category2']
   [cover]
   image = "images/post-header/SLUG.jpg"
   alt = "Alt text description here"
   +++
   ```

5. **Place the content** from the input file directly after the front matter (with one blank line separating them).

6. **Report back** with:
   - The created file path
   - The title chosen
   - The categories assigned
   - The expected header image path (`static/images/post-header/SLUG.jpg`) — note that this image may not exist yet and will need to be created/added separately

IMPORTANT RULES:
- The image path in front matter uses `images/post-header/SLUG.jpg` (no leading slash, no `static/` prefix)
- The actual image file would go in `static/images/post-header/SLUG.jpg`
- Use TOML front matter (`+++`), NOT YAML (`---`)
- Set `draft = false` (published by default)
- The date should be today's date only (no timestamp), matching the format `'YYYY-MM-DD'`
- The slug should match the image name exactly
