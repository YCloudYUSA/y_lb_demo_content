```markdown
# Roadmap for y_lb_demo_content

This roadmap outlines the historical development and potential future directions for the `y_lb_demo_content` module, based *solely* on the provided codebase structure, dependencies, git log history, and file contents.

## Historical Achievements (Based on Git Log Analysis)

*   **Core Framework:** Established a migration-based system (`migrate_plus`, `migrate_tools`) using embedded data to populate demo content for a YMCA Layout Builder environment.
*   **Comprehensive Component Demos:** Added demo content migrations for a wide array of Layout Builder components, including:
    *   Various Banner types (Chevron, Frame, Overlay, Standard, Small)
    *   Cards (Standard, Color, Chevron, Overlay variations)
    *   Accordions & Accordion Items
    *   Carousels & Carousel Items
    *   Icon Grids & Items
    *   Ping Pong blocks
    *   Statistics & Items
    *   Testimonials & Items
    *   Partners & Items
    *   Simple Menu blocks
    *   Basic HTML/Table blocks (formerly Code Block)
    *   Social Links
    *   Location Finder (Map)
    *   Branch Amenities & Hours
    *   Donate blocks & Giving Amounts
    *   Webforms (Contact Us, Try the Y)
    *   Featured Content blocks (Events, Articles)
    *   Listing/Filter blocks (Events, Articles)
    *   Menu CTA blocks
    *   Modal blocks
*   **Content Entity Demos:** Created migrations for core content types:
    *   Articles (including different types like blog, news, press release)
    *   Events (including support for recurring dates)
    *   Locations (Branches)
    *   Promotions
    *   Taxonomy Terms (Tags, Area - via dependency)
    *   Media (Images) and Files
*   **Layout Builder Page Demos:** Assembled various full landing pages (`landing_page_lb` type) using the demo blocks via Layout Builder section configuration in migrations. Examples include: Homepage, Who We Are, Programs Overview/Category/Individual, Location Finder/Individual/Child Page, Membership, Schedules, Events, Contact Us, Join the Y, Donate, Jobs, Volunteer Opportunities, Articles Listing, Dummy/Paragraphs Demo.
*   **Menu System Demos:** Implemented migrations for multiple menus (Main, Account, Utility, Helpful Links) and included custom logic for menu item classes and linking the Menu CTA block post-migration.
*   **Promotions Integration:** Added `ws_promotion` dependency and integrated promotion demo content, including specific promo blocks/pages.
*   **Activity Finder (AF) Integration:** Created a dedicated sub-module (`y_lb_demo_content_af_promotion`) for AF4-specific demo content with promotions.
*   **Refinements & Maintenance:**
    *   Updated content structure (e.g., moving card descriptions to rich text).
    *   Added specific fields (e.g., heading levels for banners, meta descriptions/images for pages).
    *   Improved demo content clarity (e.g., adding button style examples).
    *   Optimized assets (image resizing and optimization).
    *   Updated dependencies (`composer.json`).
    *   Fixed bugs and inconsistencies identified during QA (e.g., links, meta images, migration tags, sponsor section width).
    *   Updated branding (e.g., Twitter to X).

## Potential Future Directions (Inferred from Codebase and Scope)

*   **Dependency Management:**
    *   Regularly review and update composer dependencies (`y_lb`, `lb_*` blocks, `ws_promotion`, etc.) to ensure compatibility and leverage new features.
    *   Update PHP version constraints as required by dependencies or Drupal core.
*   **New Component Demos:**
    *   As new Layout Builder components are added to the `y_lb` ecosystem or its dependencies, create corresponding demo content migrations (blocks, potentially new pages or page updates).
*   **Enhance Existing Demos:**
    *   Add more variations of existing components to showcase different styling or configuration options (e.g., different `ws_style_option` combinations for banners or cards if supported).
    *   Review demo text and images periodically for relevance and freshness. Event dates use relative times (`+X days`), which is good practice.
    *   Expand the "Dummy" or "Paragraphs Demo Content" page to include more examples of rich text features or complex HTML structures supported by the WYSIWYG editor.
*   **Migration Improvements:**
    *   Consider adding more sophisticated examples if the core components support more complex data relationships than currently demonstrated.
    *   Enhance the pre/post-migration event subscriber (`YLbDemoContentMigrationSubscriber`) if more complex setup or cleanup tasks become necessary.
*   **Code Modularity:**
    *   Evaluate if other optional feature demos (like Promotions) could be moved into sub-modules similar to `y_lb_demo_content_af_promotion` to keep the main module focused and reduce default dependencies.
*   **Documentation & Examples:**
    *   Enhance the `README.md` with more detailed examples or explanations if users encounter common issues.
    *   Ensure demo content clearly explains *what* feature or component variation it is demonstrating.
*   **Testing:**
    *   While not explicitly shown, implementing automated tests (e.g., Kernel tests for migrations, Functional tests for page layouts) could improve maintainability.
```