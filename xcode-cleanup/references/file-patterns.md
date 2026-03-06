# Swift File Patterns

## Directories to Search

Search for `.swift` files in these locations:

- `**/*.swift` - Recursive search from project root
- Main target directory (e.g., `ProjectName/`)
- Test targets (e.g., `ProjectNameTests/`, `ProjectNameUITests/`)
- Any SPM or custom package targets
- `Sources/` directory (if present)

## What to Look For

All files matching:
- Extension: `.swift`
- Contains default Xcode header format (6-7 lines with filename, target, creation info)

## What NOT to Modify

- Files without headers (rare, created outside Xcode)
- Files with already customized headers
- Generated files (usually have special comments)
