# Problem

Maintenance window communication is frustratingly fragmented, requiring users to separately manage maintenance windows and announcements, leading to poor adoption and confused end-users during maintenance periods.

**Who Experiences This:**
- **Operations teams** managing infrastructure with public status pages (89.3% of paying users avoid MW feature entirely)
- **End-users** visiting status pages during maintenance (see misleading "Up" status during planned downtime)

**Current Pain Points:**
- Users must create announcements separately from maintenance windows, causing workflow friction
- Status pages show misleading "Up" status during planned maintenance, confusing subscribers
- No streamlined way to notify PSP subscribers about upcoming maintenance
- Manual announcement management discourages MW feature adoption

**Evidence:**
- #2 most requested feature on Nolt feedback platform
- Only 10.7% of paying users vs 7.8% of churned users use MW (slight retention correlation)
- User quote: "It would be nice not to have to create and manage a separate announcement for the maintenance window"
- 89.3% of paying users never tried MW feature due to perceived complexity

## Business point of view

Poorly communicated maintenance leads to confusion, support tickets, and lost trust for our customers to the degree that they avoid using our status pages. Current MW adoption is critically low (10.7%) despite being a core infrastructure management need, representing significant untapped value in user retention and platform credibility.

**Appetite:** 3 weeks, 1 person (120 hours maximum)

**Circuit Breakers:**
- Total scope >80 hours → Stop, re-evaluate approach
- Email integration >20 hours → Switch to manual approach  
- PSP integration requires refactoring → Implement badges only
- Any story >15 hours → Break down or defer

**No-Gos:**
- Advance email scheduling automation
- Complex recurring MW email management
- Comprehensive timezone reconciliation
- Bidirectional MW-announcement synchronization

---

# Solution

## Goals

- **Eliminate Communication Friction:** Integrate MW and announcement creation into single workflow
- **Provide Status Accuracy:** Clear "Paused for Maintenance" indicators during planned maintenance
- **Increase Adoption:** Target >20% of paying users using MW (from current 10.7%)
- **Reduce Support Burden:** 40% reduction in maintenance-related confusion tickets
- **Improve Communication Speed:** <2 minutes to communicate maintenance (from ~15 minutes)

## Details

### **Smart Announcement Integration**
- MW creation shows "☑️ Notify PSP subscribers (recommended)" checkbox when selected monitors have PSP subscribers
- Pre-fills announcement with MW timing and affected services
- User can customize title/description before completion
- No ongoing synchronization - announcement becomes independent after creation
- Leverages existing PSP subscriber email infrastructure

### **Maintenance Status Indicators**
- New "Paused for Maintenance" status distinct from "Up"/"Down"
- Appears on PSP status bars and dashboard monitor details during active MW
- Uses separate status tables to avoid modifying existing status logic
- Automatically activates when MW starts, deactivates when MW ends
- Maintains compatibility with all existing PSP themes

### **Manual MW Control**
- "Mark as Done" button for early maintenance completion
- Confirmation dialog prevents accidental termination
- Immediately restores normal monitoring and status indicators
- Audit logging for completion tracking (who, when, manual vs automatic)

### **Visual MW Organization**
- Group MW by status: Active | Scheduled | Completed
- Clear visual differentiation with status badges and styling
- Focus attention on current/upcoming maintenance
- Preserve existing MW search and filtering within groups

### **Editor Permissions & Timezone**
- Extend Editor role to create MW and announcements (previously Owner-only)
- Timezone selector during MW creation (defaults to account timezone)
- Consistent timezone display across all MW-related communications

## Out of scope

**Explicit No-Gos:**
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

---

# Analytics - Leading & Lagging Indicators

[L&L Indicators Guide & Example](https://www.notion.so/L-L-Indicators-Guide-Example-5e5df996d1254e31ac50f3b76123ca9e?pvs=21)

### Lagging indicator(s) - Why?

- **Increase in MW adoption rate:** % of paying users using MW at least once per 30 days (baseline: 10.7%)
- **Increase in MW creation frequency:** Average MW created per account per month
- **Reduction in maintenance-related support tickets:** % decrease in tickets related to maintenance confusion
- **Improvement in status page credibility:** User trust metrics and feedback sentiment during maintenance periods

### Hypothesis & evaluation - How?

**Hypothesis:** If maintenance windows are **properly communicated** (integrated announcements, subscriber notifications) and **status updates are accurate** (paused-for-maintenance indicators), then users will engage more actively with MW feature and adoption will increase significantly.

**Evaluation Approach:**
- **Pre-post comparison:** Compare 3 months before vs 3 months after release
- **Cohort analysis:** Track new MW users vs existing user behavior changes  
- **A/B testing consideration:** Potentially test smart checkbox vs always-show approaches
- **Qualitative feedback:** Monitor Nolt requests and support ticket themes

### Leading indicator(s) - What?

- **% of MW created with linked announcements:** Direct measure of workflow integration success
- **% of MW marked as done manually:** Indicates user engagement with completion control
- **% of MW using PSP subscriber notifications:** Measures communication feature adoption
- **Time-to-create MW with announcement:** Efficiency improvement tracking
- **Status indicator accuracy:** % of maintenance periods showing correct status vs "Up"

### Preliminary targets

- **>20%** of paying users use MW at least once per 30 days (baseline: 10.7%)
- **>60%** of MW created include linked announcements (baseline: ~0%)
- **>10%** of MW completed manually vs auto-completed (indicates active management)
- **>40%** reduction in maintenance-related support tickets
- **<2 minutes** average time to communicate maintenance (baseline: ~15 minutes)
