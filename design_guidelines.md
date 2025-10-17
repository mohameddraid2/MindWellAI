# Mental Health AI Analysis Platform - Design Guidelines

## Design Approach
**Reference-Based Approach**: Drawing inspiration from leading mental health platforms like Calm, Headspace, and BetterHelp, focusing on creating a compassionate, trustworthy environment that reduces anxiety and encourages honest self-reflection.

**Core Principles**: 
- Emotional safety through soft visual language
- Trust-building through clarity and professionalism
- Gentle guidance without clinical coldness
- Accessibility and inclusivity in all interactions

## Color Palette

**Light Mode:**
- Primary: 210 45% 45% (Calming blue - trust and stability)
- Background: 210 30% 98% (Soft off-white)
- Surface: 0 0% 100% (Pure white for cards)
- Text Primary: 220 20% 20% (Warm dark gray)
- Text Secondary: 220 15% 50%
- Accent: 150 40% 50% (Gentle teal for positive actions)
- Border: 220 15% 90%

**Dark Mode:**
- Primary: 210 50% 55%
- Background: 220 20% 12%
- Surface: 220 15% 16%
- Text Primary: 210 15% 95%
- Text Secondary: 210 10% 70%
- Accent: 150 35% 55%
- Border: 220 15% 25%

## Typography

**Font Families** (via Google Fonts):
- Headings: 'Inter' (500-600 weight) - Modern, approachable, professional
- Body: 'Inter' (400 weight) - Excellent readability
- Supportive Text: 'Inter' (300-400 weight) - Gentle, non-imposing

**Type Scale:**
- Hero Heading: text-5xl md:text-6xl font-semibold
- Section Heading: text-3xl md:text-4xl font-medium
- Question Text: text-xl md:text-2xl font-medium
- Body Text: text-base md:text-lg
- Small Text: text-sm

## Layout System

**Spacing Primitives**: Use Tailwind units of 4, 6, 8, 12, 16, 20, 24 for consistent rhythm
- Component padding: p-6 to p-8
- Section spacing: py-16 md:py-24
- Form elements: space-y-6 to space-y-8
- Container: max-w-4xl for form content, max-w-6xl for general sections

**Responsive Breakpoints:**
- Mobile-first approach
- Form: Single column on mobile, maintains single column on desktop for focus
- Results: Card layout adapts from stacked to side-by-side on larger screens

## Component Library

**Form Elements:**
- Radio buttons: Large, card-based selection (p-4 to p-6) with full-width hover states
- Question cards: Elevated with subtle shadow, rounded-2xl corners
- Input spacing: Generous vertical rhythm (space-y-8)
- Focus states: Primary color ring with increased ring width
- Labels: Text-lg weight-medium with mb-4 spacing

**Cards & Containers:**
- Main form container: bg-white dark:bg-surface rounded-3xl shadow-xl p-8 md:p-12
- Results cards: Rounded-2xl with border, subtle shadow
- Feature cards: Minimal borders, icon + heading + description pattern

**Buttons:**
- Primary CTA: Large (px-8 py-4), rounded-xl, primary color, text-lg
- Secondary: Outline variant with backdrop-blur-md when over images
- Disabled states: Reduced opacity with cursor-not-allowed

**Icons:**
- Use Heroicons (outline style) for UI elements
- Size: w-6 h-6 for inline, w-8 h-8 to w-12 h-12 for feature icons
- Color: Inherit from parent or use text-primary/text-accent

## Page Structure

**Hero Section** (min-h-[70vh]):
- Centered content with max-w-4xl
- Large heading communicating safety and support
- Subheading explaining the analysis process
- CTA button to scroll to form
- Gradient background: subtle blue-to-teal gradient (210 50% 98% to 180 45% 96%)

**Form Section:**
- Progressive disclosure: Show 2-3 questions at a time with "Continue" progression
- Question types: Radio button cards, range sliders for intensity scales
- Progress indicator: Simple step counter or minimal progress bar
- Submit button: Prominent, disabled until all required fields complete

**Results Section:**
- Analysis summary card with empathetic language
- Risk level indicator (if applicable): Color-coded but gentle (yellow/orange, not red)
- Supportive recommendations: Card grid with 2-3 actionable suggestions
- Resources section: Links to professional help, hotlines, self-care tips
- Disclaimer: Clear, visible, professional language about AI limitations

**Trust Elements:**
- Privacy notice: Visible reminder about data not being saved
- Professional disclaimer: "This is not a diagnostic tool" messaging
- Crisis resources: Always visible (sticky footer or dedicated section)

## Visual Enhancements

**Subtle Animations** (use sparingly):
- Form transitions: Gentle fade-in for new questions (duration-300)
- Results reveal: Staggered appearance with delay-100 increments
- Hover states: Scale-105 transform on interactive cards
- NO loading spinners with excessive motion - use simple fade states

**Imagery:**
- Hero: Abstract, calming illustration or photograph (soft focus nature, peaceful environment)
- Avoid clinical or medical imagery
- Use illustrations for feature/benefit icons
- Color overlay on images: Primary color at 5-10% opacity for brand consistency

**Accessibility:**
- WCAG AA contrast ratios minimum
- Focus indicators: 2px ring offset
- Form labels always visible
- Error states: Icon + color + text (never color alone)
- Dark mode: All interactive elements properly styled with sufficient contrast

## Key Differentiators

- Compassionate micro-copy throughout ("We're here to support you" not "Complete this form")
- Safe, non-judgmental language in all feedback
- Gentle color transitions, avoiding harsh contrasts
- Ample whitespace creating breathing room
- Professional yet warm aesthetic balancing medical credibility with approachability