# Orthodox Nobody Blog

A Hugo static site for Orthodox Christianity and theology discussions, built with the PaperMod theme and deployed via GitHub Pages.

## 🚀 Quick Start

### Prerequisites
- [Hugo](https://gohugo.io/installation/) (Extended version v0.150.0+)
- [Git](https://git-scm.com/)
- [Go](https://golang.org/dl/) (for Hugo modules, if needed)

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/orthodoxnobody/blog.git
   cd blog
   ```

2. **Initialize Hugo modules and install theme:**
   ```bash
   git submodule update --init --recursive
   ```

3. **Start the development server:**
   ```bash
   hugo server --buildDrafts --buildFuture
   ```

   Or for basic development:
   ```bash
   hugo server
   ```

4. **Open your browser** to http://localhost:1313

The development server includes:
- Live reload on file changes
- Draft and future post preview (with flags)
- Fast rebuild times

## 📁 Project Structure

```
├── .github/
│   └── workflows/          # GitHub Actions for deployment
├── archetypes/             # Content templates
├── assets/
│   └── css/
│       └── extended/       # Custom CSS overrides
├── content/
│   ├── posts/              # Blog posts
│   ├── about.md            # About page
│   ├── connect.md          # Contact information
│   ├── archives.md         # Post archives
│   └── search.md           # Search functionality
├── layouts/
│   └── partials/
│       └── extend_head.html # Custom head content (fonts)
├── static/                 # Static assets (images, files)
├── themes/
│   └── hugo-PaperMod/      # Theme submodule
├── hugo.yaml               # Site configuration
├── .gitignore             # Git ignore rules
└── README.md              # This file
```

## 🔧 Building

### Development Build
```bash
hugo server
```

### Production Build
```bash
hugo --minify
```

This generates optimized static files in the `public/` directory with:
- Minified HTML, CSS, and JS
- Optimized images
- Generated RSS feeds and search index

## 🚀 Deployment

### GitHub Pages (Recommended)

This blog is configured for automatic deployment to GitHub Pages using GitHub Actions.

#### Setup Instructions:

1. **Enable GitHub Pages:**
   - Go to your repository settings
   - Navigate to "Pages" section
   - Set source to "GitHub Actions"

2. **Push to main branch:**
   ```bash
   git add .
   git commit -m "Deploy to GitHub Pages"
   git push origin main
   ```

3. **GitHub Actions will automatically:**
   - Build the Hugo site
   - Deploy to GitHub Pages
   - Make it available at `https://orthodoxnobody.github.io/blog`

#### GitHub Actions Workflow

The deployment uses the following workflow (`.github/workflows/hugo.yml`):
- Triggers on pushes to `main` branch
- Uses Hugo Extended latest version
- Builds with `--minify` flag
- Deploys to GitHub Pages with proper permissions

### Manual Deployment

For other hosting providers:

1. **Build the site:**
   ```bash
   hugo --minify
   ```

2. **Upload the `public/` directory** to your web server

3. **Configure your web server** to serve from the uploaded directory

## ✍️ Writing Content

### Create a New Post

```bash
hugo new posts/my-new-post.md
```

### Post Front Matter Example

```yaml
---
title: "My New Post"
date: 2025-01-15T10:00:00-07:00
draft: false
tags: ["orthodoxy", "theology"]
categories: ["faith"]
summary: "Brief description of the post"
---
```

### Content Organization

- **Posts:** Go in `content/posts/`
- **Pages:** Go directly in `content/`
- **Images:** Place in `static/images/` and reference as `/images/filename.jpg`

## 🎨 Customization

### Fonts
- Primary font: Atkinson Hyperlegible (body text)
- Hero font: Piazzolla (headings and titles)
- Fonts are loaded via Google Fonts in `layouts/partials/extend_head.html`

### CSS Customization
Custom styles are in `assets/css/extended/custom.css` and include:
- Font family overrides
- Hero quote styling
- Dark mode support
- Responsive design enhancements

### Configuration
Main configuration is in `hugo.yaml`:
- Site metadata and URLs
- Menu structure
- Theme parameters
- Output formats (HTML, RSS, JSON for search)

## 🔍 Features

### Built-in Features:
- **Search:** Full-text search using Fuse.js
- **Archives:** Chronological post organization
- **RSS Feed:** Available at `/index.xml`
- **Dark/Light Mode:** Automatic theme switching
- **Responsive Design:** Mobile-first approach

### Custom Features:
- **Hero Quotes:** Styled quote blocks with hover effects
- **Custom Typography:** Optimized font stack for readability
- **Social Sharing:** Built-in social media sharing buttons

## 🛠️ Development Commands

```bash
# Start development server
hugo server

# Start with drafts and future posts
hugo server --buildDrafts --buildFuture

# Build for production
hugo --minify

# Check Hugo version
hugo version

# Create new content
hugo new posts/post-name.md

# Check site statistics
hugo --templateMetrics
```

## 📝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Test locally: `hugo server`
5. Commit your changes: `git commit -am 'Add feature'`
6. Push to the branch: `git push origin feature-name`
7. Create a Pull Request

## 🐛 Troubleshooting

### Common Issues:

**Hugo server not starting:**
- Check Hugo version: `hugo version`
- Ensure you have Hugo Extended
- Try `hugo server --verbose` for detailed output

**Theme not loading:**
- Update submodules: `git submodule update --init --recursive`
- Check if `themes/hugo-PaperMod` directory exists

**Build failures:**
- Clear Hugo cache: `hugo --gc`
- Check for syntax errors in content files
- Verify all images referenced in posts exist

**Font not loading:**
- Check network connection for Google Fonts
- Verify `extend_head.html` is in correct location

## 📄 License

This blog content is licensed under [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/).

The Hugo PaperMod theme is licensed under the MIT License.

## 🤝 Contact

- Email: me@orthodoxnobody.org
- GitHub: [@orthodoxnobody](https://github.com/orthodoxnobody)

---

**Note:** This is a personal blog focused on Orthodox Christianity and theology. All views expressed are those of the author and should not be considered authoritative church teaching.