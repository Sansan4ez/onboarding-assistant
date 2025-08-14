# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo-based documentation site for AI onboarding materials written in Russian. The site uses the hugo-book theme to create a documentation portal covering AI tools, search technologies, development tools, and architectural patterns for developers.

## Hugo Commands

### Development
```bash
# Start local development server
hugo server -D

# Build for production
hugo --minify

# Check configuration and content
hugo check

# Clean generated files
hugo --gc
```

### Hugo Version
Requires Hugo Extended version 0.146.0 or higher.

### Installation
```bash
# macOS with Homebrew
brew install hugo

# Ubuntu/Debian
sudo apt-get install hugo

# Windows with Chocolatey
choco install hugo-extended
```

## Content Structure

The project follows a three-level hierarchical structure:

```
content/
├── _index.md              # Main homepage
└── docs/                  # Documentation section
    ├── _index.md         # Docs homepage
    ├── menu/index.md     # Navigation menu definition
    ├── ai-ml/            # AI & Machine Learning
    ├── search-tech/      # Search Technologies  
    ├── dev-tools/        # Development Tools
    ├── content-mgmt/     # Content Management
    ├── backend/          # Backend & Database
    ├── architecture/     # Architecture patterns
    ├── utilities/        # Tools and utilities
    └── additional/       # Additional materials
```

## Hugo Configuration

Key settings in `hugo.toml`:
- `baseURL`: Set to GitHub Pages URL
- `publishDir`: "docs" (for GitHub Pages)
- `theme`: "hugo-book"
- `BookSection`: "docs" (main content section)
- `BookMenuBundle`: "/docs/menu" (navigation menu)

## Content Management

### File Naming Convention
- Use English filenames with dashes for URLs
- Russian content titles in front matter
- Section index files use `_index.md`
- Regular pages use `filename.md`

### Front Matter Structure
```yaml
---
title: "Russian Title"
date: 2024-12-19
draft: false
weight: 1
---
```

### Internal Linking
Use Hugo's relref shortcode for internal links:
```markdown
[Link Text]({{< relref "/docs/section/page" >}})
```

Avoid direct markdown links to prevent broken URLs after Hugo processing.

## Navigation Menu

Menu is defined in `content/docs/menu/index.md` using hugo-book theme format with:
- Three-level hierarchy
- Expandable sections
- Emoji icons for visual separation
- Proper weight ordering

## Deployment

The site builds to the `docs/` directory and deploys automatically to GitHub Pages. After making changes:

1. Run `hugo --minify` to build
2. Commit changes to `docs/` directory
3. GitHub Pages serves from `docs/` folder

## Theme

Uses alex-shpak/hugo-book theme installed as git submodule:
```bash
git submodule add https://github.com/alex-shpak/hugo-book.git themes/hugo-book
```

## Common Issues

- **Broken links**: Always use `{{< relref >}}` syntax for internal links
- **Missing pages**: Ensure `_index.md` files exist for sections
- **Menu not showing**: Check `BookMenuBundle` path in config
- **Build errors**: Run `hugo check` to validate configuration

## Content Categories

The documentation covers:
- **AI/ML**: LLMs, AI agents, RAG systems
- **Search**: Vector, full-text, hybrid search technologies  
- **Dev Tools**: Cursor AI, Dify.ai, UV tool
- **Content**: Git, GitHub Pages, Markdown guides
- **Backend**: Supabase analysis and setup
- **Architecture**: DDD, assistant architecture patterns
- **Utilities**: Pandoc, setup guides, scripts