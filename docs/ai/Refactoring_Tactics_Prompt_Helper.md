```markdown
# Helper Prompts for Reviewing `Refactoring_Tactics.md`

When reviewing the AI-generated `Refactoring_Tactics.md` for the `y_lb_demo_content` module, use these points to guide your evaluation. Ensure the AI's suggestions align with the specific nature and goals of this module, which primarily focuses on providing demo content via Drupal's migration system.

**1. Core Purpose & Migration Integrity:**

*   **Question:** Does the suggested refactoring preserve the module's core function: installing, importing, and uninstalling demo content cleanly using `drush mim --group=y_lb_demo_content` and `drush pmu y_lb_demo_content`?
*   **Check:** Verify that any suggested changes to migration file structure, dependencies (`migration_dependencies`), or grouping (`migration_group`) do not break the import/rollback process.
*   **Context:** This module is *meant* to be temporary. Refactoring should prioritize maintainability and clarity for developers creating *new* demo content, but not at the expense of the simple install/uninstall workflow for end-users.

**2. Migration File Structure:**

*   **Question:** If the AI suggests consolidating migration YAML files, is this practical within the Migrate API? Does it make understanding individual component migrations harder or easier?
*   **Check:** Ensure migration lookups (`migration_lookup` in `process` sections) still resolve correctly if files are merged or renamed. Confirm `migration_dependencies` remain accurate.
*   **Context:** There's a one-to-one mapping for many content types (e.g., `y_lb_demo_block_cards` depends on `y_lb_demo_block_cards_item`). Refactoring shouldn't obscure these relationships. The use of `embedded_data` is central; changes shouldn't complicate updating this data.

**3. Dependencies (Internal & External):**

*   **Question:** Does the refactoring respect the module's explicit dependencies listed in `composer.json` (e.g., `ycloudyusa/y_lb`, `drupal/lb_cards`, `open-y-subprojects/openy_custom`) and `y_lb_demo_content.info.yml`?
*   **Check:** Verify that suggestions don't assume different versions or functionalities from these dependencies. Ensure internal dependencies (like `y_lb_demo_media_image` depending on `y_lb_demo_file`) are maintained.
*   **Context:** The module integrates specific Layout Builder blocks and YMCA-related structures. Refactoring must be compatible with these specific components.

**4. PHP Code (EventSubscriber, Process Plugin):**

*   **Question:** Are suggestions for refactoring the `YLbDemoContentMigrationSubscriber` or `YLbMenuLinkClass` relevant to their specific, limited functions (cleaning up menus, adding CSS classes)?
*   **Check:** Ensure the subscriber still correctly interacts with migrate events (`MigrateEvents::PRE_IMPORT`, `MigrateEvents::POST_IMPORT`) and that menu cleanup/update logic remains sound. The process plugin is simple; major refactoring is likely unnecessary.
*   **Context:** The PHP code is minimal and serves specific purposes within the migration lifecycle. Over-engineering should be avoided.

**5. Configuration (Webforms, Menus):**

*   **Question:** If refactoring touches menu link or webform migrations, does it maintain the structure and content defined in the source YAML (e.g., `webform.webform.contact_us.yml`, `migrate_plus.migration.y_lb_demo_menu_link_main.yml`)?
*   **Check:** Confirm that menu hierarchies (`parent_id`, `parent_link_path`) and webform elements defined in the migrations are preserved.
*   **Context:** These configurations are part of the demo setup and need to be imported correctly.

**6. Assets & Submodule:**

*   **Question:** Do suggestions consider the image assets in `assets/images` and how they are referenced by the `y_lb_demo_file` and `y_lb_demo_media_image` migrations? Does refactoring impact the `y_lb_demo_content_af_promotion` submodule and its specific migrations (`y_lb_demo_block_af`, `y_lb_demo_page_af_promo`)?
*   **Check:** Ensure file paths and dependencies related to assets and the submodule remain valid. The submodule has its own install hook and migration group (`y_lb_demo_content_af`).
*   **Context:** Asset handling is tied directly to migrations. The submodule isolates specific functionality (Activity Finder promotion) which might be optional.

**Overall:**

*   Prioritize clarity and maintainability *for developers adding/updating demo content migrations*.
*   Critically evaluate suggestions for complexity – does the refactoring add significant overhead to a module designed for simple data import/rollback?
*   Ensure suggestions are grounded in the specifics of Drupal's Migrate API and the Layout Builder ecosystem used by YMCA Website Services.
```