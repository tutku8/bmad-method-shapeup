# Project Brief: MW 2.0 - Maintenance Window Enhancement

**Session Date:** September 18, 2025  
**Facilitator:** Business Analyst Mary  
**Participant:** Product Team  

## Executive Summary

MW 2.0 enhances UptimeRobot's maintenance window functionality to address the #2 most requested feature: better maintenance communication. The project focuses on integrating maintenance windows with announcements and providing clear "Paused for Maintenance" status indicators. Current adoption is low (10.7% of paying users) due to poor communication workflows and confusing status displays during maintenance.

**Target Outcome:** Increase MW adoption to >20% of paying users by making maintenance communication effortless and status displays accurate.

## Problem Statement

**Current State Pain Points:**
- Maintenance information is poorly communicated to users (2nd top requested feature)
- Announcements and maintenance windows are managed separately, causing inefficiency
- Status pages show "Up" during maintenance, which is misleading to end-users
- Users must manually create separate announcements for each maintenance window
- No clear visual distinction between maintenance vs actual downtime

**Impact Quantification:**
- Only 10.7% of paying users adopt maintenance windows
- 92.2% of churned users never used the feature
- Poor communication leads to support tickets and lost trust
- Status page credibility is undermined when showing "Up" during planned maintenance

**Why Existing Solutions Fall Short:**
- Decoupled announcement creation creates friction
- No maintenance-specific status indicators
- Manual processes discourage adoption
- Inconsistent timezone handling across features

## Proposed Solution

**Core Concept:** Integrate maintenance window creation with announcement publishing and introduce clear "Paused for Maintenance" status indicators across all user-facing surfaces.

**Key Differentiators:**
- **Seamless Integration:** Create announcements directly during MW setup
- **Clear Status Communication:** Distinct maintenance status vs downtime
- **Automated Workflows:** Reduce manual announcement management
- **Consistent Experience:** Unified timezone and permission handling

**High-Level Vision:**
Transform maintenance windows from a rarely-used feature into an essential tool that enhances rather than complicates user communication workflows.

## Target Users

### Primary User Segment: Operations Teams with Status Pages
**Profile:** Technical operations teams managing infrastructure with public status pages
**Current Behaviors:** 
- Schedule maintenance during low-traffic periods
- Manually communicate maintenance via multiple channels
- Struggle with coordinating announcements and actual maintenance
**Specific Pain Points:**
- Time-consuming separate announcement creation
- Confusion about maintenance vs incident status
- Difficulty managing subscriber notifications
**Goals:** Streamline maintenance communication while maintaining transparency

### Secondary User Segment: End-Users (Status Page Visitors)
**Profile:** Customers and stakeholders checking service status
**Current Behaviors:**
- Visit status pages during suspected issues
- Expect accurate, real-time status information
**Specific Pain Points:**
- Seeing "Up" status during planned maintenance creates confusion
- No advance notice of scheduled maintenance
**Goals:** Clear, accurate status information and advance maintenance notice

## Goals & Success Metrics

### Business Objectives
- Increase MW adoption from 10.7% to >20% of paying users within 6 months
- Reduce support tickets related to maintenance confusion by 40%
- Improve status page credibility and user trust metrics
- Decrease time-to-communicate maintenance from 15 minutes to <2 minutes

### User Success Metrics
- >40% of PSP owners use MW with linked announcements
- >10% of maintenance windows completed manually (vs auto-completed)
- >20% of maintenance windows using subscriber notifications
- Reduced user confusion during maintenance periods (measured via support tickets)

### Key Performance Indicators (KPIs)
- MW Creation Rate: Monthly MW created per account (target: 2x increase)
- Adoption Rate: % accounts using MW at least once per 30 days (target: >20%)
- Integration Usage: % MW created with linked announcements (target: >60%)
- User Satisfaction: Status page trust score improvement (target: +15%)

## MVP Scope

### Core Features (Must Have)
- **PSP Status Enhancement:** "Paused for Maintenance" status with distinct visual indicators on status pages and dashboard
- **MW-Announcement Integration:** Create announcements directly during MW creation/editing with auto-publish/unpublish
- **Basic Email Automation:** Auto-send email to PSP subscribers when MW starts (not advance scheduling)
- **Manual MW Completion:** "Mark as Done" functionality with immediate status restoration
- **MW Status Grouping:** Visual separation of active, scheduled, and completed maintenance windows
- **Editor Permissions:** Allow Editors to create/manage MW and announcements
- **Basic Timezone Selection:** User can choose timezone for MW creation

