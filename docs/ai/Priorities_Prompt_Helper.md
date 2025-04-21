Okay, here's the generated content for `docs/ai/Priorities_Prompt_Helper.md` based on the provided codebase structure and content:

```markdown
# AI Prompt Helper: Refining `Priorities.md` for y_lb_demo_content

This document provides guidelines for human editors reviewing the AI-generated `Priorities.md` file for the `y_lb_demo_content` module. Use these points to ensure the AI's output accurately reflects the project's specific context and potential priorities based *only* on the provided codebase.

**Core Purpose & Context:**

*   **Central Theme:** Verify the AI strongly emphasizes that the *absolute core priority* is the successful **importation of demo content via Drupal Migrations**. This module's sole purpose is to provide sample data for `y_lb` (YMCA Layout Builder).
*   **Ephemeral Nature:** Ensure the AI understands and potentially prioritizes the intended workflow: `enable -> import (drush mim --group=y_lb_demo_content) -> uninstall`. The module isn't meant for long-term enablement.
*   **Target Audience:** Priorities should reflect the needs of developers/site builders setting up a YMCA Website Services site who need to see examples of Layout Builder components configured.

**Key Technical Priorities (Check if AI Included/Emphasized):**

*   **Migration Integrity:**
    *   Did the AI prioritize the correctness and reliability of the `migrate_plus.migration.*.yml` files? This includes:
        *   Accurate `source` configuration (using `embedded_data`).
        *   Correct `process` mapping, especially `migration_lookup` to link demo entities.
        *   Valid `destination` entity types and bundles (`entity:node`, `entity:block_content`, etc.).
        *   Functional `migration_dependencies` to ensure the correct import order.
*   **Component Coverage:** The primary goal is demonstrating various Layout Builder blocks (`lb_hero`, `lb_cards`, `lb_ping_pong`, `lb_accordion`, `lb_openy_map`, etc.). Priorities should reflect ensuring these components are included, configured correctly in demo pages (`y_lb_demo_page_*.yml`), and visually represent the intended features.
*   **Dependencies:**
    *   Does the AI acknowledge the external PHP and Drupal module dependencies (`composer.json`) like `ycloudyusa/y_lb`, `lb_cards`, `ws_promotion`, etc.? Maintaining compatibility with specified versions could be a priority.
    *   Internal dependencies between migrations (`migration_dependencies`) are critical for successful imports.
*   **Custom Code:**
    *   Did the AI identify the `EventSubscriber/YLbDemoContentMigrationSubscriber.php`? This handles pre/post-import logic (menu cleanup, menu CTA block attachment). Its reliability might be a specific priority.
    *   Did the AI identify the custom `MigrateProcessPlugin` (`YLbMenuLinkClass.php`)? Its correct functioning is necessary for menu link styling.
*   **Data Source:** Emphasize that demo content is hardcoded (`embedded_data`). Maintaining this data (keeping it relevant, fixing typos, updating links like `[site:url]`) might be a distinct priority.
*   **Submodule (`y_lb_demo_content_af_promotion`):** Check if the AI recognized this submodule and its specific focus (Activity Finder with Promotions) and associated migrations/tags.

**Potential AI Blind Spots / Areas for Human Refinement:**

*   **Specificity of "Demo":** Ensure the AI doesn't treat this like a standard feature module. Priorities should *always* relate back to the quality, accuracy, and completeness of the *demonstration content* and the *import process*.
*   **Fragility of Custom Code:** The AI might list the Event Subscriber or Process Plugin but might not grasp their potential fragility during Drupal updates or refactoring compared to standard migration features. This could be a higher priority for testing/maintenance than the AI suggests.
*   **Migration Tags:** The AI might miss the significance of the `migration_tags` (`openy_complete_installation`, `openy_standard_installation`, `openy_extended_installation`). While not heavily used in the provided files, their presence suggests different import scopes might exist or be planned, potentially affecting priorities.
*   **Developer Experience:** While migrations are key, the AI might overlook the importance of the clear `drush` commands in the README and the ease of the install/import/uninstall workflow.
*   **Visuals/Theming:** Although templates are minimal, the demo content relies on the `y_lb` theme and component styles (`ws_style_option`, etc., mentioned in migrations). Ensuring the imported content *looks* correct within the target theme context is an implicit priority the AI might understate.
*   **Content Maintenance:** The AI might focus on migration *mechanics*. A human should ensure priorities reflect the need to periodically review and update the *actual demo text and image content* within the YAML files to keep it relevant. Check the Git Log summary for recent content updates (e.g., buttons, meta descriptions, link tokens) – this indicates ongoing maintenance is valued.
*   **Performance/Size:** The Git log shows image optimization efforts. The AI might not infer that the *size* of the demo content package (especially images) or the *speed* of the migration import could be relevant (though likely secondary) priorities.

**Instruction:** Review the AI-generated `Priorities.md`. Use the points above to add, remove, or reorder priorities to better match the specific nature and structure of the `y_lb_demo_content` module. Ensure the final `Priorities.md` clearly guides development and maintenance efforts focused on delivering high-quality demo content via migrations.
```