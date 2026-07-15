# Webflow Migration Guide - All-Star Renovations

## Quick Start
1. Create new Webflow site
2. Set up CMS Collections (see below)
3. Import content from static HTML files
4. Build using this structure

## Recommended CMS Collections

### 1. Locations Collection
Fields:
- City Name (Plain Text)
- Slug (Slug)
- Meta Title (Plain Text)
- Meta Description (Plain Text)
- Hero Headline (Plain Text)
- Hero Subheadline (Plain Text)
- Main Content (Rich Text)
- Key Benefits (Rich Text)
- Local FAQ (Rich Text)
- Phone Number (Plain Text)
- Featured Image (Image)
- Gallery Images (Multi-image)

### 2. Blog Posts Collection
Fields:
- Title (Plain Text)
- Slug (Slug)
- Featured Image (Image)
- Excerpt (Plain Text)
- Content (Rich Text)
- Category (Option)
- Published Date (Date)

### 3-Tier Comparison Component
Create a Component with 3 columns:
- Premier Card
- Signature Card (with "Most Popular" badge)
- Designer Premium Card

Each card should have:
- Tier name
- Short description
- Starting price range
- Key features list
- CTA button linking to consultation form

## Page Structure
- Home (static)
- Location Template (dynamic from Locations collection)
- Blog Template (dynamic)
- Service pages (static or dynamic)

## Custom Code for Schema
Add JSON-LD in page settings or custom code embed using the schema from references/schema-markup-library.md

## Forms
Use Webflow Forms connected to email or Zapier for lead capture.