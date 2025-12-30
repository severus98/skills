---
name: ucas-presentation-ppt-generator
description: Generate HTML presentations in University of Chinese Academy of Sciences (UCAS) style. Analyzes folder contents to create PPT outlines and incorporates local images. Use when creating academic thesis defenses, course presentations, research progress reports, conference presentations, or any formal academic PPT materials requiring UCAS branding.
author: severus98
---

# UCAS Presentation PPT Generator

A professional HTML presentation generator following the University of Chinese Academy of Sciences visual standards. Creates standardized academic PPT materials with official branding elements. Automatically analyzes folder contents to incorporate local images and generates appropriate PPT structure.

## Overview

This Skill generates professional HTML presentations following the University of Chinese Academy of Sciences (UCAS) visual standards. When creating academic reports, course presentations, thesis defenses, or research progress updates, use this Skill to produce standardized PPT materials that meet UCAS brand guidelines. The Skill analyzes folder contents to create appropriate PPT outlines and incorporates local image files.

## Workflow

When a user requests a UCAS-style presentation, follow these steps:

### Step 1: Analyze Folder Contents

Scan the current working directory and its subdirectories to:
- Find CAS_logo.png and UCAS_logo.png for logo placement
- Identify all image files that could be used in the presentation
- Understand the context and content structure from available files

