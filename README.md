# Fluxus FC — Kit Creator

**🎯 MILESTONE: STREAMLINED INTERFACE - READY FOR OBJKT.COM DEPLOYMENT**

A single-file, client-only interactive HTML app that runs inside objkt.com's interactive token iframe **and** runs in a generic test environment. Users can place images (local uploads or their Tezos NFT images) onto a 3D shirt, move/scale/rotate/flip them, and toggle a symmetry grid.

**Status:** ✅ Complete - Streamlined interface ready for production deployment

## Features

### 🎨 3D Shirt Designer
- **3D shirt viewer** with black background and white shirt
- **Decal placement**: drag to move, wheel/pinch to scale, two-finger rotate
- **Grid toggle** (light blue) for symmetry assistance
- **Position-based exclusion** - grid appears on main shirt body, excludes collar and inside parts
- **Streamlined interface** - removed complex layer management and fabric controls

### 💼 Wallet Integration
- **OBJKT Integration**: If embedded on objkt.com, uses parent wallet via postMessage
- **Beacon Fallback**: Connect wallet button for standalone use
- **NFT Gallery**: Shows your Tezos NFTs as draggable thumbnails
- **Artworks Panel**: Collapsible NFT panel for mobile-friendly experience

### 📱 Mobile Friendly
- **Responsive design** with collapsible panels
- **Touch controls**: pinch to scale, two-finger rotate
- **Large tap targets** for easy interaction
- **Mobile-optimized UI** with proper viewport handling

### 🎯 Streamlined Interface
- **Minimal sidebar** with only essential tools
- **Grid system** with position-based exclusion
- **Clean design** focused on core functionality
- **Ready for objkt.com** deployment

## 🎯 Current Milestone: Streamlined Interface

**Date:** September 25, 2025  
**Status:** ✅ COMPLETE - Ready for objkt.com deployment

### What's New:
- ✅ **Grid System Working** - Position-based exclusion excludes collar and inside parts
- ✅ **Interface Streamlined** - Removed layers, fabric controls, and export buttons
- ✅ **Clean Sidebar** - Only essential tools remain (Grid, Connect Wallet, Mint)
- ✅ **3D Model Loading** - GLB model loads correctly with Three.js ES modules
- ✅ **Material System** - Dynamic switching between plain and grid materials

### Current Interface:
- **TOOLS**: Grid toggle, Connect Wallet, Mint button
- **UPLOAD IMAGE**: File input for local images
- **NFTS IN WALLET**: Collapsible NFT gallery

## Quick Start

### Local Testing
1. Put these files in a folder:
   - `index.html` (main app file)
   - `objkt-3d-viewport.glb` (3D shirt model - optional, app has fallback)
   - `fluxus-fc-logo.png` (brand logo - optional)
2. Double-click `index.html` or serve with any static server
3. No build step required - uses CDN imports for Three.js and Beacon

### OBJKT Minting
1. Zip the folder containing all files
2. Mint as an **Interactive / HTML** token on objkt.com
3. The app will run inside their sandbox
4. If parent page provides wallet via postMessage, **Artworks** flow engages
5. Otherwise, Beacon fallback remains available

## File Structure

```
fluxus/
├── index.html              # Main application file
├── objkt-3d-viewport.glb   # 3D shirt model (optional)
├── fluxus-fc-logo.png      # Brand logo (optional)
└── README.md               # This file
```

## Usage Instructions

### Adding Images
1. **Upload**: Use the file input to select local images
2. **NFTs**: Connect wallet and drag thumbnails from the gallery
3. **Placement**: Tap on the shirt to place images
4. **Editing**: Select layers to move, scale, rotate, or flip

### Controls
- **Mouse/Touch**: Drag to move decals
- **Scroll/Pinch**: Scale images
- **Two-finger rotate**: Rotate images on mobile
- **Layer buttons**: Fine-tune positioning and effects

### Wallet Features
- **Artworks Button**: Shows when connected to OBJKT or Beacon
- **NFT Gallery**: Displays your Tezos NFT collection
- **Drag & Drop**: Drag NFT thumbnails onto the shirt

## Technical Details

### Dependencies
- **Three.js**: 3D rendering and scene management
- **Beacon SDK**: Tezos wallet connection
- **TZKT API**: NFT metadata fetching
- **IPFS**: NFT image resolution

### Browser Support
- Modern browsers with WebGL support
- ES6 modules support required
- Touch events for mobile interaction

### PostMessage Protocol
The app uses a generic postMessage protocol:
- Sends: `{ type: 'FLUXUS_REQUEST_WALLET' }`
- Receives: `{ type: 'OBJKT_WALLET', address: 'tz1...' }`
- Sends: `{ type: 'FLUXUS_OPEN_LOGIN' }` for login requests

## Development Notes

### Fallbacks
- **3D Model**: Falls back to sphere if GLB file missing
- **Logo**: Hides logo if PNG file missing
- **Wallet**: Falls back to Beacon if OBJKT wallet unavailable

### Performance
- Optimized for mobile devices
- Efficient 3D rendering with proper culling
- Lazy loading of NFT thumbnails
- Responsive design with proper viewport handling

### Security
- CORS-friendly image loading
- Safe postMessage communication
- No sensitive data storage

## Customization

### Styling
- CSS custom properties for easy theming
- Responsive grid layout
- Modern glassmorphism design

### 3D Model
- Replace `objkt-3d-viewport.glb` with your own shirt model
- Ensure proper UV mapping for decal placement
- Optimize for web performance

### Branding
- Replace `fluxus-fc-logo.png` with your logo
- Update title and branding in HTML
- Customize color scheme via CSS variables

## Troubleshooting

### Common Issues
1. **3D model not loading**: App will use sphere fallback
2. **Wallet connection fails**: Check Beacon SDK availability
3. **NFTs not loading**: Verify TZKT API access
4. **Mobile issues**: Ensure proper viewport meta tag

### Browser Compatibility
- Requires WebGL support
- ES6 modules required
- Touch events for mobile features

## License

This project is open source and available under the MIT License.

## Support

For issues or questions, please refer to the GitHub repository or contact the development team.
