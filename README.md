# 🇺🇸 America's 250th Birthday Trivia Challenge

A beautiful, fully interactive trivia web application celebrating American history and the principles of liberty. Created for Sphere Education's America's 250th Birthday collection.

![Trivia Challenge](https://img.shields.io/badge/Status-Ready_to_Deploy-success)
![Version](https://img.shields.io/badge/Version-1.0-blue)
![License](https://img.shields.io/badge/License-MIT-green)

## 🎯 Overview

This single-page trivia game tests players' knowledge of American founding history, the Constitution, Declaration of Independence, Founding Fathers, and key principles of liberty and self-governance. The game features daily rotation, progressive difficulty, speed bonuses, and a modern, responsive design.

## ✨ Features

### Game Mechanics
- **7-Question Quiz** - Perfect length for engagement without fatigue
- **Daily Rotation** - New questions every day using seed-based randomization
- **Progressive Difficulty** - Questions get harder within each quiz AND across the week
  - Sunday = Easiest day
  - Saturday = Hardest day
- **15-Second Timer** - Creates urgency and excitement
- **Two-Strike System** - Players can make one mistake before game over
- **Speed Bonus** - Earn up to 50% extra points for quick answers
- **Randomized Answers** - Answer positions change every time

### Scoring System
- **Easy Questions**: 10 base points
- **Medium Questions**: 20 base points
- **Hard Questions**: 30 base points
- **Speed Bonus**: Up to 50% additional points based on remaining time

### Design & UX
- **Beautiful Gradient Background** - Blending Sphere's brand colors
- **Smooth Animations** - Professional transitions and effects
- **Responsive Design** - Perfect on desktop, tablet, and mobile
- **Modern UI** - Clean interface with rounded corners and elegant typography
- **Visual Feedback** - Pulsing timer, animated hearts, speed bonus notifications

### Content
- **21 Curated Questions** (7 easy, 7 medium, 7 hard)
- **10 Historical Fun Facts** - Displayed randomly after quiz completion
- **Educational Focus** - Covers American founding, Constitution, Declaration, and liberty principles

## 🚀 Installation & Deployment

### Option 1: Direct Deployment (Easiest)
1. Upload `americas-250th-trivia.html` to your web server
2. Access it through your browser - that's it!

### Option 2: GitHub Pages
1. Create a new repository on GitHub
2. Upload `americas-250th-trivia.html` and rename it to `index.html`
3. Go to Settings → Pages
4. Select your branch and save
5. Your game will be live at `https://yourusername.github.io/repository-name/`

### Option 3: Local Testing
1. Simply open `americas-250th-trivia.html` in any modern web browser
2. No server required for testing!

### Option 4: Netlify Drop
1. Go to [Netlify Drop](https://app.netlify.com/drop)
2. Drag and drop `americas-250th-trivia.html`
3. Get instant deployment with a live URL

## 🛠️ Technical Details

### Technologies Used
- **HTML5** - Semantic markup
- **CSS3** - Modern styling with gradients, animations, and flexbox
- **Vanilla JavaScript** - No frameworks required
- **Google Fonts** - Raleway font family
- **localStorage API** - Daily play tracking

### Browser Compatibility
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

### File Structure
```
americas-250th-trivia.html
├── HTML Structure
├── Embedded CSS Styles
└── Embedded JavaScript Logic
```

**Total Size**: ~45KB (single self-contained file)

## 🎨 Branding

### Colors
- **Primary**: `#2D1870` (Deep Purple) - Main brand color
- **Secondary**: `#7C756D` (Elegant Taupe) - Accent color
- **Success**: `#28a745` (Green) - Speed bonus notifications
- **Warning**: `#ff4757` (Red) - Timer warnings and lost lives

### Typography
- **Font Family**: Raleway (all weights)
- **Headings**: Bold weights (700-800)
- **Body Text**: Regular to medium weights (400-600)

## 📚 Content Customization

### Adding New Questions

Questions are stored in the `questionBank` object in the JavaScript section. Each difficulty level has its own array:

```javascript
const questionBank = {
    easy: [
        {
            question: "Your question here?",
            answers: ["Correct Answer", "Wrong 1", "Wrong 2", "Wrong 3"],
            correct: 0  // Index of correct answer
        }
    ],
    medium: [...],
    hard: [...]
};
```

**Guidelines:**
- Keep 7 questions per difficulty level for optimal balance
- Ensure answer index 0 is always the correct answer (randomization happens automatically)
- Test questions for clarity and accuracy

### Adding New Fun Facts

Fun facts appear at the end of each quiz:

```javascript
const funFacts = [
    "Your interesting historical fact here...",
    "Another fascinating detail...",
    // Add more facts
];
```

## ⚙️ How It Works

### Daily Rotation System
The game uses a **seed-based randomization** system to ensure:
- Everyone sees the same questions on the same day
- Questions rotate daily without server-side logic
- Difficulty distribution changes based on day of week

### localStorage Tracking
The game stores:
- `lastPlayedDate` - Prevents multiple plays per day
- `todayScore` - Player's most recent score

### Play Again Logic
When a player clicks "Play Again":
- The page reloads
- localStorage is checked
- If already played today, shows "come back tomorrow" screen
- If new day, allows new game

## 🔧 Customization Options

### Changing Colors
Search for hex colors in the CSS section and replace:
- `#2D1870` - Primary purple
- `#7C756D` - Secondary taupe

### Adjusting Difficulty Distribution
Modify the `selectDailyQuestions()` function to change how questions are distributed across the week.

### Changing Timer Duration
Find `timeRemaining = 15;` and adjust the value (in seconds).

### Modifying Speed Bonus
Locate the speed bonus calculation:
```javascript
const speedBonus = Math.floor(basePoints * 0.5 * (timeRemaining / 15));
```
Change `0.5` to adjust bonus percentage (0.5 = 50%).

## 📱 Mobile Optimization

The game automatically adapts to different screen sizes:
- **Desktop**: Full-width layout with side-by-side buttons
- **Tablet**: Optimized spacing and font sizes
- **Mobile**: Stacked layout, larger touch targets

## 🔗 External Links

The game includes two external links:
1. **Explore Sphere's 250th Collection** → `https://www.sphere-ed.org/collection/americas-250th-birthday`
2. **Sphere Education Initiatives** → `https://www.sphere-ed.org`

## 📊 Analytics Integration (Optional)

To add analytics, insert your tracking code before the closing `</head>` tag:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR-ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'YOUR-ID');
</script>
```

## 🐛 Troubleshooting

### "Already Played Today" shows incorrectly
- Clear browser localStorage: `localStorage.clear()` in console
- Check browser date/time settings

### Questions not randomizing
- Verify the seed-based randomization is working
- Check browser console for JavaScript errors

### Styling issues
- Ensure Google Fonts is loading (check network tab)
- Verify browser supports CSS Grid and Flexbox

### Timer not working
- Check JavaScript console for errors
- Ensure browser supports setInterval/clearInterval

## 📄 License

This project is open source and available for educational use by Sphere Education Initiatives and its partners.

## 🤝 Credits

**Developed for**: [Sphere Education Initiatives](https://www.sphere-ed.org)  
**Collection**: [America's 250th Birthday](https://www.sphere-ed.org/collection/americas-250th-birthday)  
**Version**: 1.0  
**Last Updated**: October 2025

## 💡 Future Enhancements

Potential features for future versions:
- Leaderboard system
- Social sharing capabilities
- Additional question packs
- Multiplayer mode
- Achievement badges
- Question difficulty ratings by community
- Audio effects
- Dark mode toggle

## 📞 Support

For questions, issues, or suggestions regarding this trivia application, please contact Sphere Education Initiatives through their website.

---

**Made with ❤️ for American history education**
