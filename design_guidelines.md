# Design Guidelines: Web Crawler Testing Environment

## Design Approach
**Selected Approach:** Minimal Design System  
**Rationale:** This is a utility-focused testing environment for validating web crawling tools. The design should be clean, functional, and not distract from the technical testing purpose while maintaining professional appearance.

**Design System:** Bootstrap-inspired minimal approach with clean typography and simple components

## Core Design Elements

### A. Color Palette

**Light Mode (Primary):**
- Background: 0 0% 100%
- Surface: 0 0% 98%
- Border: 220 13% 91%
- Text Primary: 222 47% 11%
- Text Secondary: 215 16% 47%
- Primary Accent: 217 91% 60%
- Success: 142 71% 45%
- Error: 0 84% 60%

**Dark Mode:**
- Background: 222 47% 11%
- Surface: 217 33% 17%
- Border: 217 19% 27%
- Text Primary: 210 40% 98%
- Text Secondary: 215 20% 65%

### B. Typography

**Fonts:**
- Primary: Inter (via Google Fonts CDN)
- Monospace: JetBrains Mono (for file paths/technical content)

**Scale:**
- Hero/Page Titles: text-4xl to text-5xl, font-bold
- Section Headings: text-2xl to text-3xl, font-semibold
- Body: text-base, font-normal
- Captions/Meta: text-sm, text-muted-foreground

### C. Layout System

**Spacing Primitives:** Use Tailwind units of 2, 4, 6, 8, 12, 16, 20, 24
- Component padding: p-4 to p-8
- Section spacing: py-12 to py-20
- Grid gaps: gap-4 to gap-8

**Container Strategy:**
- Max width: max-w-7xl
- Horizontal padding: px-4 md:px-6 lg:px-8

### D. Component Library

**Navigation:**
- Sticky header with horizontal navigation
- Breadcrumb trail showing page hierarchy
- Footer with site map and page count indicator

**Page Components:**
- Simple hero section per page with page title and description
- Grid-based content sections (2-3 columns on desktop)
- Card components for grouping related content
- File reference lists showing linked static resources
- Page navigation (Previous/Next) at bottom

**Interactive Elements:**
- Standard buttons with primary and secondary variants
- Simple link styling with underline on hover
- Minimal form elements if needed for search/filter

**Data Display:**
- Tables for listing static file references
- Code blocks for showing file paths
- Status indicators for file types

### E. Page Structure

**25-Page Architecture:**
- Homepage with site overview and navigation
- Category pages (5-6 categories with 4-5 pages each)
- Each page should have 8-12 static file references mixed between working and broken links
- Consistent header/footer across all pages
- Clear page numbering and hierarchy

**Content Distribution:**
- Distribute broken files naturally across pages
- Mix file types on each page
- Include realistic content placeholders (lorem ipsum acceptable)
- Add varied page lengths (some short, some longer)

### F. Static File Integration

**Visual Treatment:**
- Display working images naturally within content
- Show broken image placeholders with alt text
- List all CSS/JS references in page metadata sections
- Icon usage from Font Awesome (CDN) for file type indicators

### G. Animations

**Minimal Approach:**
- No animations - maintain fast load times for testing
- Simple hover states only (opacity/color changes)
- Focus on functionality over visual effects

## Images

**No Hero Images:** This utility site doesn't require hero imagery

**Content Images:**
- Placeholder images from working CDNs (unsplash, picsum)
- Broken image references to test domains
- SVG icons for file types and navigation

**Image Placement:**
- Scattered throughout page content naturally
- Mix of inline and background images
- Varied sizes to test different scenarios

## Testing-Specific Features

- Clear page indicators (Page X of 25)
- File reference counters per page
- Visual distinction between internal and external links
- Breadcrumb navigation for crawler path tracking
- Sitemap page listing all 25 pages
- Robots.txt reference indicator

**Key Principle:** Functionality and testability over aesthetics. Clean, professional, and purpose-built for web crawler validation.