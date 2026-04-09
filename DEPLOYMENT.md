# NBCraft PWA Deployment Guide

## Overview
NBCraft is now a Progressive Web App (PWA) that can be installed and works offline. This guide shows you how to deploy it to the internet.

## Files Created
- `index.html` - Landing page
- `nbcraft.html` - Game page
- `manifest.json` - PWA manifest
- `sw.js` - Service worker for offline support
- `icons/` - App icons for all sizes
- `nbcraft.js/wasm/data` - Game files
- `game/` - Minecraft assets

## Local Testing
```bash
cd web_dist
python3 -m http.server 8080
```
Visit http://localhost:8080 to test.

## Deployment Options

### 1. GitHub Pages (Free)
1. Create a new GitHub repository
2. Push all files from `web_dist/` to the repository
3. Enable GitHub Pages in repository settings
4. Access at `https://username.github.io/repository-name`

### 2. Netlify (Free)
1. Sign up at netlify.com
2. Drag and drop the `web_dist` folder
3. Get a free subdomain like `nbcraft-game.netlify.app`

### 3. Vercel (Free)
1. Sign up at vercel.com
2. Connect your GitHub repository
3. Automatic deployment with every push

### 4. Firebase Hosting (Free tier)
1. Create Firebase project
2. Install Firebase CLI: `npm install -g firebase-tools`
3. Run: `firebase init` and `firebase deploy`

### 5. Traditional Web Hosting
Upload the `web_dist` folder contents to any web host.

## PWA Features
- ✅ Installable on mobile/desktop
- ✅ Works offline with service worker
- ✅ Responsive design
- ✅ App icons for all platforms
- ✅ Fullscreen mode
- ✅ Landscape orientation optimized

## URL Structure
- `/` - Landing page
- `/nbcraft.html` - Direct game access
- `/manifest.json` - PWA manifest
- `/sw.js` - Service worker

## Browser Support
- Chrome/Edge: Full PWA support
- Safari: PWA support (iOS 11.3+)
- Firefox: Good support

## Testing PWA Features
1. Open in Chrome/Edge
2. Look for "Install" icon in address bar
3. Install as app
4. Test offline functionality

## Performance Tips
- The game assets are ~50MB (cached by service worker)
- Initial load may take 30-60 seconds
- Subsequent loads are instant
- Consider CDN for asset delivery
