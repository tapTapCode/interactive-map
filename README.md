# Interactive Regional Map

A standalone, self-contained interactive map solution that works on **any website platform** (Wix, WordPress, Squarespace, custom sites, etc.). Built with pure HTML, CSS, and JavaScript - no dependencies required.

## ✨ Features

- **100% Standalone** - Single HTML file, no external dependencies
- **Platform Agnostic** - Works on Wix, WordPress, Squarespace, or any website
- **Interactive** - Hover and click functionality with smooth animations
- **Responsive** - Works perfectly on desktop and mobile devices
- **Customizable** - Easy-to-update data structure for your regions
- **Modern UI** - Clean design with tooltips and info panels
- **Accessible** - Keyboard navigation and screen reader friendly

## 🚀 Quick Start

### Option 1: Direct Embedding (iframe)

1. Upload `index.html` to your web hosting or CDN
2. Embed using an iframe:

```html
<iframe 
    src="https://your-domain.com/path/to/index.html" 
    width="100%" 
    height="700" 
    frameborder="0"
    style="border-radius: 12px;">
</iframe>
```

### Option 2: Code Injection (Wix, WordPress, Squarespace)

1. Copy the entire contents of `index.html`
2. In your website builder:
   - **Wix**: Add HTML iframe widget → Paste code
   - **WordPress**: Use HTML block or custom HTML widget → Paste code
   - **Squarespace**: Add Code Block → Paste code
   - **Custom Site**: Include directly in your HTML

### Option 3: Standalone Page

Simply open `index.html` in a web browser - it works completely offline!

## 📋 Customization Guide

### Step 1: Update Map Data

Open `index.html` and find the `mapData` object (around line 200). This is where you configure your regions:

```javascript
const mapData = {
    // Set your SVG viewBox dimensions
    viewBox: "0 0 800 600",
    
    // Define your regions
    regions: [
        {
            id: "region1",                    // Unique ID
            name: "North Region",             // Display name
            path: "M 100 100 L 300 100...",  // SVG path data
            data: {
                population: "125,000",
                area: "2,500 sq mi",
                description: "Your description here",
                services: ["Service 1", "Service 2"],
                contact: "email@example.com"
            }
        },
        // Add more regions...
    ]
};
```

### Step 2: Get SVG Path Data

To create your custom map:

1. **Use a vector graphics tool** (Adobe Illustrator, Inkscape, Figma)
2. **Draw your regions** as separate shapes
3. **Export as SVG** or copy the path data
4. **Extract path data** from the SVG `<path d="...">` attribute

**Example SVG Path:**
```svg
<path d="M 100 100 L 300 100 L 300 250 L 100 250 Z"/>
```

**How to read:**
- `M` = Move to (start point)
- `L` = Line to
- `Z` = Close path

### Step 3: Customize Colors

Edit the CSS in the `<style>` section to match your brand:

```css
.region {
    fill: #e0e0e0;        /* Default color */
}

.region:hover {
    fill: #4a90e2;        /* Hover color */
}

.region.selected {
    fill: #27ae60;        /* Selected color */
}
```

### Step 4: Customize Data Fields

Modify the `data` object structure to include your custom fields:

```javascript
data: {
    // Add any fields you need
    population: "125,000",
    revenue: "$2.5M",
    manager: "John Doe",
    phone: "(555) 123-4567",
    // ... more fields
}
```

Then update the `showInfoPanel()` method to display your custom fields.

## 📁 File Structure

```
interactive-map/
├── index.html          # Main standalone file (everything in one file)
├── README.md          # This documentation
└── examples/          # Example maps (optional)
    └── california.html
```

## 🎨 Styling Options

### Change Map Size

Adjust the container width in CSS:

```css
.map-container {
    max-width: 1200px;  /* Change to your preferred width */
}
```

### Change Tooltip Style

Modify the `.tooltip` class:

```css
.tooltip {
    background: rgba(0, 0, 0, 0.9);  /* Background color */
    color: white;                     /* Text color */
    border-radius: 8px;              /* Corner radius */
}
```

### Change Animation Speed

Adjust transition durations:

```css
.region {
    transition: all 0.3s ease;  /* Change 0.3s to your preferred speed */
}
```

## 🔧 Advanced Customization

### Add Click Actions

In the `handleClick()` method, add custom actions:

```javascript
handleClick(element) {
    // ... existing code ...
    
    // Add your custom action
    if (region.data.url) {
        window.open(region.data.url, '_blank');
    }
    
    // Or trigger a custom event
    window.dispatchEvent(new CustomEvent('regionSelected', {
        detail: region
    }));
}
```

### Add Search Functionality

Add a search input and filter regions:

```javascript
function searchRegions(query) {
    const filtered = mapData.regions.filter(region => 
        region.name.toLowerCase().includes(query.toLowerCase())
    );
    // Highlight matching regions
}
```

### Add Zoom Functionality

Implement pan and zoom using SVG transforms:

```javascript
let scale = 1;
function zoomIn() {
    scale *= 1.2;
    svg.style.transform = `scale(${scale})`;
}
```

## 📱 Responsive Design

The map is fully responsive and includes:
- Mobile-friendly tooltips
- Responsive info panel
- Touch-friendly click areas
- Adaptive sizing

## 🌐 Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 📝 Example Use Cases

- **Service Area Maps** - Show coverage areas for businesses
- **County/Regional Maps** - Display administrative regions
- **Sales Territory Maps** - Visualize sales regions
- **Event Location Maps** - Highlight event venues
- **Property Maps** - Show property boundaries
- **Delivery Zone Maps** - Display delivery coverage

## 🐛 Troubleshooting

### Map Not Showing

1. Check that SVG paths are valid
2. Verify viewBox matches your SVG dimensions
3. Check browser console for JavaScript errors

### Tooltip Not Appearing

1. Ensure `data-region-id` matches region `id`
2. Check that mouse events are not blocked
3. Verify CSS z-index values

### Styling Issues

1. Clear browser cache
2. Check for CSS conflicts with parent page
3. Use browser DevTools to inspect elements

## 📄 License

This code is provided as-is for use in your projects. Feel free to modify and customize as needed.

## 💡 Tips

1. **Test on multiple devices** - Always test responsive behavior
2. **Optimize SVG paths** - Use tools to simplify complex paths
3. **Keep data updated** - Regularly update region information
4. **Performance** - For maps with 100+ regions, consider lazy loading
5. **Accessibility** - Add ARIA labels for screen readers

## 🤝 Support

For questions or customization help, refer to the code comments in `index.html` - everything is well-documented inline.

---

**Ready to use?** Just customize the `mapData` object with your regions and you're good to go! 🎉