### Out of Scope for MVP
- Advance email scheduling ("X hours before MW starts")
- Recurring MW email automation and complex scheduling
- Cross-system timezone reconciliation (defer to future)
- Bulk announcement management for recurring MW
- Advanced email preference management
- PSP upcoming maintenance window lists

### MVP Success Criteria
Successfully deliver core maintenance communication workflow that eliminates the need for separate announcement creation while providing accurate status indicators during maintenance periods.

## Post-MVP Vision

### Phase 2 Features
- Advanced email scheduling with user-defined lead times
- Recurring MW announcement automation
- PSP upcoming maintenance window display
- Advanced timezone reconciliation across all systems

### Long-term Vision
Complete maintenance communication ecosystem with predictive scheduling, automated stakeholder workflows, and comprehensive maintenance analytics.

### Expansion Opportunities
- Integration with external incident management tools
- Maintenance window templates and best practices
- Advanced maintenance analytics and reporting

## Technical Considerations

### Platform Requirements
- **Target Platforms:** Web dashboard, Public Status Pages (PSP), Email system
- **Browser/OS Support:** Current UptimeRobot compatibility requirements
- **Performance Requirements:** No impact on existing monitoring performance

### Technology Preferences
- **Frontend:** Existing UptimeRobot web stack
- **Backend:** Current API and database infrastructure
- **Database:** Extend existing MW and announcement schemas
- **Email System:** Leverage existing PSP subscriber notification infrastructure

### Architecture Considerations
- **Repository Structure:** Integrate with existing UptimeRobot codebase
- **Service Architecture:** Extend current MW and announcement services
- **Integration Requirements:** Email system, PSP rendering, dashboard UI
- **Security/Compliance:** Maintain existing user permission and data protection standards

## Constraints & Assumptions

### Constraints
- **Budget:** 120 hours (1 person × 3 weeks)
- **Timeline:** Q4 2025 delivery target
- **Resources:** Development team familiar with existing MW/announcement systems
- **Technical:** Must integrate with existing UptimeRobot infrastructure without breaking changes

### Key Assumptions
- Existing email infrastructure can handle MW-triggered notifications
- PSP rendering system can accommodate new status types
- Current announcement system can be extended rather than rebuilt
- User timezone preferences are available in existing user management
- Editor permission system can be extended to cover MW functionality

## Risks & Open Questions

### Key Risks
- **Integration Complexity:** Existing MW and announcement systems may have undocumented dependencies that increase effort
- **Email System Limitations:** Current infrastructure may not support MW-triggered emails without significant modification
- **User Experience Confusion:** New status indicators might confuse existing users if not implemented carefully
- **Performance Impact:** Additional status checks during MW periods could affect PSP load times

### Open Questions
- How does existing email infrastructure handle automated triggers?
- Are there undocumented dependencies between MW and monitoring systems?
- What's the current announcement system architecture and extensibility?
- How do existing PSP status indicators work technically?

### Areas Needing Further Research
- Technical feasibility of MW-triggered email automation
- Existing codebase architecture for MW and announcement systems
- Current PSP rendering pipeline and status indicator implementation
- User permission system extension capabilities

## Next Steps

### Immediate Actions
1. **Technical Architecture Review:** Assess existing MW/announcement system integration points
2. **PM Handoff:** Create comprehensive PRD with validated scope and story breakdown
3. **Engineering Estimation:** Validate 70-hour estimate against actual system complexity
4. **User Research Validation:** Confirm Option C approach meets core user needs

### PM Handoff

This Project Brief provides the full context for MW 2.0 with validated scope alignment to 120-hour appetite. The analysis has identified email automation as the primary complexity driver and scoped the MVP to focus on core user value while deferring advanced scheduling features.

**Key Scope Decisions Made:**
- Focus on basic email automation (when MW starts) vs advance scheduling
- Prioritize PSP status accuracy over complex notification workflows  
- Defer recurring MW email automation to Phase 2
- Maintain 71% estimation buffer for technical unknowns

Please start in 'PRD Generation Mode', review this brief thoroughly, and work with the user to create the PRD section by section, ensuring story breakdown aligns with the validated 70-hour scope estimate.

---

*Analysis facilitated using the BMAD-METHOD™ framework with advanced elicitation techniques*
