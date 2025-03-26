# Modern Roblox UI Library

A sleek, customizable UI library designed for Roblox exploiting environments. This library features smooth animations, responsive design, and a modern aesthetic.

## Features

- **Modern Design**: Clean, minimalist interface with rounded corners and subtle animations
- **Responsive Layout**: Scales properly on different screen sizes
- **Customizable Themes**: Easily change colors to match your preferences
- **Smooth Animations**: All components feature smooth transitions and effects
- **Exploit Environment Compatible**: Designed to work with popular Roblox exploit engines

## Components

- **Buttons**: With ripple effects and hover animations
- **Text Inputs**: With validation and formatting options
- **Toggles**: Animated toggle switches
- **Sliders**: Customizable range sliders with value display
- **Dropdowns**: Expandable option menus
- **Notifications**: Timed notifications with different types (info, success, warning, error)
- **Tabs**: For organizing content

## Installation

1. Download the library files or load them directly via HTTP requests
2. Use the `loadstring` function to include the components you need:

```lua
local ModernUI = loadstring(game:HttpGet("https://raw.githubusercontent.com/username/ModernRobloxUI/main/ModernUI.txt"))()
local Button = loadstring(game:HttpGet("https://raw.githubusercontent.com/username/ModernRobloxUI/main/Button.txt"))()
local TextInput = loadstring(game:HttpGet("https://raw.githubusercontent.com/username/ModernRobloxUI/main/TextInput.txt"))()
local Toggle = loadstring(game:HttpGet("https://raw.githubusercontent.com/username/ModernRobloxUI/main/Toggle.txt"))()
local Slider = loadstring(game:HttpGet("https://raw.githubusercontent.com/username/ModernRobloxUI/main/Slider.txt"))()
local Dropdown = loadstring(game:HttpGet("https://raw.githubusercontent.com/username/ModernRobloxUI/main/Dropdown.txt"))()
local Notification = loadstring(game:HttpGet("https://raw.githubusercontent.com/username/ModernRobloxUI/main/Notification.txt"))()
```

## Basic Usage

### Creating a UI Window

```lua
-- Create the main UI window
local mainUI = ModernUI:Create("My UI Title", UDim2.new(0, 500, 0, 350))

-- Add a tab
local mainTab = mainUI:AddTab("Main")
```

### Adding Components

#### Button

```lua
local myButton = Button.new(
    mainTab.Content,              -- Parent
    "Click Me!",                  -- Text
    UDim2.new(0, 200, 0, 40),     -- Size
    UDim2.new(0.5, 0, 0, 100)     -- Position
)

-- Add click handler
myButton:OnClick(function()
    print("Button clicked!")
end)
```

#### Text Input

```lua
local myInput = TextInput.new(
    mainTab.Content,              -- Parent
    "Enter your name",            -- Placeholder
    UDim2.new(0, 200, 0, 40),     -- Size
    UDim2.new(0.5, 0, 0, 150)     -- Position
)

-- Add validation
myInput:SetRequired(true)
myInput:SetPattern("^[%w%s]+$", "Letters and numbers only")

-- Get input value
myInput:GetText()
```

#### Toggle

```lua
local myToggle = Toggle.new(
    mainTab.Content,              -- Parent
    "Enable Feature",             -- Text
    UDim2.new(0, 200, 0, 40),     -- Size
    UDim2.new(0.5, 0, 0, 200)     -- Position
)

-- Set default value
myToggle:SetValue(true)

-- Add change handler
myToggle:OnChanged(function(value)
    print("Toggle is now:", value)
end)
```

#### Slider

```lua
local mySlider = Slider.new(
    mainTab.Content,              -- Parent
    "Volume",                     -- Text
    0, 100, 50,                   -- Min, Max, Default
    UDim2.new(0, 200, 0, 40),     -- Size
    UDim2.new(0.5, 0, 0, 250)     -- Position
)

-- Configure slider
mySlider:SetPrecision(0)          -- No decimal places
mySlider:SetValueSuffix("%")      -- Add percentage sign

-- Add change handler
mySlider:OnChanged(function(value)
    print("Slider value:", value)
end)
```

#### Dropdown

```lua
local myDropdown = Dropdown.new(
    mainTab.Content,              -- Parent
    "Select Option",              -- Placeholder
    {                             -- Options
        {Text = "Option 1", Value = 1},
        {Text = "Option 2", Value = 2},
        {Text = "Option 3", Value = 3}
    },
    UDim2.new(0, 200, 0, 40),     -- Size
    UDim2.new(0.5, 0, 0, 300)     -- Position
)

-- Add change handler
myDropdown:OnChanged(function(value, text)
    print("Selected:", text, "with value", value)
end)
```

#### Notifications

```lua
-- Show different types of notifications
Notification.info("Information", "This is an info message", 3)
Notification.success("Success", "Operation completed successfully", 3)
Notification.warning("Warning", "This action cannot be undone", 3)
Notification.error("Error", "Something went wrong", 3)

-- Custom notification
Notification.custom(
    "Custom", 
    "Custom notification with custom color", 
    Color3.fromRGB(180, 100, 255),    -- Color
    "rbxassetid://7733658504",        -- Icon ID (optional)
    3                                  -- Duration
)
```

### Customizing Theme

```lua
-- Change the theme
ModernUI:SetTheme({
    Primary = Color3.fromRGB(45, 50, 60),    -- Main background color
    Secondary = Color3.fromRGB(35, 40, 50),  -- Secondary background color
    Accent = Color3.fromRGB(65, 125, 225),   -- Accent color for highlights
    Text = Color3.fromRGB(255, 255, 255),    -- Main text color
    TextDark = Color3.fromRGB(180, 180, 180) -- Secondary text color
})
```

## Examples

For detailed examples, check the included example files:

- `SimpleExample.txt`: Basic usage of the library
- `AdvancedExample.txt`: More complex example with forms, tabs, and theme customization

## Notes

- This library is designed for Roblox exploiting environments and includes protections for CoreGui
- UI elements are draggable by default (by the title bar)
- All components support chaining for easier configuration
- Responsive to different screen sizes

## License

Free to use and modify for personal and commercial projects. 