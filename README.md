# Dynamic Email Signature Generator

A flexible and configurable email signature generator that allows users to create professional email signatures based on company templates and configurations.

## Features

- **Dynamic Configuration**: Load company settings from JSON configuration files
- **Template-Based**: Use HTML templates with placeholders for easy customization
- **Real-time Preview**: See signature updates as you type
- **Multiple Companies**: Support for multiple companies with different branding
- **Cross-platform Instructions**: Step-by-step installation guides for various email clients
- **Copy to Clipboard**: One-click copying with HTML formatting preserved
- **Responsive Design**: Works on desktop and mobile devices
- **Loading States**: User-friendly loading indicators and error handling

## Project Structure

```
email-signature-generator/
├── index.html                 # Main application file
├── config.json               # Company configurations
├── signature-template.html    # HTML template with placeholders
├── README.md                 # This documentation
└── images/                   # Assets directory
    ├── favicon/              # Favicon files
    ├── tutorials/            # Tutorial screenshots
    ├── logotipo-grupo-take5.svg
    ├── logotipo-grupo-take5.png
    ├── email.png
    ├── phone.png
    └── website.png
```

## Configuration

### Company Configuration (config.json)

The `config.json` file contains an array of company configurations:

```json
[
    {
        "id": "company-id",
        "name": "Company Name",
        "website": "https://www.company.com",
        "websiteDisplay": "company.com",
        "logo": "images/company-logo.png",
        "logoWidth": 83,
        "logoHeight": 45,
        "borderColor": "#33B16B",
        "websiteColor": "#33B16B",
        "emailIcon": "images/email.png",
        "phoneIcon": "images/phone.png",
        "websiteIcon": "images/website.png",
        "signatureTemplate": "signature-template.html",
        "banner": "images/company-banner.png",
        "bannerUrl": "https://www.company.com",
        "bannerWidth": 230,
        "bannerHeight": 50
    }
]
```

#### Configuration Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | string | Unique identifier for the company |
| `name` | string | Display name of the company |
| `website` | string | Full website URL |
| `websiteDisplay` | string | Shortened website display text |
| `logo` | string | Path to company logo image |
| `logoWidth` | number | Logo width in pixels |
| `logoHeight` | number | Logo height in pixels |
| `borderColor` | string | Hex color for signature borders |
| `websiteColor` | string | Hex color for website links |
| `emailIcon` | string | Path to email icon |
| `phoneIcon` | string | Path to phone icon |
| `websiteIcon` | string | Path to website icon |
| `signatureTemplate` | string | Path to HTML template file |
| `banner` | string | Path to banner image |
| `bannerUrl` | string | URL banner should link to |
| `bannerWidth` | number | Banner width in pixels |
| `bannerHeight` | number | Banner height in pixels |

### Signature Template

The signature template is an HTML file with placeholders that get replaced with actual data:

#### Available Placeholders

| Placeholder | Description |
|-------------|-------------|
| `[NAME]` | User's full name |
| `[JOB_TITLE]` | User's job title |
| `[EMAIL]` | User's email address |
| `[PHONE]` | User's phone number |
| `[COMPANY_NAME]` | Company name from config |
| `[WEBSITE]` | Company website URL |
| `[WEBSITE_DISPLAY]` | Company website display text |
| `[LOGO]` | Company logo path |
| `[LOGO_WIDTH]` | Logo width |
| `[LOGO_HEIGHT]` | Logo height |
| `[BORDER_COLOR]` | Border color |
| `[WEBSITE_COLOR]` | Website link color |
| `[EMAIL_ICON]` | Email icon path |
| `[PHONE_ICON]` | Phone icon path |
| `[WEBSITE_ICON]` | Website icon path |
| `[BANNER]` | Banner image path |
| `[BANNER_URL]` | Banner link URL |
| `[BANNER_WIDTH]` | Banner width |
| `[BANNER_HEIGHT]` | Banner height |

## Installation

