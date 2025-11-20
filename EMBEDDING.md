# Embedding Instructions

Step-by-step instructions for embedding the interactive map on different platforms.

## 📌 General Instructions

The map is a **standalone HTML file** that can be embedded in multiple ways:

1. **Iframe Embed** (Recommended) - Works on all platforms
2. **Direct Code Injection** - For platforms that support HTML/CSS/JS
3. **Hosted Page** - Upload to your server and link to it

---

## 🌐 Wix

### Method 1: HTML iframe Widget

1. Go to your Wix Editor
2. Click **Add** → **More** → **HTML iframe**
3. Click **Enter Code**
4. Paste this code:

```html
<iframe 
    src="https://your-domain.com/path/to/index.html" 
    width="100%" 
    height="700" 
    frameborder="0"
    style="border: none; border-radius: 12px;">
</iframe>
```

5. Replace `https://your-domain.com/path/to/index.html` with your actual file URL
6. Adjust `height="700"` to your preferred size
7. Click **Update**

### Method 2: Custom Code (Advanced)

1. Go to **Settings** → **Custom Code**
2. Add code to **Head** or **Body** section
3. Use the iframe method above

---

## 📝 WordPress

### Method 1: HTML Block (Gutenberg)

1. Add a new **HTML Block**
2. Paste the iframe code:

```html
<iframe 
    src="https://your-domain.com/path/to/index.html" 
    width="100%" 
    height="700" 
    frameborder="0"
    style="border: none; border-radius: 12px;">
</iframe>
```

3. Update the `src` URL to your hosted file
4. Publish

### Method 2: Custom HTML Widget (Classic)

1. Go to **Appearance** → **Widgets**
2. Add **Custom HTML** widget
3. Paste iframe code
4. Save

### Method 3: Page Template (Advanced)

1. Upload `index.html` to your WordPress theme folder
2. Create a custom page template
3. Include the file using `get_template_part()` or direct include

---

## 🎨 Squarespace

### Method 1: Code Block

1. Add a **Code Block** to your page
2. Paste the iframe code:

```html
<iframe 
    src="https://your-domain.com/path/to/index.html" 
    width="100%" 
    height="700" 
    frameborder="0"
    style="border: none; border-radius: 12px;">
</iframe>
```

3. Update the `src` URL
4. Save

### Method 2: Code Injection (Site-wide)

1. Go to **Settings** → **Advanced** → **Code Injection**
2. Add to **Footer** or **Page Header Code**
3. Use iframe method

---

## 💻 Custom HTML Website

### Method 1: Direct Include

Simply include the file in your HTML:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Website</title>
</head>
<body>
    <h1>My Page</h1>
    
    <!-- Include the map -->
    <iframe 
        src="map/index.html" 
        width="100%" 
        height="700" 
        frameborder="0">
    </iframe>
</body>
</html>
```

### Method 2: Copy Code Directly

1. Open `index.html`
2. Copy the entire content
3. Paste into your HTML page where you want the map
4. Adjust container styles as needed

---

## 📱 Shopify

### Method 1: Custom HTML Section

1. Go to **Online Store** → **Themes** → **Customize**
2. Add a **Custom HTML** section
3. Paste iframe code:

```html
<iframe 
    src="https://your-domain.com/path/to/index.html" 
    width="100%" 
    height="700" 
    frameborder="0"
    style="border: none;">
</iframe>
```

### Method 2: Theme Files

1. Upload `index.html` to your theme's `assets` folder
2. Reference it in a template file using Liquid

---

## 🔗 Webflow

1. Add an **Embed** element to your page
2. Paste the iframe code:

```html
<iframe 
    src="https://your-domain.com/path/to/index.html" 
    width="100%" 
    height="700" 
    frameborder="0"
    style="border: none;">
</iframe>
```

---

## ☁️ Hosting the File

### Option 1: Your Existing Website

1. Upload `index.html` to your web server
2. Note the full URL (e.g., `https://yoursite.com/maps/index.html`)
3. Use that URL in your iframe `src` attribute

### Option 2: GitHub Pages (Free)

1. Create a GitHub repository
2. Upload `index.html`
3. Enable GitHub Pages in repository settings
4. Use the GitHub Pages URL in your iframe

### Option 3: CDN (Cloudflare, AWS S3, etc.)

1. Upload to your CDN
2. Get the public URL
3. Use in iframe

### Option 4: Google Drive / Dropbox

1. Upload file to Google Drive or Dropbox
2. Get shareable link
3. Convert to direct download link
4. Use in iframe (may have limitations)

---

## 🎯 Responsive Sizing

For better mobile experience, use responsive iframe:

```html
<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe 
        src="https://your-domain.com/path/to/index.html" 
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none;"
        frameborder="0">
    </iframe>
</div>
```

---

## 🔒 Security Considerations

### Content Security Policy (CSP)

If your site has CSP headers, you may need to allow:

```
frame-src 'self' https://your-domain.com;
```

### Same-Origin Policy

If embedding from a different domain:
- Ensure CORS headers are set (if needed)
- Use HTTPS for both sites
- Consider using `sandbox` attribute for iframe security

---

## ✅ Testing Checklist

After embedding, verify:

- [ ] Map displays correctly
- [ ] Hover tooltips work
- [ ] Click functionality works
- [ ] Info panel appears on click
- [ ] Responsive on mobile devices
- [ ] No console errors
- [ ] Styling matches your site

---

## 🆘 Troubleshooting

### Map Not Loading

- Check file URL is correct and accessible
- Verify HTTPS/HTTP matches your site
- Check browser console for errors
- Ensure iframe is not blocked by CSP

### Styling Conflicts

- The map uses scoped styles, but parent page CSS might interfere
- Use iframe method to isolate styles completely
- Check z-index values if elements overlap

### Mobile Issues

- Ensure viewport meta tag is present
- Test touch events on actual devices
- Adjust iframe height for mobile screens

---

## 📞 Need Help?

Refer to the main `README.md` for customization options and the inline code comments in `index.html` for technical details.

