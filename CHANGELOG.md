# Changelog - BMad Method Shape Up Edition

All notable changes to this Shape Up fork of BMad Method will be documented in this file.

## [1.0.0] - 2025-01-18

### Added - Shape Up Integration

#### Core Shape Up Workflow
- **Shape Up Planning Workflow** (`.bmad-core/workflows/shape-up-planning.yaml`)
  - Appetite-first planning approach
  - Proper role distribution across BMad agents
  - Circuit breaker integration for appetite protection
  - Optional architect involvement for codebase access scenarios

#### Agent Role Enhancements
- **Analyst**: Problem & appetite validation focus
- **PM**: Business perspective & scope boundaries 
- **UX Expert**: Fat marker sketches using breadboarding technique
- **PO**: Deliverability & risk management
- **Architect**: Technical feasibility (optional, codebase-dependent)
- **Orchestrator**: Shape Up methodology compliance

#### Templates & Tasks
- **Final Pitch Template** (`.bmad-core/templates/shape-up-final-pitch-tmpl.yaml`)
  - Matches exact user pitch format requirements
  - Integrates all Shape Up methodology elements
  - Preserves developer autonomy while providing clear guidance
- **Shape Up Pitch Creation Task** (`.bmad-core/tasks/create-shape-up-pitch.md`)
- **Shape Up Methodology Checklist** (`.bmad-core/checklists/shape-up-pitch-checklist.md`)

#### Shape Up Methodology Features
- **Appetite-Driven Planning**: Time constraints drive solution shaping
- **Fat Marker Sketches**: Breadboarding technique for solution direction
- **Circuit Breakers**: Automatic stopping triggers for complexity protection
- **Developer Autonomy**: Technical decisions preserved for implementation teams
- **Betting Table Format**: Pitches ready for Shape Up decision-making process

### Enhanced from Original BMad

#### Planning Philosophy
- **Fixed Time, Variable Scope** instead of fixed scope, variable time
- **Problem-First Approach** with appetite validation before solution exploration
- **Business Outcome Focus** rather than feature-complete specifications

#### Risk Management
- **Circuit Breakers** replace traditional risk identification
- **Appetite Protection** built into every planning stage
- **Rabbit Hole Identification** using advanced elicitation techniques

#### Developer Experience
- **Preserved Technical Autonomy** - no over-prescription of technical solutions
- **Implementation Flexibility** - architecture guidance without constraints
- **Clear Boundaries** - explicit "no-gos" and scope limitations

### Compatibility

#### Maintains Full BMad Compatibility
- All existing BMad workflows remain functional
- Existing agents work in both traditional and Shape Up modes
- No breaking changes to core BMad functionality

#### IDE Integration
- Works with existing `@agent` syntax in IDE environments
- Compatible with both web and IDE-based BMad usage
- Maintains all existing BMad tool integrations

## Example Usage

### Traditional BMad (Still Works)
```
*workflow brownfield-fullstack
```

### New Shape Up Mode
```
*workflow shape-up-planning
```

## Migration Notes

- **No migration required** - this is additive functionality
- **Existing projects** can continue using traditional BMad workflows
- **New projects** can choose between traditional BMad or Shape Up approaches
- **Hybrid usage** is supported - use Shape Up for planning, traditional BMad for execution

## References

- [Shape Up Methodology](https://basecamp.com/shapeup) by Ryan Singer, Basecamp
- [Original BMad Method](https://github.com/bmad-method/bmad-method)

---

*This fork integrates Shape Up methodology principles while preserving all BMad Method capabilities.*