**Logo Search Priority**:
1. Search for `CAS_logo.png` and `UCAS_logo.png` in current directory and subdirectories
2. If found, use relative paths like `CAS_logo.png` or `subfolder/CAS_logo.png`
3. If not found, display warning text in SimSun font with red color (#CC0000)

### Step 2: Gather User Requirements and Create Outline

Collect the following information from the user:
- Presentation title and subtitle (if any)
- Presenter name and affiliation
- Presentation content outline (topics, sections)
- Number of slides or page distribution
- Key emphasis points (important data, conclusions)

**Create PPT Outline Based On**:
- User's stated requirements and topics
- Context from folder contents (e.g., image files suggest certain topics)
- Standard academic presentation structure

### Step 3: Analyze Images for Context

For each image file found in the folder:
- Use `images_understand` MCP tool to understand image content if needed
- Note the image filename and its apparent meaning
- Determine appropriate slide placement based on image content
- Match images with relevant PPT sections

### Step 4: Generate Homepage

Create a title slide with the following structure:
- Left sidebar (32% width) with #18388A background color
- CAS logo (or warning text if logo not found) vertically centered in the sidebar
- Right content area with left-aligned text
- Main title (48px, Bold, #18388A)
- Subtitle (26px, Regular, #18388A)
- Presenter information and date

**Missing Logo Handling**:
```html
<p style="font-family: 'SimSun', '宋体', serif; color: #CC0000; font-size: 14px;">
    [警告：未找到CAS_logo.png，请将logo文件放入当前目录]
</p>
```

### Step 5: Generate Content Pages

For each content page, follow the standard format:
- UCAS logo (or warning text if logo not found) at top-right corner
- Page title (32px, Bold, #18388A) with left-border decoration (6px solid #18388A)
- Left-aligned body content (20px, Regular)
- Subtitle (22px, Bold, #18388A) for section headers
- Page number at bottom-right
- Insert relevant images from folder when appropriate

**Image Insertion Example**:
```html
<div class="image-container">
    <img src="chart_results.png" alt="实验结果图表">
    <p class="image-caption">图1：实验结果对比</p>
</div>
```

### Step 6: Apply Emphasis and Images

Apply formatting based on content importance:
- **Red Emphasis (#CC0000)**: Key conclusions, important data, core findings (max 2-3 per page)
- **Bold Emphasis**: Technical terms, proper nouns, important concepts
- **Highlight Box**: Red left-border box for critical information
- **Images**: Insert analyzed images at appropriate positions with captions

### Step 7: Final Review

Verify the presentation meets all UCAS standards:
- Logo files correctly placed or warning text displayed
- All text uses appropriate font (Microsoft YaHei or SimSun for warnings)
- Theme blue #18388A consistently applied
- Homepage uses asymmetric sidebar layout
- Content page titles use left-border decoration
- Images from folder are appropriately placed with captions
- Red emphasis used sparingly (2-3 per page)
- All content left-aligned

## Folder Analysis

### Logo Detection Process

1. **Search Locations**:
   - Current working directory
   - All subdirectories recursively
   - Common locations: root, images/, resources/, references/

2. **File Matching**:
   - Case-insensitive matching for `CAS_logo.png` and `UCAS_logo.png`
   - Accept exact filename matches

3. **Fallback Behavior**:
   - If logo not found, display warning message
   - Warning text uses SimSun font and red color (#CC0000)
   - Warning message in Chinese: "[警告：未找到logo文件，请将CAS_logo.png放入当前目录]"

### Image Context Analysis

For each image file in the folder:
1. Use `images_understand` tool to analyze content
2. Extract relevant information:
   - What the image depicts
   - Its relevance to presentation topic
   - Appropriate caption text
3. Determine insertion point based on:
   - Image subject matter
   - Current PPT section
   - Logical flow of presentation

## Design Standards

### Color Specification

| Element | Color Code | Usage |
|---------|------------|-------|
| Primary Blue | #18388A | Sidebar background, titles, key elements |
| Emphasis Red | #CC0000 | Key conclusions, important data, warnings |
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
| Warning Text | 14px | Regular | Missing logo warning (SimSun, #CC0000) |

**Font Family**: 'Microsoft YaHei', '微软雅黑', 'PingFang SC', 'Helvetica Neue', sans-serif
**Warning Font**: 'SimSun', '宋体' (for missing logo warnings)

### Logo Usage

| Page Type | Logo | Position | Fallback |
|-----------|------|----------|----------|
| Homepage | CAS Logo | Left sidebar, vertically centered | SimSun red warning text |
| Content Pages | UCAS Logo | Top-right corner | SimSun red warning text |

### Layout Structure

**Homepage Layout**:
- Asymmetric two-column layout
- Left sidebar: 32% width, #18388A background
- Right content area: 68% width, left-aligned
- Logo (or warning) and title in blue sidebar theme

**Content Page Layout**:
- UCAS logo (or warning) at top-right
- Title with left blue border decoration (6px)
- Left-aligned body content
- Images inserted with captions
- Page number at bottom-right

### Emphasis Rules

| Style | Color | Weight | Usage |
|-------|-------|--------|-------|
| Red Emphasis | #CC0000 | Bold | Key conclusions, important data (max 2-3 per page) |
| Bold Emphasis | #333333 | Bold | Technical terms, proper nouns, concepts |
| Warning Text | #CC0000 | Regular | Missing logo notifications (SimSun font) |

## When to Apply

Apply these guidelines whenever creating:
- Academic thesis defenses
- Course presentations and assignments
- Research progress reports
- Academic conference presentations
- Proposal and final reports
- Group meeting updates
- Formal academic presentation occasions
- Any presentation requiring analysis of local folder contents

## HTML Template Structure

### Homepage Layout
```html
<div class="slide title-slide">
    <div class="title-sidebar">
        <!-- Logo found -->
        <img src="CAS_logo.png" alt="CAS Logo" class="cas-logo">
        <!-- OR if logo not found -->
        <p style="font-family: 'SimSun', '宋体'; color: #CC0000; font-size: 14px;">
            [警告：未找到CAS_logo.png，请将logo文件放入当前目录]
        </p>
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

### Content Page with Image
```html
<div class="slide">
    <!-- Logo or warning -->
    <img src="UCAS_logo.png" alt="UCAS Logo" class="ucas-logo">
    <!-- OR -->
    <p style="font-family: 'SimSun', '宋体'; color: #CC0000; position: absolute; top: 30px; right: 40px; font-size: 12px;">
        [缺UCAS_logo]
    </p>

    <h2 class="slide-title">Page Title</h2>
    <div class="content">
        <p>Content paragraph with analysis...</p>

        <!-- Inserted image with caption -->
        <div class="image-container">
            <img src="experiment_chart.png" alt="实验结果">
            <p class="image-caption">图1：实验结果对比图</p>
        </div>

        <p class="emphasis-red">Key point in red</p>
    </div>
    <span class="page-number">1/10</span>
</div>
```

### CSS Key Definitions
```css
/* Page Container - 16:9 Aspect Ratio for Printing */
.presentation-container {
    width: 100vw;
    height: 56.25vw; /* 16:9 aspect ratio based on width */
    max-height: 100vh;
    max-width: 177.78vh; /* 16:9 aspect ratio based on height */
    margin: 0 auto;
    aspect-ratio: 16/9;
    overflow: hidden;
    position: relative;
    font-family: 'Microsoft YaHei', '微软雅黑', 'PingFang SC', 'Helvetica Neue', sans-serif;
    background: #FFFFFF;
}

/* Slide Base */
.slide {
    width: 100%;
    height: 100%;
    display: none;
    position: absolute;
    top: 0;
    left: 0;
    background: #FFFFFF;
    overflow: hidden;
}

/* Homepage Sidebar - Full Left Side */
.title-sidebar {
    position: absolute;
    left: 0;
    top: 0;
    width: 35%;
    height: 100%;
    background: #18388A;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 40px;
}

/* CAS Logo - Appropriate Size in Sidebar */
.title-sidebar .cas-logo {
    width: 70%;
    max-width: 200px;
    height: auto;
    object-fit: contain;
}

/* Homepage Content Area */
.title-content {
    position: absolute;
    left: 35%;
    top: 0;
    width: 65%;
    height: 100%;
    padding: 60px 80px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: left;
}

/* Content Page Title */
.slide-title {
    font-size: 32px;
    font-weight: bold;
    color: #18388A;
    padding-left: 20px;
    border-left: 6px solid #18388A;
    margin-bottom: 35px;
}

/* Content Page Layout */
.slide .content {
    padding: 0 80px 60px 80px;
    font-size: 20px;
    line-height: 1.8;
    color: #333333;
}

/* UCAS Logo - Top Right Corner */
.slide:not(.title-slide) .ucas-logo {
    position: absolute;
    top: 25px;
    right: 40px;
    width: 50px;
    height: auto;
    object-fit: contain;
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

/* Image Container */
.image-container {
    margin: 30px 0;
    padding: 20px;
    background: #F9F9F9;
    border-radius: 8px;
    text-align: center;
}

.image-container img {
    max-width: 100%;
    max-height: 350px;
    object-fit: contain;
}

.image-caption {
    font-size: 16px;
    color: #666666;
    margin-top: 12px;
    text-align: center;
}

/* Page Number */
.page-number {
    position: absolute;
    bottom: 20px;
    right: 40px;
    font-size: 14px;
    color: #666666;
}

/* Spacing for Balanced Layout */
.content p {
    margin-bottom: 15px;
}

.content ul, .content ol {
    margin: 20px 0 20px 30px;
}

.content li {
    margin-bottom: 12px;
}

.content .subtitle {
    font-size: 22px;
    font-weight: bold;
    color: #18388A;
    margin: 30px 0 15px 0;
}

/* Highlight Box */
.highlight-box {
    background: #FFF8F8;
    border-left: 4px solid #CC0000;
    padding: 20px;
    margin: 25px 0;
    border-radius: 0 4px 4px 0;
}

/* Table Styling */
.content table {
    width: 100%;
    border-collapse: collapse;
    margin: 25px 0;
}

.content th, .content td {
    border: 1px solid #DDDDDD;
    padding: 12px 15px;
    text-align: left;
}

.content th {
    background: #F5F7FA;
    color: #18388A;
    font-weight: bold;
}
```

## Usage Examples

### Example 1: Thesis Defense with Folder Analysis
User: "Generate a thesis defense PPT. The folder contains experimental data images."

Claude will:
1. Analyze folder to find CAS_logo.png, UCAS_logo.png, and experiment images
2. Use images_understand to comprehend experiment images
3. Create outline based on thesis structure and image context
4. Generate homepage with CAS logo (or warning)
5. Insert experiment images with appropriate captions on relevant slides

### Example 2: Research Progress with Local Images
User: "Create a research progress report. We have result charts and diagrams in the project folder."

Claude will:
1. Scan folder for logos and research images
2. Analyze chart images to understand their content
3. Create presentation outline matching research sections
4. Insert analyzed charts at appropriate positions
5. Add captions explaining each figure

### Example 3: Missing Logo Scenario
User: "Generate a presentation but I haven't prepared the logo files yet."

Claude will:
1. Search for CAS_logo.png and UCAS_logo.png
2. Not find them in the folder
3. Generate presentation with SimSun red warning text
4. Continue with all other UCAS styling elements
5. Remind user to add logo files for final version

## Quick Reference

| Scenario | Action |
|----------|--------|
| "Create thesis defense PPT" | Analyze folder, create outline, generate with logos |
| "Make report with local images" | Scan images, analyze content, insert appropriately |
| "No logo files available" | Use SimSun red warning text, continue generation |
| "Update with new images" | Re-analyze folder, insert at logical positions |

## Folder Resources

This Skill analyzes:
- Logo files: CAS_logo.png, UCAS_logo.png
- Content images: Charts, diagrams, photos, screenshots
- Context files: Any file that suggests presentation topics

## Notes

- Generated HTML files support keyboard navigation (arrow keys, space) and mouse clicks
- Use browser fullscreen mode (F11) for best presentation experience
- Print to PDF available via browser print function
- Ensure logo files are official versions with proper authorization
- All text should use Microsoft YaHei font (SimSun for warnings)
- Missing logo warnings use SimSun font in red (#CC0000)
- Image analysis improves relevance and caption quality
