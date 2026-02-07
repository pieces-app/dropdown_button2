# Fork Changes Documentation

This document tracks all custom modifications, patches, and deviations from the upstream `AhmedLSayed9/dropdown_button2` repository.

## Fork Information

- **Fork Repository**: `https://github.com/pieces-app/dropdown_button2`
- **Upstream Repository**: `https://github.com/AhmedLSayed9/dropdown_button2`
- **Current Branch**: `master`
- **Fork Version**: `2.0.0`
- **Upstream Latest**: `2.3.9` (stable), `3.0.0-beta.24` (prerelease)
- **Commits Ahead**: 4
- **Commits Behind**: 328
- **Last Upstream Merge**: Fork created from upstream v2.0.0

## Custom Modifications

### 1. Overlay Colors Refactoring
- **Commit**: `a8dc84f`
- **Changes**:
  - Refactored overlay color handling in `dropdown_button2.dart`
  - Formatting/code style alignment (line wrapping, indentation)
  - Minor structural changes to `dropdown_button2_data.dart`
- **Files Modified**:
  - `lib/src/dropdown_button2.dart` (272 lines changed: 90 insertions, 186 deletions)
  - `lib/src/dropdown_button2_data.dart` (4 lines changed)
- **Reason**: Custom overlay color behavior for Pieces UI

### 2. SDK Constraint Bumps
- **Commits**: `3db632f`, `9322fb8`
- **Changes**:
  - Bumped Dart SDK constraint
  - Updated Flutter dependency versions
- **Reason**: Compatibility with workspace Dart SDK requirements

## Important Note: Structural Divergence

The upstream has **restructured to a monorepo** using Melos with `packages/` directories. Our fork uses the **old flat structure** from v2.0.0 where library code lives directly in `lib/src/`. This means a simple `git merge` will not work -- the merge requires either:

1. Rebasing our changes onto the upstream's new monorepo structure
2. Or extracting just the `packages/dropdown_button2/` subdirectory from upstream and applying our overlay color changes

## Upstream Sync Status

- **Current Gap**: 328 commits behind upstream/master
- **Complexity**: HIGH -- upstream restructured to monorepo
- **Priority**: HIGH -- missing 9+ versions of bug fixes and improvements

### Recommended Sync Approach
1. Create a new branch from upstream/master
2. Extract `packages/dropdown_button2/` content to match our structure
3. Re-apply the overlay colors changes
4. Evaluate if the overlay color changes are still needed in the newer API
5. Test thoroughly against Pieces frontend

## Why This Fork Exists

1. **Overlay Colors**: Custom overlay color behavior required for Pieces UI design
2. **Historical**: Fork predates upstream's monorepo migration

## Future Considerations

1. **Evaluate Fork Necessity**: The overlay color changes may now be achievable through upstream's expanded API (2.3.9 has more customization options)
2. **Consider 3.0.0**: Upstream is actively developing v3.0.0 with breaking changes
3. **Upstream Contribution**: If overlay color customization is still needed, consider contributing it upstream

## Contact

For questions about this fork or to request changes, contact the Pieces development team.
