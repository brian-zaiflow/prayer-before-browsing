# Orthodox Prayer Before Browsing

A simple intervention page that displays an icon of Christ and the Jesus Prayer before you browse the internet. Designed to work with iOS Shortcuts as a moment of reflection before opening Safari or other browsers.

## Setup

### 1. Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g., `prayer-before-browsing`)
2. Upload `index.html` to the repository
3. Go to **Settings** → **Pages**
4. Under "Source", select **main** branch and **/ (root)**
5. Click **Save**
6. Your page will be live at: `https://yourusername.github.io/prayer-before-browsing/`

### 2. Set Up iOS Shortcut Automation

1. Open the **Shortcuts** app on your iPhone
2. Go to the **Automation** tab
3. Tap **+** → **App**
4. Select **Safari** (and any other browsers you use: Chrome, Firefox, etc.)
5. Choose **"Is Opened"**
6. Set to **"Run Immediately"**
7. Add action: **"Open URLs"**
8. Enter your GitHub Pages URL: `https://yourusername.github.io/prayer-before-browsing/`
9. Tap **Done**

Now whenever you open Safari, it will first open the prayer page.

## Customization

### Change the Wait Time

Edit the `WAIT_SECONDS` value in the `<script>` section:

```javascript
const WAIT_SECONDS = 15;  // Change to your preferred duration
```

### Use a Different Icon

Replace the image URL in the `<img>` tag, or save your own icon as `icon.jpg` in the same folder:

```html
<img src="icon.jpg" alt="Icon">
```

Some suggested icons (public domain):
- [Christ Pantocrator (Sinai)](https://commons.wikimedia.org/wiki/File:Spas_vsederzhitel_sinay.jpg)
- [Theotokos of Vladimir](https://commons.wikimedia.org/wiki/File:Theotokos_of_Vladimir.jpg)
- [Christ the Saviour (Andrei Rublev)](https://commons.wikimedia.org/wiki/File:Spas_vsederzhitel.jpg)

### Change the Prayer

Edit the prayer text in the HTML:

```html
<p class="prayer-text">
    Lord Jesus Christ,<br>
    Son of God,<br>
    have mercy on me,<br>
    <em>a sinner.</em>
</p>
```

Other Orthodox prayers you might use:
- **Trisagion**: "Holy God, Holy Mighty, Holy Immortal, have mercy on us."
- **Prayer Before Reading**: "Illumine our hearts, O Master Who lovest mankind..."

### Change the Instruction

```html
<p class="instruction">
    Pray this three times before continuing.
</p>
```

## How It Works

1. You tap Safari
2. iOS Shortcut automation triggers
3. Opens the prayer page instead
4. You see the icon and prayer with a 15-second countdown
5. After praying and waiting, you tap "Continue"
6. You close the tab and proceed to browse

## Limitations

- Safari still opens in the background (iOS doesn't allow true blocking)
- User can always skip by switching apps
- In-app browsers (links from other apps) won't trigger the automation

This is designed as a **voluntary friction tool**, not a blocker. The goal is to create a moment of reflection, not to make browsing impossible.

## License

Public domain. Use freely.