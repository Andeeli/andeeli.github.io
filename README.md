# DS Portfolio

Welcome to my **Data Science Portfolio**! This repository is built using the [Jekyll Chirpy theme](https://github.com/cotes2020/jekyll-theme-chirpy), offering a clean and modern design for showcasing projects, blogs, and achievements.

---

## Features

### 🚀 Modern Jekyll Theme
- Powered by the **Chirpy theme**, this portfolio is optimized for speed, usability, and aesthetics.

### 📊 Data Science Projects
- Highlight key projects with detailed write-ups, code snippets, and visualizations.

### 📝 Blogs
- Share your thoughts on data science topics, methodologies, and insights.

### 🌐 Responsive Design
- Fully responsive layout ensures a seamless experience across devices.

---

## Installation

### Prerequisites
1. [Ruby](https://www.ruby-lang.org/en/downloads/)
2. [Jekyll](https://jekyllrb.com/docs/installation/)
3. [Bundler](https://bundler.io/)

### Steps
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/ds-portfolio.git
   cd ds-portfolio
   ```
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Run the site locally:
   ```bash
   bundle exec jekyll serve
   ```
4. Open the portfolio in your browser:
   ```
   http://localhost:4000
   ```

---

## Folder Structure

```
.
├── _config.yml         # Site configuration
├── _posts/            # Blog posts
├── _data/             # Site data files
├── _includes/         # HTML partials
├── _layouts/          # Page layouts
├── assets/            # Images, CSS, JS, etc.
├── projects/          # Project write-ups
├── index.html         # Homepage
└── README.md          # This file
```

---

## Customization

### Update `_config.yml`
Edit `_config.yml` to personalize the site, including:
- Site title and description
- Author information
- Social media links

### Add Projects
1. Create a new folder in `projects/` for each project.
2. Include a `README.md` or a custom HTML/Markdown file to describe the project.

### Write Blogs
1. Add a new file in the `_posts/` directory.
2. Use the following template:
   ```yaml
   ---
   layout: post
   title: "Post Title"
   date: YYYY-MM-DD
   tags: [tag1, tag2]
   ---

   Your blog content here.
   ```

---

## Deployment

### GitHub Pages
This portfolio is designed to be hosted on **GitHub Pages**. Follow these steps:
1. Push the repository to GitHub.
2. Go to the repository's **Settings > Pages**.
3. Select the source branch (e.g., `main`) and folder (`/root` or `/docs`).
4. Save and wait for the site to be published.

---

## License

This repository is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute as needed.

---

## Acknowledgments
- [Jekyll Chirpy Theme](https://github.com/cotes2020/jekyll-theme-chirpy) for the amazing theme.
- The open-source community for inspiration and support.
