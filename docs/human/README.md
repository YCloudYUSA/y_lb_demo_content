```markdown
# YMCA Layout Builder Demo Content (y_lb_demo_content)

## Project Purpose

This Drupal module provides a set of migrations to populate a YMCA Website Services site with demonstration content specifically designed to showcase the capabilities of the Layout Builder (`y_lb`) module and its associated components. It creates various pages, content types, blocks, menus, and configuration examples typical for a YMCA website.

The primary goal is to offer a visual and functional example of how Layout Builder can be used within the YMCA context, making it easier for users to understand and utilize the available features.

## Key Features (Inferred from Code)

Based on the migrations and configuration files, this module creates the following demo elements:

*   **Demo Pages:**
    *   Homepage (`/demo-home-page`)
    *   Who We Are
    *   Programs (Overview, Category, Individual Example - Youth Soccer)
    *   Locations (Finder, Individual Branch Example - Downtown Springfield, Branch Child Page Example - Child Care)
    *   Membership
    *   Schedules
    *   Events Listing
    *   Articles Listing
    *   Contact Us
    *   Donate
    *   Jobs
    *   Volunteer Opportunities
    *   Join the Y
    *   Activity Finder (Standard and with Promotion Block)
    *   Promotions Showcase Page
    *   Dummy/Placeholder pages for linking

*   **Layout Builder Components (as Demo Blocks):**
    *   Hero Banners (Chevron, Frame, Overlay, Standard, Small variants)
    *   Cards (Standard, Color, Chevron, Overlay variants)
    *   Accordions & Accordion Items (including FAQ examples)
    *   Carousels & Carousel Items
    *   Icon Grids & Icon Grid Items (for principles, stats, contact methods)
    *   Ping-Pong Layouts (Alternating Image & Text)
    *   Statistics Blocks
    *   Testimonials & Testimonial Items
    *   Partner/Sponsor Logo Grids
    *   Donate Blocks (with giving amounts)
    *   Webforms (Contact Us, Try the Y examples)
    *   Social Links (Branch-specific)
    *   Branch Amenities List
    *   Branch Hours Display
    *   Listings & Filters (Events, Articles)
    *   Featured Content Blocks (Events, Articles)
    *   Activity Finder Block
    *   Simple Menus (Quick Links style)
    *   Basic HTML/Table Block
    *   Modal Promo Block

*   **Content Types & Entities:**
    *   Demo Articles (Blog, News, Press Release types)
    *   Demo Events (including example recurring event setup)
    *   Demo Promotions
    *   Demo Location (Branch)
    *   Demo Taxonomy Terms (Tags: Seniors, Family, etc.; Location Amenities)
    *   Demo Media (Images for pages, blocks, articles, events)
    *   Demo Files (Image assets)

*   **Menus & Configuration:**
    *   Demo Main Navigation Menu structure
    *   Demo Account Menu (Join link)
    *   Demo Utility Menu (Contact, Give, Jobs)
    *   Demo Helpful Links Menu (Footer)
    *   Demo Branch Menu (Location Page)
    *   Integration with Menu Item Extras (adding a CTA block to a menu item)
    *   Site Configuration (Sets Site Name to "YMCA OF [SPRINGFIELD]", sets front page)

## Installation & Setup

This module is intended to be installed temporarily to import the demo content via Drupal migrations. It requires Drush.

1.  **Enable the module:**
    ```bash
    drush en y_lb_demo_content
    ```
2.  **Run the migrations:**
    ```bash
    drush mim --group=y_lb_demo_content
    ```
    *(Note: If using the `y_lb_demo_content_af_promotion` submodule, you might also need to run `drush mim --group=y_lb_demo_content_af` or follow its specific instructions).*
3.  **Uninstall the module (Optional but Recommended):** The module is not needed after the content is imported.
    ```bash
    drush pmu y_lb_demo_content
    ```

**Dependencies:** This module requires `y_lb`, `lb_cards`, `openy_custom`, `ws_promotion`, `lb_hero`, and several other Layout Builder component modules, as well as Migrate Plus and Migrate Tools. See `composer.json` for the full list.

## Basic Usage

After running the installation steps above, the site will be populated with the demo pages, blocks, and content listed under Key Features.

*   The site's front page will be set to `/demo-home-page`.
*   Navigate through the main menu and other demo pages to see examples of Layout Builder layouts and components in action.
*   Review the created content (Articles, Events, Locations, etc.) in the Drupal admin interface.
*   Examine the Layout Builder configuration for the demo pages (`landing_page_lb` node type) to see how the layouts are constructed.

**Note:** This module provides *demonstration* content. It uses placeholder text (like "Lorem Ipsum" and "[Springfield]") and example links. It is not intended for direct use on a production site without significant modification and replacement of demo assets and text. It serves as a starting point and educational tool for using Layout Builder in the YMCA Website Services distribution.
```