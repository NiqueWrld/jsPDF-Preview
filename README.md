# jsPDF Live Preview

A real-time PDF generator and preview tool built with jsPDF library. This project allows you to write jsPDF code and see the generated PDF instantly in your browser.

## Features

- **Live Preview**: Real-time PDF generation as you type
- **Interactive Code Editor**: Built-in textarea with syntax highlighting-friendly font
- **Automatic Updates**: PDF updates automatically after 500ms of inactivity
- **Manual Generation**: Manual PDF generation button for immediate updates
- **Error Handling**: Graceful error handling with console logging
- **Memory Management**: Automatic cleanup of blob URLs to prevent memory leaks
- **Responsive Design**: Clean, modern interface using Tailwind CSS

## How to Use

1. **Open the Project**: Open `index.html` in your web browser
2. **Write jsPDF Code**: Enter your jsPDF code in the textarea
   - The `doc` object is already initialized for you
   - Use standard jsPDF syntax and methods
3. **View Results**: The PDF will automatically generate and display in the preview iframe
4. **Manual Generation**: Click the "Manual Generate" button if needed

## Example Code

Here's a simple example to get you started:

```javascript
const pageWidth = doc.internal.pageSize.getWidth();
const pageHeight = doc.internal.pageSize.getHeight();

// Add a title
doc.setFontSize(20);
doc.setFont('helvetica', 'bold');
doc.text('Hello World!', pageWidth / 2, 50, { align: 'center' });

// Add some content
doc.setFontSize(12);
doc.setFont('helvetica', 'normal');
doc.text('This is a sample PDF generated with jsPDF.', 20, 80);

// Add a rectangle
doc.setDrawColor(0, 0, 255);
doc.rect(20, 100, 100, 50);
```

## Project Structure

```
jsPDF Preview/
├── index.html          # Main application file
├── README.md           # This documentation
└── (any additional assets)
```

## Technical Details

### Dependencies
- **jsPDF**: PDF generation library (loaded via CDN)
- **Tailwind CSS**: Utility-first CSS framework (loaded via CDN)

### Configuration
- **PDF Format**: A4 landscape (297x210mm) by default
- **Orientation**: Landscape
- **Units**: Millimeters (mm)
- **Auto-update Delay**: 500ms after typing stops

### Browser Compatibility
- Modern browsers with ES6+ support
- Requires JavaScript enabled
- Works with Chrome, Firefox, Safari, and Edge

## Customization

### Changing PDF Format
Modify the jsPDF initialization in the JavaScript section:

```javascript
const doc = new jsPDF({
    orientation: 'portrait', // or 'landscape'
    unit: 'mm',             // or 'pt', 'in', 'cm'
    format: [210, 297]      // or 'a4', 'letter', etc.
});
```

### Adjusting Auto-update Timing
Change the debounce timer in the `debounceGeneratePDF` function:

```javascript
debounceTimer = setTimeout(generatePDF, 1000); // 1 second delay
```

## Common Use Cases

1. **Certificate Generation**: Create professional certificates with logos and styling
2. **Report Generation**: Generate formatted reports with tables and charts
3. **Invoice Creation**: Design invoice templates with company branding
4. **Form Creation**: Build fillable PDF forms
5. **Prototype Testing**: Quick PDF layout testing and experimentation

## Tips for Better Development

1. **Use Comments**: Comment your jsPDF code for better readability
2. **Test Incrementally**: Build your PDF step by step using the live preview
3. **Check Console**: Monitor the browser console for any errors
4. **Save Often**: Copy your working code to external files for backup
5. **Experiment**: Try different jsPDF methods and see immediate results

## Troubleshooting

### PDF Not Generating
- Check for JavaScript errors in the browser console
- Ensure your jsPDF code syntax is correct
- Verify the textarea is not empty

### Blank PDF
- Make sure you're calling methods on the `doc` object
- Check if your coordinates are within the page boundaries
- Verify text/images are positioned correctly

### Performance Issues
- Avoid complex operations in large loops
- Consider reducing image sizes if using base64 images
- Clear the textarea if you notice memory issues

## License

This project is open source and available under the MIT License.

## Contributing

Feel free to fork this project and submit pull requests for improvements!

## Support

For jsPDF-specific questions, refer to the [official jsPDF documentation](https://github.com/parallax/jsPDF).
