---
name: ucas-presentation-ppt-generator
description: Generate HTML presentations in University of Chinese Academy of Sciences (UCAS) style. Use when creating academic thesis defenses, course presentations, research progress reports, conference presentations, or any formal academic PPT materials requiring UCAS branding.
author: severus98
---

# UCAS Presentation PPT Generator

A professional HTML presentation generator following the University of Chinese Academy of Sciences visual standards. Creates standardized academic PPT materials with official branding elements.

## Overview

This Skill generates professional HTML presentations following the University of Chinese Academy of Sciences (UCAS) visual standards. When creating academic reports, course presentations, thesis defenses, or research progress updates, use this Skill to produce standardized PPT materials that meet UCAS brand guidelines.

## Workflow

When a user requests a UCAS-style presentation, follow these steps:

### Step 1: Gather User Requirements

Collect the following information:
- Presentation title and subtitle (if any)
- Presenter name and affiliation
- Presentation content outline (topics, sections)
- Number of slides or page distribution
- Key emphasis points (important data, conclusions)

### Step 2: Generate Homepage

Create a title slide with the following structure:
- Left sidebar (32% width) with #18388A background color
- CAS logo vertically centered in the sidebar
- Right content area with left-aligned text
- Main title (48px, Bold, #18388A)
- Subtitle (26px, Regular, #18388A)
- Presenter information and date

### Step 3: Generate Content Pages

For each content page, follow the standard format:
- UCAS logo at top-right corner
- Page title (32px, Bold, #18388A) with left-border decoration (6px solid #18388A)
- Left-aligned body content (20px, Regular)
- Subtitle (22px, Bold, #18388A) for section headers
- Page number at bottom-right

### Step 4: Apply Emphasis

Apply formatting based on content importance:
- **Red Emphasis (#CC0000)**: Key conclusions, important data, core findings (max 2-3 per page)
- **Bold Emphasis**: Technical terms, proper nouns, important concepts
- **Highlight Box**: Red left-border box for critical information

### Step 5: Final Review

Verify the presentation meets all UCAS standards:
- Logo files correctly placed and referenced
- All text uses Microsoft YaHei font
- Theme blue #18388A consistently applied
- Homepage uses asymmetric sidebar layout
- Content page titles use left-border decoration
- Red emphasis used sparingly (2-3 per page)
- All content left-aligned

## Design Standards

### Color Specification

| Element | Color Code | Usage |
|---------|------------|-------|
| Primary Blue | #18388A | Sidebar background, titles, key elements |
| Emphasis Red | #CC0000 | Key conclusions, important data, core findings |
| Background | #FFFFFF | Page background |
| Text | #333333 | Body text content |

### Font Specification

| Element | Size | Weight | Usage |
|---------|------|--------|-------|
| Homepage Main Title | 48px | Bold | Presentation title on homepage |
| Homepage Subtitle | 26px | Regular | Optional subtitle on homepage |
| Content Page Title | 32px | Bold | Section headers on content pages |
| Subtitle | 22px | Bold | Section sub-headers |
| Body Text | 20px | Regular | Main content |
| Page Number | 14px | Regular | Footer page indicator |

**Font Family**: 'Microsoft YaHei', '微软雅黑', 'PingFang SC', 'Helvetica Neue', sans-serif

### Logo Usage

| Page Type | Logo | Position | Size |
|-----------|------|----------|------|
| Homepage | CAS Logo | Left sidebar, vertically centered | 70-80% of sidebar width |
| Content Pages | UCAS Logo | Top-right corner | ~45px height |

**File Requirements**: PNG format with transparent background

### Layout Structure

**Homepage Layout**:
- Asymmetric two-column layout
- Left sidebar: 32% width, #18388A background
- Right content area: 68% width, left-aligned
- Logo and title in blue sidebar theme

**Content Page Layout**:
- UCAS logo at top-right
- Title with left blue border decoration (6px)
- Left-aligned body content
- Page number at bottom-right

### Emphasis Rules

| Style | Color | Weight | Usage |
|-------|-------|--------|-------|
| Red Emphasis | #CC0000 | Bold | Key conclusions, important data (max 2-3 per page) |
| Bold Emphasis | #333333 | Bold | Technical terms, proper nouns, concepts |

## When to Apply

Apply these guidelines whenever creating:
- Academic thesis defenses
- Course presentations and assignments
- Research progress reports
- Academic conference presentations
- Proposal and final reports
- Group meeting updates
- Formal academic presentation occasions

## HTML Template Structure

### Homepage Layout
```html
<div class="slide title-slide">
    <div class="title-sidebar">
        <img src="references/CAS_logo.png" alt="CAS Logo" class="cas-logo">
    </div>
    <div class="title-content">
        <h1>Presentation Title</h1>
        <h2>Subtitle (Optional)</h2>
        <p>Presenter: Name</p>
        <p>University of Chinese Academy of Sciences</p>
        <p>December 2025</p>
    </div>
</div>
```

### Content Page Layout
```html
<div class="slide">
    <img src="references/UCAS_logo.png" alt="UCAS Logo" class="ucas-logo">
    <h2 class="slide-title">Page Title</h2>
    <div class="content">
        <p class="emphasis-red">Key point in red</p>
        <p>Regular content with <span class="emphasis-bold">bold emphasis</span></p>
        <ul>
            <li>First point</li>
            <li>Second point with <span class="emphasis-red">important data</span></li>
        </ul>
    </div>
    <span class="page-number">1/10</span>
</div>
```

### CSS Key Definitions
```css
/* Homepage Sidebar */
.title-sidebar {
    width: 32%;
    height: 100%;
    background: #18388A;
}

/* Content Page Title */
.slide-title {
    font-size: 32px;
    font-weight: bold;
    color: #18388A;
    padding-left: 20px;
    border-left: 6px solid #18388A;
}

/* Red Emphasis */
.emphasis-red {
    color: #CC0000;
    font-weight: bold;
}

/* Bold Emphasis */
.emphasis-bold {
    font-weight: bold;
    color: #333333;
}
```

## Usage Examples

### Example 1: Thesis Defense
User: "Generate a thesis defense PPT titled 'Research on Deep Learning Image Classification' by Zhang San, supervised by Professor Li Si."

Claude will generate:
- Homepage with thesis title, author, supervisor
- Content pages covering: research background, methodology, experiments, results, conclusion
- Appropriate emphasis on key innovations and results

### Example 2: Research Progress
User: "Create a 10-page research progress report covering: background, methodology, results, issues, and next steps."

Claude will generate:
- Homepage with project title and presenter info
- 10 content pages distributed across sections
- Tables for data presentation
- Highlight boxes for key findings

### Example 3: Course Presentation
User: "Generate a 5-page presentation on machine learning basics for a course assignment."

Claude will generate:
- Homepage with course name and topic
- 5 content pages covering fundamentals
- Clear subtitle hierarchy
- Appropriate use of emphasis

## Quick Reference

| User Request | Action |
|--------------|--------|
| "Create a thesis defense PPT" | Generate defense presentation with all standard sections |
| "Make a research report" | Generate research progress presentation with data tables |
| "Course presentation" | Generate educational presentation with clear structure |
| "Update existing presentation" | Follow all UCAS standards for consistency |

## references

See the references folder for:
- CAS_logo.png (for homepage sidebar)
- UCAS_logo.png (for content page headers)
- template.html (complete reference template)

## Notes

- Generated HTML files support keyboard navigation (arrow keys, space) and mouse clicks
- Use browser fullscreen mode (F11) for best presentation experience
- Print to PDF available via browser print function
- Ensure logo files are official versions with proper authorization
- All text should use Microsoft YaHei font for consistency
