# OctoAcme — Execution & Tracking

## Purpose
Guidance for managing day-to-day execution and tracking progress toward project milestones.

## Team Rhythm
- Daily standups (15 min) — focus on progress, blockers, dependencies
- Weekly delivery sync — show progress, updates, and flagged risks
- Demo/Review at the end of each sprint or milestone

## Workflows

### Task Assignment Process
1. **Backlog Grooming**: PM and PdM review and prioritize backlog items weekly
2. **Sprint Planning**: Team selects items from "Ready" column based on:
   - Clear acceptance criteria defined
   - Dependencies resolved or identified
   - Estimated effort fits team capacity
   - Required approvals obtained
3. **Assignment Guidelines**:
   - Developers self-assign tasks from "Ready" column during standups
   - Each person should have max 2 "In Progress" items simultaneously  
   - Complex tasks should be paired or have a designated reviewer identified upfront
   - Blocked items moved back to "Ready" with clear unblocking owner/timeline

### Project Board Management
- Use the project board (e.g., GitHub Projects) with columns: Backlog, Ready, In Progress, In Review, QA, Done
- **Backlog**: Prioritized items awaiting refinement
- **Ready**: Items with clear acceptance criteria, ready to start
- **In Progress**: Active development (max 2 per person)
- **In Review**: Code review and approval phase
- **QA**: Testing and validation phase  
- **Done**: Completed and deployed/merged

### Pull Request workflow:
- Small PRs (<= 400 lines when possible)
- Include issue link and acceptance criteria in PR description
- Run automated tests and linting in CI before requesting review
- Require at least one approval before merging (or team-defined policy)
- Use [Code Review Checklist](templates/code-review-checklist.md) for thorough reviews

## Quality & Testing
- Unit tests for new logic
- Integration tests where applicable
- End-to-end smoke tests for critical flows before release
- Security scanning in CI
- Manual QA for feature acceptance when needed

## Reporting & Metrics
- Track velocity and burndown
- Monitor success metrics identified in the Project One-pager
- Use dashboards for key signals (errors, latency, usage)

## Blocker Escalation
- Level 1: Team-level triage in daily standup
- Level 2: PM escalates to Product Lead and dependent teams
- Level 3: Sponsor-level escalation for business-impacting issues

## Execution Checklist
- [ ] Branching and PR conventions documented in repo
- [ ] CI configured for tests and lint
- [ ] Regular demos scheduled
- [ ] Risk register updated weekly
