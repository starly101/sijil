# Phase 06: Document Viewer

## Overview

This phase implements the core document reading experience for Sijil. Users can view full documents with proper typography, navigation, metadata display, and version information. This is the primary content consumption interface of the application.

## Goals

- Render full document text with optimal readability
- Display comprehensive document metadata
- Support hierarchical navigation (chapters/sections)
- Implement smooth scrolling and position memory
- Provide citation and reference tools
- Ensure accessibility for screen readers
- Optimize for long-form reading sessions

## Deliverables

1. **Document Detail Page** (`/documents/[id]`)
   - Main content area with rendered text
   - Sticky header with navigation controls
   - Metadata sidebar (collapsible on mobile)
   - Table of contents panel
   - Citation tools

2. **Components**
   - `DocumentViewer` - Main viewer container
   - `DocumentText` - Text rendering with typography
   - `DocumentMetadata` - Author, date, collection info
   - `TableOfContents` - Chapter/section navigation
   - `CitationTool` - Copy/paste citation formats
   - `ReadingProgress` - Scroll progress indicator
   - `FontControls` - Text size/theme adjustments
   - `SectionNavigator` - Jump to section

3. **Features**
   - Persistent scroll position (localStorage)
   - Font size adjustment (3 levels)
   - Reading theme toggle (light/sepia/dark)
   - Section highlighting on scroll
   - Copy section functionality
   - Print-friendly styles

## Dependencies

**Completed Before This Phase:**
- Phase 01: Foundation (API client, base components)
- Phase 02: App Shell (navigation, layout)
- Phase 03: Homepage
- Phase 04: Topic List
- Phase 05: Topic Detail

**Required APIs:**
- `GET /api/v1/documents/:id` - Document content
- `GET /api/v1/documents/:id/metadata` - Extended metadata
- `GET /api/v1/collections/:id` - Collection context
- `POST /api/v1/analytics/read` - Track reading session

## Exit Criteria

✓ All acceptance criteria in `acceptance.md` pass
✓ Manual verification tests in `tests.md` complete
✓ No mocked data - all content from real APIs
✓ Responsive on mobile, tablet, desktop
✓ Accessibility audit passes (WCAG 2.1 AA)
✓ Performance metrics met (TTI < 2s for 50k words)
✓ CURRENT_PHASE.md updated
✓ CHANGELOG.md updated

## Estimated Effort

**Complexity:** Large (L)
**Estimated Time:** 5-7 days
**Risk Level:** Medium (text rendering edge cases)

## Key Challenges

1. **Performance:** Rendering very long documents (100k+ words) without lag
2. **Typography:** Ensuring readable text at all font sizes
3. **Navigation:** Smooth scrolling to sections in long documents
4. **Memory:** Managing scroll position across sessions
5. **Accessibility:** Proper ARIA labels for screen readers
6. **Print:** Generating print-friendly layouts

## Success Metrics

- Time to Interactive < 2 seconds
- Scroll performance > 55fps on mid-range devices
- Zero layout shift during text loading
- 100% keyboard navigable
- Successful citation copy in < 1 click
