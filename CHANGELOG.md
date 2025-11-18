# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.3.0] - 2025-11-18

### Added

- **File-level card support**: Add entire org files as cards, perfect for org-roam workflows
  - New command `org-workbench-add-file` to add files as cards
  - File cards use `#+ID:` keyword at file level for identification
  - File cards display with `[FILE]` prefix for visual distinction
  - File cards use `#+TITLE:` keyword or filename as title

- **Enhanced sync and navigation**:
  - `org-workbench-goto-source` now supports both file and heading cards
  - `org-workbench-sync-card` can sync file cards from source
  - `org-workbench-sync-all-cards` handles mixed workbenches (file + heading cards)

- **Documentation improvements**:
  - Comprehensive documentation for file card feature
  - Added recommended key bindings section (no default bindings)
  - Updated technical details explaining card structure
  - Chinese README fully updated

### Changed

- **No default key bindings**: Removed all preset key bindings to give users full control
  - Users can now choose their own preferred key combinations
  - Documentation provides suggested bindings as a starting point
  - Prevents conflicts with other packages

- **Data structure enhancement**:
  - `:level 0` now indicates file-level cards (vs `1-N` for heading cards)
  - Unified card structure supports both types seamlessly
  - Zero breaking changes - existing heading cards work unchanged

### Technical Details

- Added 7 new core functions for file card support
- Enhanced 4 existing functions for mixed card type handling
- ~150 lines of new code with zero linter errors
- 100% backward compatible with existing workbenches

### Design Philosophy

This release follows Linus Torvalds' software design principles:

- **No special cases**: File and heading cards share the same data structure
- **Never break userspace**: Complete backward compatibility
- **Simplicity**: Minimal code changes with maximum functionality
- **Pragmatism**: Solves real user needs (org-roam integration)

## [0.1.0] - 2025-01-XX

### Added

- Initial release of org-workbench
- Digital card workbench system for org-mode
- Support for heading-based cards
- Multiple workbench management
- Persistent storage across sessions
- ID system integration (org-supertag, org-roam, org-brain)
- Card operations: add, remove, reorder, sync
- Export to org-links functionality
- Clean org-mode display interface

[0.3.0]: https://github.com/yibie/org-workbench/compare/v0.1.0...v0.3.0
[0.1.0]: https://github.com/yibie/org-workbench/releases/tag/v0.1.0
