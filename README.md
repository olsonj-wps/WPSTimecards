# TimeClock Plus to WPS Payroll Converter

A browser-based tool for converting TimeClock Plus "Payroll Detail" HTML reports into Worcester Public Schools 6-Hour Drivers Time Sheets.

![Screenshot](screenshot.png)

## Features

- **Drag and Drop Upload**: Simply drop your TimeClock Plus HTML export file
- **Editable Hours**: All hours fields are editable before export
- **Per-Row Comments**: Add notes for individual employees
- **Multiple Export Formats**:
  - WPS Template CSV
  - Formatted Excel (.xls)
  - Workday EIB CSV
- **Supervisor Sign-off**: Include certification and supervisor name in exports
- **Demo Mode**: Pre-loaded sample data for testing

## Usage

### Option 1: Use Directly in Browser

1. Download `index.html`
2. Open it in any modern web browser
3. No server or installation required

### Option 2: Host on GitHub Pages

1. Fork this repository
2. Enable GitHub Pages in repository settings
3. Access via `https://yourusername.github.io/timeclock-to-wps-payroll/`

### How to Use

1. **Upload**: Drag and drop a TimeClock Plus "Payroll Detail" HTML file into the drop zone, or click to browse
2. **Review**: Check the parsed data in the timesheet view. Edit hours or add notes as needed
3. **Export**: Click one of the export buttons:
   - **Export WPS CSV**: Standard CSV format for spreadsheet import
   - **Export Formatted Excel**: Styled HTML that opens in Excel with formatting
   - **Export Workday EIB**: Format compatible with Workday Enterprise Interface Builder

## Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- TimeClock Plus Payroll Detail report exported as HTML

## File Structure

```
timeclock-to-wps-payroll/
├── index.html      # Main application (single file, no dependencies)
├── README.md       # This file
└── LICENSE         # MIT License
```

## Technical Details

This tool is a single HTML file with embedded CSS and JavaScript. It requires no external dependencies, servers, or build steps.

### Supported Input Format

The tool expects TimeClock Plus HTML exports with:
- Employee names in bold `<b>` tags within `td[colspan="15"]` cells
- Date range in `<h2>` element
- 15-column data rows with: date (column 4), job code (column 8), hours (column 10)

### Export Formats

**WPS Template CSV**
- Includes organization header
- Columns separated for each weekday
- Certification and supervisor fields at bottom

**Formatted Excel (.xls)**
- HTML table that opens natively in Excel
- Includes zebra striping and professional formatting
- Print-ready layout

**Workday EIB CSV**
- One row per employee per day (only days with hours)
- Columns: Employee, Date (ISO format), Hours, Comment

## Development

Since this is a single HTML file, development is straightforward:

1. Open `index.html` in a text editor
2. Make changes
3. Refresh the browser to test

The code is organized into sections:
- CSS styles at the top
- Demo data JSON
- Grid building functions
- State management
- Export functions
- File parsing logic
- Event handlers

## License

MIT License. See [LICENSE](LICENSE) for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Credits

Developed for Worcester Public Schools Payroll Department.
