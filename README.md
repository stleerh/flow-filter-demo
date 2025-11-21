# Flow Filter Selector Demo

A prototype for a network flow filter with intelligent field validation and context-aware value inputs.

Try it out at [https://stleerh.github.io/flow-filter-demo/](https://stleerh.github.io/flow-filter-demo/).

## Features

### Multi-Filter Support
- Add multiple filter rows with the **+ Add Filter** button
- Remove individual filters with the **✕** button
- Clear all filters with the **Clear Filters** button

### Smart Field Name Selection
- Searchable dropdown
- Type-ahead filtering for quick field selection
- Case-insensitive validation with automatic correction
- Invalid entries highlighted in red italics

### Context-Aware Value Input
- Value field adapts based on the selected field name

#### Field Name: Namespace Fields
**Fields:** Source Namespace, Dest Namespace
- Dropdown with predefined OpenShift namespace values
- Tag-based multi-value input
- Type or select from suggestions
- Case-insensitive validation with automatic correction for enumerated values
- Values can be entered with double or single quotes for an exact match

#### Field Name: Direction Fields
**Fields:** Interface Directions, Node Direction
- Restricted to "Ingress" or "Egress" only
- Dropdown selection
- Validation ensures only valid directions

#### Field Name: TCP Flags
**Field:** TCP flags
- Dropdown with valid TCP flags
- Multiple flags supported

#### Field Name: IP Address Fields
**Fields:** Any field containing "IP" (Source IP, Dest IP, Source Node IP, Dest Node IP)
- Plain text input with IP address validation
- Regex validation: `xxx.xxx.xxx.xxx` format
- Multiple IPs supported (space-separated)

#### Field Name: MAC Address Fields
**Fields:** Source MAC, Dest MAC
- Plain text input with MAC address validation
- Supports both formats: `XX:XX:XX:XX:XX:XX` and `XX-XX-XX-XX-XX-XX`
- Multiple MACs supported (space-separated)

#### Other Fields
- All other fields accept free-form text input.

### Tag-Based Value Entry
- Valid values appear as blue rounded tags with white text
- Click **×** on any tag to remove it
- Press **Space** or **Enter** to create a tag. Press **Tab** to create a tag and move to the next field.
- Backspace on empty input removes the last tag
- Selected values are removed from dropdown to prevent duplicates
- Values return to dropdown when tags are removed

### Validation & Feedback
- **Red border/text**: Invalid value detected
- **Visual feedback**: Real-time validation on blur

### Return Traffic Option
- Checkbox for including return traffic in the filter

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

### Use Cases

See how easy it is to create these use-case scenario.

1. I want all traffic for `netobserv` namespace.
```
[Dest Namespace] [=] [netobserv] ✓ Return Traffic
  -or-
[Source Namespace] [=] [netobserv] ✓ Return Traffic
```

2. I want all traffic between the namespaces `netobserv` and `openshift-console`.
```
[Source Namespace] [=] [netobserv]
[Dest Namespace] [=] [openshift-console] ✓ Return Traffic
```

3. I want all SYN traffic.
```
[TCP flags] [=] [SYN]
```

If you want the acknowledgement,
```
[TCP flags] [=] [SYN SYN_ACK]
```

4. I want all web request traffic.
```
[Dest Port] [=] [80 443]
```

## Technical Details

- **Pure HTML/CSS/JavaScript** - No dependencies required
- **Responsive design** - Adapts to different screen sizes
- **Tag-based UI** - Similar to popular tagging interfaces
- **Smart validation** - Field-specific validation rules
- **Dynamic dropdowns** - Context-aware suggestions

## License

This project is open source and available for use and modification.  It was written with the help of Claude Code.
