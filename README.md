# Birthday Surprise Website 🎂✨

A beautiful, interactive birthday experience with multiple pages including letter, cake cutting, wishes, and music.

## Files Structure

- `index.html` - Landing page (redirects to main experience)
- `birthday_v2 (2).html` - Main birthday experience (Pages 1-5: Splash, Letter, Cake, Wish, Music)
- `birthday_surprises (1).html` - Birthday wishes cards page
- Audio files: `bargad.mp3`, `oce.mp3`, `If The World Was Ending.mp3`
- Images: `hello-kitty-hearts.gif`, `hello-kitty-spidey.webp`

## Features

### Main Experience (birthday_v2)
- **Page 1**: Animated splash screen with birthday greeting
- **Page 2**: Interactive envelope that opens to reveal a heartfelt letter with Elsa sticker
- **Page 3**: Interactive cake cutting with canvas drawing
- **Page 4**: Birthday wish with animated Sanrio character
- **Page 5**: Music player with 3 songs and album art

### Letter Card Features
- Landscape mode with 16:9 aspect ratio
- Aesthetic gradient pink border
- Caveat handwritten font for authentic feel
- Envelope completely disappears when letter opens
- Corner Elsa sticker decoration
- Smooth animations and transitions

### Wishes Cards Page
- Flip cards with Hello Kitty illustrations
- Progress tracking
- Confetti celebration
- Letter sealing feature
- Responsive design with accessibility features

## Deployment to Vercel

### Quick Deploy
1. Push this repository to GitHub
2. Go to [Vercel](https://vercel.com)
3. Click "New Project"
4. Import your GitHub repository
5. Vercel will auto-detect the configuration from `vercel.json`
6. Click "Deploy"

### Manual Deploy
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy from project directory
vercel

# Deploy to production
vercel --prod
```

## Local Testing

Simply open `index.html` in a web browser, or use a local server:

```bash
# Python 3
python -m http.server 8000

# Node.js (with http-server)
npx http-server

# Then open http://localhost:8000
```

## Responsive Design

- Desktop: Full 3D animations and effects
- Mobile: Optimized stacked layout for cards
- Tablet: Adaptive sizing with clamp() functions
- Accessibility: Keyboard navigation, ARIA labels, reduced motion support

## Browser Support

- Chrome/Edge (recommended)
- Firefox
- Safari
- Mobile browsers (iOS Safari, Chrome Mobile)

## Performance Optimizations

- Confetti throttled on low-power devices
- Reduced animations with `prefers-reduced-motion`
- Optimized for Save-Data mode
- Responsive images and fonts

---

Made with endless love 💕 