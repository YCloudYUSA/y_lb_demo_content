```markdown
# AI Roadmap Prompt Helper for y_lb_demo_content

## Purpose of this Document

This document provides guidelines for human editors reviewing the AI-generated `Roadmap.md` for the `y_lb_demo_content` module. Its goal is to help align the AI's generic suggestions with the specific context, goals, and potential future directions evident from the module's codebase.

## Module Context

Based *only* on the codebase:

*   **Primary Goal:** This module provides demo content via Drupal migrations (`migrate_plus`) for the Layout Builder (`y_lb`) components used in the YMCA Website Services distribution.
*   **Content Types:** It creates demo nodes (articles, events, landing pages, locations, promotions), block content (various Layout Builder components like accordions, banners, cards, grids), media entities (images from `assets/images`), files, taxonomy terms (tags), menu links (main, account, helpful links, utility), and webforms.
*   **Mechanism:** Uses embedded data sources in YAML migration files. Includes install/uninstall hooks for migration execution and basic site setup (front page). An Event Subscriber handles pre/post-migration tasks (menu cleanup, linking CTA blocks).
*   **Dependencies:** Relies heavily on `ycloudyusa/y_lb`, various `lb_*` component modules, Open Y modules (`openy_custom`, `openy_map_lb`, etc.), promotion modules (`ws_promotion*`), and Drupal core/contrib migration modules.
*   **Structure:** Includes a submodule (`y_lb_demo_content_af_promotion`) for specific Activity Finder + Promotion demo content. Migrations are tagged for different installation profiles (`openy_standard_installation`, `openy_extended_installation`, etc.).

## Reviewing the AI-Generated Roadmap.md

When reviewing the AI-generated roadmap, consider the following points and questions to ensure it aligns with the project's specific nature:

1.  **Focus on Demo Content:**
    *   Does the roadmap prioritize adding/updating *demo content* for `y_lb` components? The primary purpose isn't to add *new features* to the site itself, but to *demonstrate* existing features via content.
    *   Are roadmap items directly tied to showcasing specific Layout Builder blocks or features provided by the dependencies (e.g., `lb_cards`, `lb_hero`, `ws_promotion`)?

2.  **Maintenance and Updates:**
    *   Does the roadmap account for updating existing demo content when the underlying `y_lb` components or dependencies change? (e.g., If `lb_cards` gets a new feature, the demo content migration `y_lb_demo_block_cards` might need updating).
    *   Does it suggest keeping dependencies (like `y_lb`, `lb_cards`, PHP version) up-to-date as reflected in `composer.json`?

3.  **Completeness and Realism:**
    *   Does the roadmap suggest adding demo content for any `y_lb` components that are *currently missing*?
    *   Does it propose improvements to the *quality* or *realism* of the existing demo text and images? (e.g., replacing "Lorem Ipsum" in `y_lb_demo_block_table_block.yml` or adding more varied event/article examples).
    *   Are there plans to address placeholders mentioned in the content (e.g., "Placeholder for the schedules block", "Placeholder for the membership finder block") by creating actual demo implementations or linking to relevant modules?

4.  **Technical Improvements & Refactoring:**
    *   Does the roadmap include potential technical improvements based on past activity? (e.g., Further image optimization, refactoring migrations for clarity, replacing deprecated approaches like the past move from `lb_code_block` to `lb_table`).
    *   Does it consider standardizing migration structures or processes?

5.  **Integration and Submodules:**
    *   Does the roadmap account for demo content related to integrations, like the Activity Finder + Promotion example in the `y_lb_demo_content_af_promotion` submodule? Should more such examples be added?
    *   Does it consider the different installation profiles (`openy_standard_installation`, etc.) and whether demo content needs tailoring for each?

6.  **Scope:**
    *   Ensure roadmap items are within the scope of *demo content migrations*. Avoid suggestions that belong in the `y_lb` module itself or other functional modules (e.g., adding a *new* type of Layout Builder block belongs in `y_lb` or a specific `lb_*` module, not here).

**Example Check:** If the AI suggests "Implement user authentication improvements", this is likely out of scope. A relevant suggestion would be "Update demo landing pages (`y_lb_demo_page_*`) to showcase how authenticated user content might differ" or "Add demo user roles and permissions if relevant to showcased features". If the AI suggests "Add a Calendar Component", the relevant item for *this* module would be "Create demo content migration (`y_lb_demo_block_calendar`) once the corresponding `lb_calendar` module exists".
```