1. **Clone or download** the project files to your web server
2. **Configure companies** by editing `config.json`
3. **Add company assets** (logos, icons) to the `images/` directory
4. **Customize templates** if needed by modifying `signature-template.html`
5. **Serve the files** through a web server (required for loading external files)

### Local Development

For local development, you can use a simple HTTP server:

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server

# Using PHP
php -S localhost:8000
```

Then open `http://localhost:8000` in your browser.

## Usage

1. **Select a Company**: Choose from the dropdown list of configured companies
2. **Fill Personal Information**: Enter your name, job title, email, and phone
3. **Preview**: See the signature update in real-time in the preview panel
4. **Copy Signature**: Click "Copiar Assinatura" to copy the HTML signature
5. **Install**: Use the installation guide for your email client

## Adding New Companies

To add a new company:

1. **Add company configuration** to `config.json`:
   ```json
   {
       "id": "new-company",
       "name": "New Company",
       "website": "https://www.newcompany.com",
       "websiteDisplay": "newcompany.com",
       "logo": "images/new-company-logo.png",
       "logoWidth": 100,
       "logoHeight": 50,
       "borderColor": "#FF6B35",
       "websiteColor": "#FF6B35",
       "emailIcon": "images/email.png",
       "phoneIcon": "images/phone.png",
       "websiteIcon": "images/website.png",
       "signatureTemplate": "signature-template.html",
       "banner": "images/new-company-banner.png",
       "bannerUrl": "https://www.newcompany.com",
       "bannerWidth": 230,
       "bannerHeight": 50
   }
   ```

2. **Add company assets** to the `images/` directory
3. **Create custom template** (optional) if the company needs a different layout

## Creating Custom Templates

To create a custom signature template:

1. **Copy** `signature-template.html` to a new file (e.g., `custom-template.html`)
2. **Modify** the HTML structure and styling as needed
3. **Use placeholders** for dynamic content (see placeholder list above)
4. **Update** the company configuration to reference the new template
5. **Test** the template with the generator

### Template Best Practices

- Use **table-based layouts** for better email client compatibility
- Include **inline CSS** for styling
- Keep **images optimized** and properly sized
- Test with **multiple email clients**
- Use **web-safe fonts** (Arial, sans-serif)

## Supported Email Clients

The generator includes installation instructions for:

- **Gmail** (Web)
- **Apple Mail** (macOS)
- **Mail App** (iOS)
- **General Webmail** clients

## Browser Compatibility

- **Modern browsers** with ES6+ support
- **Chrome** 60+
- **Firefox** 55+
- **Safari** 12+
- **Edge** 79+

## Dependencies

- **Vue.js 3** (loaded from CDN)
- **Tailwind CSS** (loaded from CDN)

## Troubleshooting

### Common Issues

**Configuration not loading**
- Ensure `config.json` is valid JSON
- Check browser console for errors
- Verify file paths are correct

**Template not displaying**
- Check template file path in configuration
- Ensure template file exists and is accessible
- Verify placeholder syntax in template

**Images not showing**
- Check image file paths in configuration
- Ensure images are in the correct directory
- Verify image file formats (PNG, JPG, SVG)

**Copy function not working**
- Modern browsers required for full functionality
- Some browsers may require user interaction
- Check browser permissions for clipboard access

### Development Tips

- Use browser developer tools to debug issues
- Check the Network tab for failed file loads
- Validate JSON configuration files
- Test templates with different data combinations

## Contributing

To contribute to this project:

1. **Fork** the repository
2. **Create** a feature branch
3. **Make** your changes
4. **Test** thoroughly
5. **Submit** a pull request

## License

This project is open source and available under the [MIT License](LICENSE).

## Support

For support and questions:

- Check the troubleshooting section above
- Review browser console for error messages
- Ensure all file paths and configurations are correct
- Test with a simple HTTP server for local development

---

**Note**: This generator requires a web server to function properly due to CORS restrictions when loading external files. It cannot be run directly by opening the HTML file in a browser.