# Flow Filter Selector

A dynamic HTML interface for building network flow filters with intelligent field validation and context-aware value inputs.

## Features

### Multi-Filter Support
- Add multiple filter rows with the **+ Add Filter** button
- Remove individual filters with the **✕** button
- Clear all filters with the **Clear Filters** button

### Smart Field Selection
- Searchable dropdown with 31 network flow field options
- Type-ahead filtering for quick field selection
- Case-insensitive validation with automatic correction
- Invalid entries highlighted in red italics

### Context-Aware Value Input
The value field adapts based on the selected field name:

#### Namespace Fields
**Fields:** Source Namespace, Dest Namespace
- Dropdown with predefined OpenShift namespace values
- Tag-based multi-value input
- Type or select from suggestions

#### Direction Fields
**Fields:** Interface Directions, Node Direction
- Restricted to "Ingress" or "Egress" only
- Dropdown selection
- Validation ensures only valid directions

#### TCP Flags
**Field:** TCP flags
- Dropdown with valid TCP flags: FIN, SYN, RST, PSH, ACK, URG, ECE, CWR, SYN_ACK, FIN_ACK, RST_ACK
- Multiple flags supported

#### IP Address Fields
**Fields:** Any field containing "IP" (Source IP, Dest IP, Source Node IP, Dest Node IP)
- Plain text input with IP address validation
- Regex validation: `xxx.xxx.xxx.xxx` format
- Multiple IPs supported (space-separated)

#### MAC Address Fields
**Fields:** Source MAC, Dest MAC
- Plain text input with MAC address validation
- Supports both formats: `XX:XX:XX:XX:XX:XX` and `XX-XX-XX-XX-XX-XX`
- Multiple MACs supported (space-separated)

#### Other Fields
All other fields accept free-form text input.

### Tag-Based Value Entry
- Values appear as blue rounded tags with white text
- Click **×** on any tag to remove it
- Press **Space** or **Enter** to create a tag
- Backspace on empty input removes the last tag
- Selected values are removed from dropdown to prevent duplicates
- Values return to dropdown when tags are removed

### Quote Handling
- Values can be entered with double or single quotes
- Quotes are automatically stripped: `"netobserv"` becomes `netobserv`
- Useful for values with special characters

### Validation & Feedback
- **Green border flash**: Valid value entered
- **Red border/text**: Invalid value detected
- **Visual feedback**: Real-time validation on blur

### Return Traffic Option
- Checkbox for including return traffic in the filter
- Located at the bottom right

## Available Fields

### Destination Fields
- Dest IP
- Dest Kind
- Dest MAC
- Dest Name
- Dest Namespace
- Dest Node IP
- Dest Node Name
- Dest Owner Name
- Dest Port
- Dest Resource
- Dest Subnet Label

### Source Fields
- Source IP
- Source Kind
- Source MAC
- Source Name
- Source Namespace
- Source Node IP
- Source Node Name
- Source Owner Name
- Source Port
- Source Resource
- Source Subnet Label

### Network Properties
- DSCP
- Flow layer
- ICMP code
- ICMP type
- Interface Directions
- Network interfaces
- Node Direction
- Protocol
- TCP flags

## Usage

1. **Open** `index.html` in a web browser
2. **Select a field** by clicking the field name dropdown and typing or selecting
3. **Choose an operator** (= or !=)
4. **Enter values**:
   - Type a value and press Space/Enter
   - Or select from the dropdown (if available)
   - Multiple values appear as tags
5. **Add more filters** using the + Add Filter button
6. **Remove filters** using the ✕ button on each row
7. **Check "Return traffic"** if needed
8. **Clear all** using the Clear Filters button

## Technical Details

- **Pure HTML/CSS/JavaScript** - No dependencies required
- **Responsive design** - Adapts to different screen sizes
- **Tag-based UI** - Similar to popular tagging interfaces
- **Smart validation** - Field-specific validation rules
- **Dynamic dropdowns** - Context-aware suggestions

## Browser Compatibility

Works in all modern browsers supporting:
- ES6 JavaScript
- CSS Flexbox
- HTML5 form elements

## File Structure

```
filter/
├── index.html          # Main application file
└── README.md           # This file
```

## License

This project is open source and available for use and modification.  It was written with the help of Claude Code.
