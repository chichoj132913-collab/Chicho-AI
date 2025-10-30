# Chicho AI Chat Interface - Design Guidelines

## Design Approach
**iMessage-Inspired Chat Application** - Drawing from Apple's iMessage design language with frosted glass effects, clean typography, and minimalist aesthetics focused on conversation clarity.

## Core Design Elements

### Typography
- **Primary Font**: SF Pro Display (fallback: -apple-system, BlinkMacSystemFont, "Segoe UI")
- **Message Text**: 15px regular weight for readability
- **Input Field**: 16px regular weight
- **Timestamps**: 11px regular, slightly reduced opacity
- **App Title**: 20px semibold
- **Code Blocks**: SF Mono, Consolas, monospace at 14px

### Layout System
**Spacing Scale**: Tailwind units of 2, 3, 4, 6, 8, 12
- Message bubbles: p-3 to p-4
- Container padding: p-6 to p-8
- Message spacing: gap-2 between messages, gap-6 between conversation groups
- Input area: p-4

### Theme System
**Dark Theme (Default)**
- Background: Pure black (#000000) static
- Frosted glass overlays: backdrop-blur-xl with rgba(255, 255, 255, 0.1) for subtle translucency
- User message bubbles: rgba(0, 122, 255, 0.85) with backdrop-blur
- AI message bubbles: rgba(60, 60, 67, 0.6) with backdrop-blur
- Text on dark: White (#FFFFFF)
- Input background: rgba(255, 255, 255, 0.08) with backdrop-blur

**Light Theme**
- Background: Pure white (#FFFFFF) static
- Frosted glass overlays: backdrop-blur-xl with rgba(0, 0, 0, 0.05)
- User message bubbles: rgba(0, 122, 255, 0.95) with subtle blur
- AI message bubbles: rgba(229, 229, 234, 0.9) with subtle blur
- Text on light: Black (#000000)
- Input background: rgba(0, 0, 0, 0.05) with backdrop-blur

### Component Library

**Chat Container**
- Max width: 900px centered on viewport
- Full height viewport layout
- Frosted glass header bar (60px height) with backdrop-blur-xl
- Scrollable message area with smooth scrolling
- Fixed input area at bottom (70px height) with frosted glass backdrop

**Message Bubbles**
- User messages: Right-aligned, max-width 65%, rounded corners (18px)
- AI messages: Left-aligned, max-width 70%, rounded corners (18px)
- Tail-less bubble design (modern iMessage style)
- Internal padding: 12px horizontal, 10px vertical
- Shadow: subtle rgba shadow for depth

**Header Component**
- Frosted glass bar spanning full width
- "Chicho AI" title centered at 20px semibold
- Theme toggle button (sun/moon text symbols, not emojis): positioned top-right
- Toggle button: 36px × 36px, rounded-full, backdrop-blur with hover state

**Input Area**
- Frosted glass container with backdrop-blur-xl
- Text input: rounded-full (24px radius), frosted glass background
- Send button: Text-based "Send" or "→" symbol (not emoji), rounded-full
- Input stretches with padding-right for send button
- Auto-resize textarea that grows with content (max 120px height)

**Markdown Rendering**
- **Bold**: font-weight 600
- *Italic*: font-style italic
- `Inline code`: monospace font, slight background tint, 2px padding, rounded
- Code blocks: Full-width in bubble, monospace, background contrast, 12px padding, 8px border-radius, syntax highlighting with simple color scheme
- Lists: Proper bullet points with 4px left margin
- Links: Underlined, theme-appropriate blue

**Loading Indicator**
- Three animated dots (text-based "•••") that pulse
- Appears in AI message bubble while waiting for response
- Smooth fade-in/out transitions

**Empty State**
- Centered in message area when no messages
- "Start chatting with Chicho AI" message
- Subtle opacity, 16px regular weight

**Theme Toggle Button**
- Text symbols: "☀" for light mode trigger, "☾" for dark mode trigger
- 36px circular button
- Frosted glass background matching theme
- Smooth rotation animation on toggle (180deg)
- Position: Absolute top-right of header with 16px margin

### Interaction Patterns
- Message send: Enter key or click send button
- Shift+Enter: New line in message
- Smooth auto-scroll to latest message
- Fade-in animation for new messages (200ms)
- Hover states on send button: slight scale increase (1.05x)
- Theme toggle: Instant switch with 300ms transition on background colors
- Focus states: Subtle glow on input field

### Accessibility
- Sufficient contrast ratios for both themes (WCAG AA minimum)
- Focus indicators on all interactive elements
- Semantic HTML for screen readers
- Keyboard navigation support
- ARIA labels for icon buttons

### Animations
- Message appearance: Gentle slide-up + fade (200ms ease-out)
- Loading dots: Staggered pulse animation (600ms)
- Theme transition: 300ms ease for background and color shifts
- Button hover: 150ms scale transform
- No distracting parallax or excessive motion

## Images
**No images required** - This is a text-based chat interface. All visual elements use CSS effects (frosted glass, gradients, shadows) and text-based symbols rather than icons or imagery.