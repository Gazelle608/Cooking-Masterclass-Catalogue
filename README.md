# README.md for Cooking Masterclass Catalogue

Create or replace the `README.md` file in your project root with this content:

```markdown
# 🍳 Cooking Masterclass Catalogue

A responsive Vue.js single-page application showcasing cooking classes with wishlist functionality, featuring South African Rand pricing.

## 📋 Project Overview

This project is a dynamic course catalogue for Cooking Masterclass, built with Vue 3. Users can browse available cooking classes, view details, and save their favorite courses to a wishlist.

### ✨ Features

- **Course Catalogue**: Dynamic cards displaying chef information, pricing, and skill levels
- **Wishlist Functionality**: Save favorite courses with a live counter
- **Sold Out Indicators**: Clear visibility for unavailable courses
- **Currency Support**: Prices displayed in South African Rands (ZAR)
- **Filtering**: Toggle between all courses and available-only courses
- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Interactive UI**: Hover effects and smooth animations

## 🚀 Live Demo

[Add your live demo link here after deployment]

## 🛠️ Technology Stack

- **Framework**: Vue 3 with Composition API
- **Build Tool**: Vite
- **Styling**: CSS3 with Grid & Flexbox
- **Icons**: Emoji-based icons
- **Images**: Unsplash for course thumbnails

## 📁 Project Structure

```
cooking-masterclass-catalogue/
├── src/
│   ├── components/
│   │   ├── Header.vue          # App header with wishlist counter
│   │   └── CourseCard.vue      # Individual course card component
│   ├── data/
│   │   └── courses.js          # Sample course data
│   ├── App.vue                 # Main application component
│   └── main.js                 # Application entry point
├── public/                     # Static assets
├── package.json                # Project dependencies and scripts
└── README.md                   # Project documentation
```

## ⚡ Installation & Setup

### Prerequisites
- Node.js (version 14 or higher)
- npm or yarn package manager

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/cooking-masterclass-catalogue.git
   cd cooking-masterclass-catalogue
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Run the development server**
   ```bash
   npm run dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:5173`

### Build for Production

```bash
# Build for production
npm run build

# Preview production build
npm run preview
```

## 🎯 How to Use

1. **Browse Courses**: Scroll through the available cooking classes
2. **View Details**: Each card shows chef, price, skill level, and availability
3. **Save Courses**: Click the "Save" button on available courses to add them to your wishlist
4. **Track Wishlist**: View your saved courses count in the header
5. **Filter Courses**: Use the "Available Only" filter to hide sold-out classes

## 📱 Features in Detail

### Course Information
- **Title & Chef**: Course name and instructor
- **Pricing**: Displayed in South African Rands (ZAR) with proper formatting
- **Skill Levels**: Color-coded badges (Beginner, Intermediate, Advanced)
- **Availability**: Clear "Sold Out" indicators for unavailable courses

### Wishlist System
- Real-time counter in the header
- Persistent within the current session
- Visual feedback when courses are saved/unsaved
- Sold-out courses cannot be added to wishlist

### Responsive Design
- **Desktop**: 3-column grid layout
- **Tablet**: 2-column grid layout  
- **Mobile**: Single-column stack layout

## 🎨 Customization

### Adding New Courses
Edit `src/data/courses.js` to add new courses:

```javascript
{
  id: 7,
  title: "Your Course Title",
  chef: "Chef Name",
  price: 1999.99, // ZAR price
  level: "Beginner", // Beginner, Intermediate, or Advanced
  available: true,
  image: "https://your-image-url.com"
}
```

### Styling
The application uses CSS custom properties and can be easily themed by modifying the color variables in component styles.

## 📸 Screenshots

[Add screenshots of your application here]

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Course images provided by [Unsplash](https://unsplash.com)
- Built with [Vue.js](https://vuejs.org/)
- Icons from Twemoji

## 📞 Support

If you have any questions or issues, please open an issue on the GitHub repository.

---

**Developed for Cooking Masterclass** 🍽️
```

## Key Sections Explained:

1. **Project Overview**: Brief description of what the app does
2. **Features**: Bullet points highlighting key functionality
3. **Technology Stack**: What technologies were used
4. **Installation**: Step-by-step setup instructions
5. **How to Use**: User instructions
6. **Customization**: How to modify the app
7. **Screenshots**: Placeholder for your app images

## After creating the README:

1. **Add and commit it**:
   ```bash
   git add README.md
   git commit -m "Add comprehensive README documentation"
   git push
   ```

2. **Take screenshots** of your application and add them to the README

3. **Update the repository URL** in the clone command

This README provides professional documentation that meets all the project requirements and helps others understand and run your project easily!
