# MW 2.0 - Shape Up Pitch

## Problem

**Problem Statement:** Maintenance window communication is frustratingly fragmented, requiring users to separately manage maintenance windows and announcements, leading to poor adoption and confused end-users during maintenance periods.

**Who Experiences This:** 
- **Primary:** Operations teams managing infrastructure with public status pages (89.3% of paying users avoid MW feature entirely)
- **Secondary:** End-users visiting status pages during maintenance (see "Up" status during planned downtime)

**Current Pain Points:**
- Users must create announcements separately from maintenance windows (friction)
- Status pages show misleading "Up" status during planned maintenance (confusion)
- No easy way to notify PSP subscribers about upcoming maintenance (communication gap)
- Maintenance window adoption is critically low (10.7% of paying users, 7.8% of churned users)

**Evidence:**
- #2 most requested feature on Nolt feedback platform
- Usage data: 89.3% of paying users never use MW feature
- User feedback: "It would be nice not to have to create and manage a separate announcement"
- Support impact: Confusion during maintenance leads to support tickets and lost trust

**Current Workarounds:** Users either skip maintenance communication entirely or manually create separate announcements, leading to inconsistent communication and poor user experience.

## Appetite

**Time Investment:** 3 weeks for 1 person (120 hours maximum)

**What We're Willing to Spend:** 
- Up to 120 hours for integrated MW-announcement workflow
- Time to solve core communication friction
- Effort to provide accurate status indicators during maintenance

**What We're NOT Willing to Spend:**
- Time on complex email scheduling automation (advance notifications)
- Effort on comprehensive timezone reconciliation across all systems
- Resources on recurring maintenance automation complexity
- Time on advanced announcement management features

**Appetite Rationale:** This is the #2 requested feature with clear adoption impact. 3 weeks investment should significantly improve MW adoption (target: 10.7% → >20%) and reduce support burden.

## Solution (Fat Marker Sketch)

**High-Level Approach:** Integrate maintenance window creation with announcement workflow using smart contextual prompts, plus add distinct "Paused for Maintenance" status indicators across status displays.

**Key Elements:**
- **Smart Announcement Integration:** Show "☑️ Notify PSP subscribers" checkbox during MW creation when relevant (PSP subscribers exist)
- **Template-Based Approach:** Pre-fill announcement with MW details, user customizes as needed, no ongoing sync complexity
- **Maintenance Status Indicators:** New "Paused for Maintenance" status distinct from "Up"/"Down" on PSP and dashboard
- **Manual Control:** "Mark as Done" functionality for early maintenance completion
- **Visual Organization:** Group MW by status (Active | Scheduled | Completed) for better workflow management

**Core User Flows:**
1. **MW Creation Flow:** Create MW → Smart checkbox appears → Optional announcement creation → Complete setup
2. **Status Display Flow:** MW starts → Status changes to "Paused for Maintenance" → MW ends → Status reverts
3. **Management Flow:** View organized MW list → Quick "Mark as Done" actions → Clear status tracking

**Fat Marker Sketch:** Single integrated workflow that eliminates separate announcement creation while providing accurate status communication. Focus on workflow integration, not technical complexity.

## Rabbit Holes & Circuit Breakers

### Potential Rabbit Holes
- **Email Integration Complexity:** Existing email system might require significant modification beyond simple piggyback approach (Risk: 20+ hours)
- **PSP Status System Refactoring:** Current status rendering might not easily accommodate new status types (Risk: 15+ hours)  
- **Smart Detection Logic:** PSP-monitor relationship queries might be complex or slow (Risk: 8+ hours)
- **Timezone Coordination:** Consistent timezone handling across MW/announcement/email systems (Risk: 10+ hours)
- **Event System Reliability:** Auto-publish/unpublish might need robust error handling and retry logic (Risk: 15+ hours)

### Circuit Breakers
1. **Total scope >80 hours (67% of appetite)** → Stop, re-evaluate entire approach, consider deferring stories
2. **Email integration >20 hours** → Switch to manual email sending approach
3. **PSP integration requires refactoring existing status logic** → Implement simple status badges only
4. **Smart detection logic >8 hours** → Remove smart detection, always show checkbox
5. **Any story exceeds original estimate by >50%** → Stop, break down or defer that story
6. **Existing system modification required** → Find alternative approach that extends rather than modifies

## No-Gos (Boundaries)

**Explicit Exclusions:**
- Advance email scheduling ("Send notification X hours before MW starts")
- Recurring maintenance window email automation with complex scheduling
- Comprehensive timezone reconciliation across all UptimeRobot systems
- Complex announcement-MW bidirectional synchronization
- Advanced email preference management for MW notifications
- Bulk announcement management for recurring MW

**Scope Protection:**
- Template approach only - no ongoing sync between MW and announcements after creation
- Extend existing systems only - no refactoring of legacy status or email code
- Single checkbox integration - resist complex multi-step announcement workflows
- Basic email automation only - resist advanced scheduling features

**Future Considerations:** Advanced scheduling, recurring automation, and comprehensive timezone handling are valuable but belong in future cycles after core workflow adoption is validated.

## Success Criteria

**Definition of Done:** MW communication friction is eliminated through integrated workflow, and status indicators accurately represent maintenance state, leading to measurable adoption improvement.

**Success Metrics:**
- **MW Adoption Rate:** >20% of paying users use MW at least once per 30 days (baseline: 10.7%)
- **Workflow Integration:** >60% of MW created with linked announcements
- **Communication Efficiency:** Time-to-communicate maintenance <2 minutes (baseline: ~15 minutes)
- **Support Impact:** 40% reduction in maintenance-related support tickets

**Expected User Behavior Changes:** 
- Operations teams naturally create announcements during MW setup instead of skipping communication
- End-users see accurate maintenance status instead of confusing "Up" indicators
- Increased MW feature engagement due to reduced workflow friction

## Trade-off Zones

**Technical Decisions (Developer Choice):**
- Database schema design for maintenance_status table and MW-announcement relationships
- PSP status indicator implementation approach (CSS classes, rendering logic, theme integration)
- Smart PSP detection query optimization and caching strategy
- Email integration architecture within existing infrastructure

**UI/UX Flexibility:**
- Exact visual design for "Paused for Maintenance" status (color, icons, styling)
- MW status grouping layout and visual hierarchy
- Announcement preview section design and interaction patterns
- Confirmation dialog styling and messaging tone

**Performance Trade-offs:** 
- Balance between real-time smart detection vs static form load detection
- PSP status rendering optimization vs feature richness
- Email sending reliability vs immediate delivery

**Implementation Flexibility:** 
- Choice of frontend framework patterns for new UI components
- Database migration strategy and rollback approach
- Testing strategy and coverage levels
- Error handling and user feedback mechanisms

## Betting Table Summary

**Problem Worth:** High - #2 most requested feature with clear adoption and support impact. Current 10.7% adoption represents significant untapped value.

**Appetite Justification:** 3 weeks investment for 2x adoption improvement and 40% support reduction is excellent ROI. Problem has been validated through user feedback and usage analytics.

**Delivery Confidence:** High (80%) - Solution uses template approach to avoid complex sync logic, extends existing systems rather than rebuilding, and has been scope-validated through multi-agent analysis.

**Key Risks:** 
1. Email integration complexity (mitigated by piggyback approach)
2. PSP status system integration (mitigated by separate status tables)
3. Smart detection performance (mitigated by circuit breaker at 8 hours)

**Recommendation:** GO - Well-shaped problem with appetite-aligned solution, clear circuit breakers, and strong user value proposition. Ready for betting table consideration.
