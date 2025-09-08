# Super Field - Icon

An icon picker component for Budibase applications with categorized icon library, search functionality, and visual selection interface.

## 🚀 Features

### Icon Selection

- **Categorized Library**: Organized icon categories for easy browsing
- **Search Functionality**: Quick icon finding by name or keyword
- **Visual Picker**: Grid-based icon selection interface
- **Default Values**: Pre-selected default icons
- **Template Formatting**: Custom icon display formatting

### Display Options

- **Swatch Styles**: Square or circular icon display
- **Inline Icons**: Additional visual indicators
- **Clear Value**: Option to clear selected icon
- **Help Text**: Guidance for icon selection
- **Placeholder**: Input guidance text

### User Experience

- **Intuitive Interface**: Visual icon browsing and selection
- **Debounced Search**: Performance-optimized search functionality
- **Event Handling**: On change events with icon context
- **Accessibility**: Keyboard navigation and screen reader support
- **Responsive Design**: Adapts to different screen sizes

### Validation & Control

- **Icon Validation**: Ensure valid icon selection
- **State Management**: Disabled and readonly modes
- **Input Masking**: Format restrictions for icon values
- **Conditional Logic**: Dynamic behavior based on icon state

### Advanced Features

- **Category Filtering**: Browse icons by category
- **Recent Icons**: Quick access to recently used icons
- **Custom Icons**: Support for custom icon uploads
- **Icon Metadata**: Size, format, and usage information

### Styling & Layout

- **Flexible Positioning**: Label placement options
- **Size Configuration**: Adjustable component width
- **Theme Integration**: Consistent with Budibase design
- **Custom CSS**: Advanced styling modifications

## 📝 Usage Instructions

### Basic Setup

1. Add the Super Field - Icon component to your form
2. Bind to a string field for storing icon values
3. Enable categories for organized icon browsing
4. Configure display options and validation

### Advanced Configuration

- **Category Display**: Enable categorized icon browsing
- **Search Settings**: Configure search and filtering options
- **Display Style**: Choose square or circular swatches
- **Events**: Attach actions to icon selection changes

### Common Use Cases

- **UI Customization**: Icon selection for buttons and menus
- **Status Indicators**: Visual status icons for data
- **Category Icons**: Icons for categorizing content
- **Navigation Elements**: Icons for navigation and menus
- **Visual Enhancement**: Icons for improving visual design

## 🔧 Configuration Options

| Setting          | Type     | Description                 |
| ---------------- | -------- | --------------------------- |
| Field            | String   | Icon value field binding    |
| Label            | String   | Display label text          |
| Placeholder      | String   | Selection guidance text     |
| Default Value    | String   | Pre-selected icon           |
| Formatted Value  | Template | Icon display formatting     |
| Help Text        | String   | Help/instruction text       |
| Validation       | Rules    | Icon selection validation   |
| Categories       | Boolean  | Enable categorized browsing |
| Debounce Delay   | Number   | Search debounce timing      |
| Disabled         | Boolean  | Disable icon selection      |
| Read Only        | Boolean  | Read-only mode              |
| Clear Value Icon | Boolean  | Show clear icon button      |
| Add Inline Icon  | Boolean  | Enable additional icon      |
| Icon             | Icon     | Inline icon selection       |
| Label Position   | Select   | Label placement             |
| Size             | Number   | Component width span        |
| Swatch           | Select   | Square or circular display  |

## 📋 Events

### On Change

Triggered when an icon is selected or changed.

**Context:**

- `value`: Selected icon value
- `field`: The bound field information

## 🎨 Styling

The component integrates with Budibase's styling system:

- **Icon Grid**: Organized icon display layout
- **Category Navigation**: Styled category browsing
- **Search Interface**: Clean search and filter controls
- **Selection States**: Visual feedback for selected icons

## 🔍 Best Practices

- Enable categories for large icon libraries
- Use appropriate swatch styles for context
- Provide help text for icon meaning/significance
- Consider accessibility with alternative text
- Test icon selection on various devices
- Use consistent icon styles across applications
