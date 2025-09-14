# Avalara Zombie Fixer - Deployment Ready

A fun, interactive zombie-themed quiz game that teaches tax compliance concepts for reviving "zombie" businesses.

![Game Screenshot](https://github.com/user-attachments/assets/48f50bb9-b7d0-4583-bc95-fcbccf9952b7)

## Features

- 🧟 Zombie-themed UI with animated background elements
- 📊 Real-time score tracking and lives system
- 🎯 Wave-based progression system
- 🎮 Two game modes: Training and Live (API)
- 📱 Fully responsive design for mobile and desktop
- 🎨 Dark theme with green terminal-style aesthetics

## Game Modes

### Training Mode (Default)
- Uses built-in question set about tax compliance
- Perfect for offline use or testing
- 6 sample questions covering zombie business revival topics

### Live Mode (API Integration)
- Fetches questions from external API
- Requires API endpoint configuration
- Falls back to training mode if API fails

## Deployment

### Quick Deploy (Static Hosting)

1. **Upload to any static hosting service:**
   - Netlify: Drag and drop the `index.html` file
   - Vercel: Connect GitHub repo and deploy
   - GitHub Pages: Enable in repository settings
   - Any web server: Upload `index.html` to web root

2. **No build process required** - it's a single HTML file with embedded CSS and JavaScript

### API Configuration (Optional)

To enable live mode with API questions:

```javascript
const CONFIG = {
    MODE: 'live',
    API_URL: 'https://your-api-endpoint.com/questions',
    API_TOKEN: 'your-api-token-here' // Optional
};
```

Expected API response format:
```json
{
    "prompt": "Question text here?",
    "options": ["Option 1", "Option 2", "Option 3", "Option 4"],
    "correct": 1,
    "doc": "Explanation of the correct answer"
}
```

### Local Development

```bash
# Start local server
python3 -m http.server 8000

# Open in browser
open http://localhost:8000/index.html
```

## File Structure

```
/
├── index.html          # Complete game application
├── README.md          # This file
└── trying-again       # Original code fragments (for reference)
```

## Browser Compatibility

- Chrome/Chromium 60+
- Firefox 60+
- Safari 12+
- Edge 79+

## Game Controls

- **Start Game**: Begin a new game session
- **Reset**: Return to initial state
- **Mode Selection**: Switch between Training and Live modes
- **Answer Selection**: Click on any option to answer

## Scoring System

- **+10 points** for each correct answer
- **-1 life** for each incorrect answer
- **Game Over** when all lives are lost
- **Infinite waves** - see how high you can score!

## Customization

The game is easily customizable:

- **Questions**: Modify the `TRAINING_SET` array
- **Styling**: Update the CSS variables and classes
- **Scoring**: Adjust point values in the `answerQuestion` function
- **Lives**: Change initial lives in the `start` function

## Production Notes

- Single file deployment - no external dependencies
- Optimized for performance with CSS animations
- Mobile-first responsive design
- Graceful API fallback handling
- SEO-friendly with proper meta tags