# My Blog

A modern blog built with Hugo and the PaperMod theme, deployed on Cloudflare Pages.

## Local Development

1. Install Hugo (if not already installed):
   ```bash
   brew install hugo  # macOS
   # or visit https://gohugo.io/installation/ for other platforms
   ```

2. Clone this repository:
   ```bash
   git clone <your-repo-url>
   cd my-blog
   ```

3. Initialize git submodules (for the theme):
   ```bash
   git submodule update --init --recursive
   ```

4. Start the development server:
   ```bash
   hugo server --buildDrafts
   ```

5. Visit `http://localhost:1313` to view the site.

## Creating Content

- Create a new blog post: `hugo new content posts/my-post.md`
- Create a new page: `hugo new content page-name.md`

## Deployment on Cloudflare Pages

This site is configured to deploy automatically to Cloudflare Pages. The build settings are:

- **Build command**: `hugo`
- **Build output directory**: `public`
- **Hugo version**: `0.148.2` (or latest)

The site will automatically rebuild and deploy when you push changes to the main branch.

## Theme

This blog uses the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, which provides:

- Clean, modern design
- Dark/light mode toggle
- Fast performance
- SEO optimized
- Social media integration
- Search functionality

## Configuration

Site configuration is in `hugo.toml`. Key settings include:

- Site title and description
- Theme configuration
- Menu items
- SEO settings
- Social media links

## License

This project is open source and available under the [MIT License](LICENSE).