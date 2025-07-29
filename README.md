# Fausto Rosado - Portfolio Website

A modern, responsive portfolio website showcasing my skills, projects, and professional experience. Built with HTML, CSS, and JavaScript, featuring a clean design and smooth animations.

## 🌟 Features

- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Modern UI/UX**: Clean, professional design with smooth animations
- **Interactive Elements**: Animated headlines, image sliders, and hover effects
- **Project Showcase**: Detailed presentation of development projects
- **Professional Resume**: Comprehensive resume with skills and experience
- **Social Integration**: Direct links to LinkedIn and GitHub profiles

## 📁 Project Structure

```
my-portfolio/
├── index.html          # Main landing page
├── projects.html       # Project showcase page
├── hire.html          # Resume and hiring page
├── assets/
│   ├── css/
│   │   ├── main.css
│   │   ├── jquery.mb.vimeo_player.min.css
│   │   └── jquery.mb.YTPlayer.min.css
│   ├── js/
│   │   ├── main.js
│   │   ├── plugins/
│   │   │   ├── animate-headline.js
│   │   │   ├── jquery.mb.vimeo_player.min.js
│   │   │   ├── jquery.mb.YTPlayer.min.js
│   │   │   └── slick.min.js
│   │   └── vendor/
│   │       ├── jquery-1.12.0.min.js
│   │       └── modernizr-2.8.3.min.js
│   ├── images/
│   │   ├── admin-panel.gif
│   │   ├── friendly-bakery.gif
│   │   ├── rumblr.gif
│   │   ├── index.jpg
│   │   ├── index-slider1.jpg
│   │   └── index-slider2.jpg
│   └── fonts/
│       ├── vimeo.otf
│       ├── vimeo.ttf
│       ├── vimeo.woff
│       ├── vimeo.woff2
│       ├── ytp-regular.eot
│       ├── ytp-regular.ttf
│       └── ytp-regular.woff
└── README.md
```

## 🚀 Quick Start

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/FaustoRosado/my-portfolio.git
   cd my-portfolio
   ```

2. **Open in your browser**
   - Simply open `index.html` in your web browser
   - Or use a local server for better development experience:
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js (if you have http-server installed)
   npx http-server
   
   # Using PHP
   php -S localhost:8000
   ```

3. **Access your site**
   - Navigate to `http://localhost:8000` in your browser

## 🌐 Free Deployment Options

### GitHub Pages (Free & Recommended)

GitHub Pages is completely **FREE** and perfect for portfolio websites. It automatically builds and deploys your site from your GitHub repository.

#### Quick Setup (5 minutes)

1. **Create GitHub Repository**
   ```bash
   # If you haven't already, create a new repository on GitHub
   # Then push your code:
   git add .
   git commit -m "Initial portfolio commit"
   git push origin main
   ```

2. **Enable GitHub Pages (Free)**
   - Go to your repository on GitHub
   - Click **Settings** tab
   - Scroll down to **Pages** section (under "Code and automation")
   - Under **Source**, select **Deploy from a branch**
   - Choose **main** branch and **/(root)** folder
   - Click **Save**

3. **Your site is live!**
   ```
   https://yourusername.github.io/repository-name
   ```
   *Example: https://faustorosado.github.io/my-portfolio*

#### Custom Domain (Optional)

Want your own domain? GitHub Pages supports custom domains for free:

1. **Purchase a domain** (e.g., from Namecheap, GoDaddy, or Google Domains)

2. **Configure DNS**
   - Add a CNAME record pointing to `yourusername.github.io`
   - Or add A records pointing to GitHub Pages IP addresses

3. **Update GitHub repository**
   - Go to repository **Settings** → **Pages**
   - Enter your custom domain in the **Custom domain** field
   - Save the changes

4. **Create CNAME file**
   ```bash
   echo "yourdomain.com" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push origin main
   ```

### AWS S3 + CloudFront (Advanced - Optional)

For those who want more control and advanced features, AWS offers a robust hosting solution:

#### Prerequisites
- AWS Account (free tier available)
- AWS CLI installed and configured

#### Setup Steps

1. **Create S3 Bucket**
   ```bash
   aws s3 mb s3://your-portfolio-bucket-name
   aws s3 website s3://your-portfolio-bucket-name --index-document index.html
   ```

2. **Upload Files**
   ```bash
   aws s3 sync . s3://your-portfolio-bucket-name --exclude ".git/*" --exclude "README.md"
   ```

3. **Configure CloudFront Distribution**
   - Go to AWS CloudFront console
   - Create new distribution
   - Set origin domain to your S3 bucket
   - Configure caching and security settings

4. **Set up CI/CD (Optional)**
   ```yaml
   # .github/workflows/deploy.yml
   name: Deploy to AWS S3
   on:
     push:
       branches: [ main ]
   jobs:
     deploy:
       runs-on: ubuntu-latest
       steps:
       - uses: actions/checkout@v2
       - name: Deploy to S3
         uses: aws-actions/configure-aws-credentials@v1
         with:
           aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
           aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
           aws-region: us-east-1
       - name: Sync files
         run: aws s3 sync . s3://your-bucket-name --delete
   ```

