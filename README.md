# GitHub Pages Static Website

A modern, responsive static website ready for deployment on GitHub Pages.

## 🚀 Quick Start

### 1. Create a GitHub Repository

1. Go to [GitHub](https://github.com) and create a new repository
2. Name it `your-username.github.io` (for user site) or any name (for project site)
3. Make sure it's **public** (required for free GitHub Pages)
4. Don't initialize with README, .gitignore, or license (since you already have files)

### 2. Upload Your Files

**Option A: Using Git (Recommended)**
```bash
# Initialize git in your project folder
cd /Users/mac/Documents/choso-static
git init

# Add all files
git add .

# Commit your files
git commit -m "Initial commit: Static website"

# Add your GitHub repository as origin
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git

# Push to GitHub
git branch -M main
git push -u origin main
```

**Option B: Using GitHub Web Interface**
1. Go to your repository on GitHub
2. Click "uploading an existing file"
3. Drag and drop all your files (`index.html`, `styles.css`, `script.js`)
4. Commit the changes

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings** tab
3. Scroll down to **Pages** section (in the left sidebar)
4. Under **Source**, select **Deploy from a branch**
5. Choose **main** branch and **/ (root)** folder
6. Click **Save**

### 4. Access Your Website

- **User site**: `https://your-username.github.io`
- **Project site**: `https://your-username.github.io/repository-name`

It may take a few minutes for your site to be available after the first deployment.

## 📁 File Structure

```
choso-static/
├── index.html      # Main HTML file
├── styles.css      # CSS styling
├── script.js       # JavaScript functionality
└── README.md       # This file
```

## 🎨 Customization

### Update Content
- Edit `index.html` to change text, sections, and structure
- Update the hero section, about content, services, and contact info
- Replace placeholder email and GitHub username

### Modify Styling
- Edit `styles.css` to change colors, fonts, layout
- The site uses a modern blue gradient theme by default
- Fully responsive design that works on all devices

### Add Functionality
- Edit `script.js` to add interactive features
- Includes smooth scrolling, animations, and mobile menu

### Add More Pages
Create additional HTML files in the same directory:
- `about.html`
- `contact.html`
- `portfolio.html`

Update navigation links in `index.html` accordingly.

## 🔧 Advanced Features

### Custom Domain (Optional)
1. Add a `CNAME` file with your domain name
2. Configure DNS settings with your domain provider
3. Update GitHub Pages settings to use custom domain

### Analytics (Optional)
Add Google Analytics by inserting the tracking code in the `<head>` section of `index.html`.

### SEO Optimization
- Update `<title>` and meta tags in `index.html`
- Add Open Graph tags for social media sharing
- Include a `sitemap.xml` file

## 🌟 Features

- ✅ Fully responsive design
- ✅ Modern, clean aesthetic
- ✅ Smooth scrolling navigation
- ✅ Mobile-friendly menu
- ✅ CSS animations and hover effects
- ✅ Cross-browser compatible
- ✅ Fast loading times
- ✅ SEO-friendly structure

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## 🛠️ Development

To make changes:
1. Edit files locally
2. Test by opening `index.html` in your browser
3. Commit and push changes to GitHub
4. GitHub Pages will automatically update your live site

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

**Need help?** Check the [GitHub Pages documentation](https://docs.github.com/en/pages) or [create an issue](https://github.com/YOUR-USERNAME/YOUR-REPO-NAME/issues).