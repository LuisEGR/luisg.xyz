# Luis G - Personal Website

A modern, responsive personal website built with Svelte, showcasing projects, drone photography, and professional information.

## 🚀 Features

- **Modern Design**: Clean, responsive design with smooth animations
- **Project Showcase**: Filterable project gallery with technology tags
- **Drone Photography**: Interactive photo gallery with Google Drive integration
- **Skills Display**: Animated skill bars and technology proficiency
- **Contact Form**: Easy-to-use contact form with social links
- **Mobile Responsive**: Optimized for all device sizes
- **GitHub Pages Ready**: Automatic deployment via GitHub Actions

## 🛠️ Tech Stack

- **Frontend**: Svelte 4
- **Build Tool**: Vite
- **Styling**: CSS3 with modern features
- **TypeScript**: Full type safety
- **Deployment**: GitHub Pages + GitHub Actions

## 📦 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/luisg.xyz.git
   cd luisg.xyz
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run dev
   ```

4. **Build for production**
   ```bash
   npm run build
   ```

## 🎨 Customization

### Personal Information
Update the following files with your information:

- `src/components/About.svelte` - Personal bio and skills
- `src/components/Projects.svelte` - Your projects
- `src/components/Gallery.svelte` - Your drone photos
- `src/components/Contact.svelte` - Contact details and social links

### Styling
The design uses a modern color scheme with:
- Primary: `#2563eb` (Blue)
- Accent: `#fbbf24` (Yellow)
- Background: `#f9fafb` (Light Gray)

### Google Drive Integration
To add your drone photos:

1. Upload photos to Google Drive
2. Get shareable links (set to "Anyone with the link can view")
3. Update the `photos` array in `src/components/Gallery.svelte`

## 🚀 Deployment

### GitHub Pages (Recommended)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository settings
   - Navigate to "Pages"
   - Select "Deploy from a branch"
   - Choose `gh-pages` branch
   - Save

3. **Automatic Deployment**
   - The GitHub Actions workflow will automatically build and deploy on every push to `main`
   - Your site will be available at `https://yourusername.github.io/luisg.xyz`

### Manual Deployment

1. **Build the project**
   ```bash
   npm run build
   ```

2. **Deploy the `dist` folder** to your hosting provider

## 📁 Project Structure

```
luisg.xyz/
├── src/
│   ├── components/
│   │   ├── Header.svelte      # Navigation header
│   │   ├── Hero.svelte        # Hero section
│   │   ├── About.svelte       # About section
│   │   ├── Projects.svelte    # Projects showcase
│   │   ├── Gallery.svelte     # Photo gallery
│   │   ├── Contact.svelte     # Contact form
│   │   └── Footer.svelte      # Footer
│   ├── App.svelte             # Main app component
│   └── main.ts                # Entry point
├── .github/workflows/         # GitHub Actions
├── public/                    # Static assets
└── dist/                      # Build output
```

## 🎯 Key Features Explained

### Project Filtering
The projects section includes filtering by technology (Angular, Svelte, React) and featured projects.

### Photo Gallery
- Modal view for full-size images
- Category filtering (Landscapes, Urban, Nature)
- Google Drive integration for high-resolution photos

### Skills Visualization
Animated skill bars showing proficiency levels with custom colors for each technology.

### Contact Form
- Click-to-copy contact information
- Social media links
- Contact form (requires backend integration for functionality)

## 🔧 Development

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run check` - Type check with Svelte

### Adding New Sections

1. Create a new component in `src/components/`
2. Import and add it to `src/App.svelte`
3. Add navigation link in `src/components/Header.svelte`

## 📱 Mobile Optimization

The site is fully responsive with:
- Mobile-first design approach
- Touch-friendly navigation
- Optimized images and animations
- Proper viewport meta tags

## 🎨 Design System

### Colors
- Primary: `#2563eb`
- Secondary: `#fbbf24`
- Background: `#f9fafb`
- Text: `#1f2937`
- Muted: `#6b7280`

### Typography
- Font: Inter (system font fallback)
- Headings: 700 weight
- Body: 400 weight
- Line height: 1.6

### Spacing
- Container max-width: 1200px
- Section padding: 5rem
- Component spacing: 1rem-2rem

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- Built with [Svelte](https://svelte.dev/)
- Icons from [Material Design Icons](https://material.io/icons/)
- Deployed with [GitHub Pages](https://pages.github.com/)

---

**Made with ❤️ by Luis G**