#### AWS Benefits
- **Global CDN**: Faster loading worldwide
- **Custom SSL**: Free SSL certificates
- **Advanced Analytics**: Detailed visitor statistics
- **Security**: DDoS protection and security headers
- **Scalability**: Handles high traffic automatically

#### Cost Comparison
- **GitHub Pages**: Completely FREE
- **AWS S3 + CloudFront**: ~$1-5/month (depending on traffic)
- **Custom Domain**: ~$10-15/year (domain registration)

**Recommendation**: Start with GitHub Pages (free), upgrade to AWS if you need advanced features or high traffic.

## 📝 Customization Guide

### Updating Personal Information

1. **Main Page (`index.html`)**
   - Update the hero section text in the `title__effect` divs
   - Modify the description text
   - Update navigation links

2. **Projects Page (`projects.html`)**
   - Replace project images in `assets/images/`
   - Update project descriptions and links
   - Add new project sections as needed

3. **Resume Page (`hire.html`)**
   - Update personal information in the resume section
   - Modify skills, experience, and education
   - Customize the styling in the `<style>` section

### Styling Customization

The portfolio uses a clean, modern design with these key styling features:

- **Color Scheme**: Blue (#007bff) primary, with green (#28a745) and yellow (#ffc107) accents
- **Typography**: Montserrat font family for professional appearance
- **Layout**: Responsive grid system with CSS Grid and Flexbox
- **Animations**: Smooth transitions and hover effects

### Adding New Pages

1. **Create new HTML file** following the existing structure
2. **Include required assets**:
   ```html
   <link href="assets/css/main.css" rel="stylesheet">
   <script src="assets/js/vendor/jquery-1.12.0.min.js"></script>
   <script src="assets/js/main.js"></script>
   ```
3. **Update navigation** in all existing pages
4. **Test responsiveness** on different screen sizes

## 💼 Resume Writing Tips

### Structure Your Resume Effectively

1. **Header Section**
   - Name, title, contact information
   - Professional summary (2-3 sentences)
   - Links to portfolio, LinkedIn, GitHub

2. **Skills Section**
   - Group skills by category (Languages, Frameworks, Tools)
   - Use specific technologies rather than general terms
   - Include proficiency levels if relevant

3. **Experience Section**
   - Use action verbs to start bullet points
   - Quantify achievements with numbers
   - Focus on impact and results
   - Include relevant projects and technologies

4. **Education & Certifications**
   - List most recent education first
   - Include relevant certifications
   - Mention ongoing education or training

### Writing Tips for Tech Resumes

1. **Use Technical Keywords**
   - Include specific programming languages, frameworks, and tools
   - Match keywords from job descriptions
   - Use industry-standard terminology

2. **Quantify Achievements**
   - "Completed 1550+ technical jobs with 4.9/5 rating"
   - "Managed 500+ client relationships"
   - "Reduced system downtime by 40%"

3. **Show Problem-Solving Skills**
   - Describe challenges you've solved
   - Explain your approach and methodology
   - Highlight innovative solutions

4. **Keep It Concise**
   - Aim for 1-2 pages maximum
   - Use bullet points for readability
   - Remove outdated or irrelevant information

### Resume Styling Best Practices

1. **Consistent Formatting**
   - Use consistent fonts and sizes
   - Maintain proper spacing and alignment
   - Use clear section headers

2. **Professional Appearance**
   - Choose a clean, readable font
   - Use subtle colors for emphasis
   - Ensure good contrast for readability

3. **Mobile-Friendly Design**
   - Test how your resume looks on mobile devices
   - Ensure text is readable at different sizes
   - Consider responsive design principles

## 🔧 Technical Details

### Dependencies

- **jQuery**: 1.12.0 for DOM manipulation and animations
- **Modernizr**: 2.8.3 for feature detection
- **Slick Carousel**: For image sliders
- **Animate Headline**: For text animations
- **Google Fonts**: Montserrat for typography

### Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Internet Explorer 11+

### Performance Optimization

- Images are optimized for web
- CSS and JS files are minified
- Fonts are loaded efficiently
- Responsive images for different screen sizes

## 🤝 Contributing

While this is a personal portfolio, suggestions and improvements are welcome:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 📞 Contact

- **Portfolio**: [https://faustorosado.github.io/my-portfolio](https://faustorosado.github.io/my-portfolio)
- **LinkedIn**: [linkedin.com/in/fausto-codes](https://linkedin.com/in/fausto-codes)
- **GitHub**: [github.com/FaustoRosado](https://github.com/FaustoRosado)
- **Email**: faustrosado@gmail.com

---

**Built with ❤️ by Fausto Rosado**

*Last updated: January 2025* 