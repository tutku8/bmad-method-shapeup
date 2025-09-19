# Working Artifacts Folder

This folder contains **temporary working artifacts** created during Shape Up planning sessions.

## Purpose

- **Working files**: Intermediate artifacts created during the Shape Up workflow
- **Not committed**: This entire folder is ignored by git (.gitignore)
- **Session-specific**: Files are created fresh for each planning session
- **Temporary**: Delete or archive when planning session is complete

## Files Created During Shape Up Workflow

- `discovery-analysis.md` - Analyst's complete discovery (raw idea + current state + appetite + validation)
- `shape-up-pitch.md` - PM's main Shape Up pitch artifact
- `solution-sketches.md` - UX Expert's text-based breadboards
- `task-breakdown.md` - PO's task breakdown with architect estimates

## Usage

### During Planning Session
1. **Let the workflow create files here** - All agents save to `docs/working/`
2. **Review and iterate** - Agents can update files as needed
3. **Scope cutting iterations** - PM updates pitch when estimates exceed appetite

### After Planning Session
1. **Copy final pitch** - Move `shape-up-pitch.md` to main `docs/` folder if satisfied
2. **Archive or delete** - Clean up working files
3. **Commit final pitch** - Only the final, polished pitch goes to git

## Benefits

✅ **Clean git history** - No intermediate planning artifacts in commits  
✅ **Iterative refinement** - Agents can update files during scope cutting  
✅ **Session isolation** - Each planning session starts fresh  
✅ **Final artifact control** - You decide what gets permanently saved  

## Example Structure After Session

```
docs/
├── working/                    # Temporary (not committed)
│   ├── discovery-analysis.md   # Analyst work
│   ├── shape-up-pitch.md      # PM main artifact
│   ├── solution-sketches.md   # UX breadboards
│   └── task-breakdown.md      # PO/Architect estimates
├── examples/                   # Committed examples
│   └── mw-2-0-final-pitch.md  # Reference examples
└── my-feature-pitch.md        # Your final pitch (copied from working/)
```

This keeps your repository clean while providing full working space for Shape Up planning sessions!
