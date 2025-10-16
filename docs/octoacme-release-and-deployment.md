# OctoAcme — Release & Deployment Guide

## Purpose
Standardize how OctoAcme releases features to production to reduce risk and improve observability.

## Release Types
- Patch: hotfixes addressing critical production issues
- Minor: incremental features and improvements
- Major: significant functionality or breaking changes

## Pre-release requirements
- All acceptance criteria met and PRs merged
- Code reviews completed using [Code Review Checklist](templates/code-review-checklist.md)
- Passing CI and security scans
- Release notes drafted
- Rollback / mitigation plan documented
- Smoke tests prepared and executed in staging
- Required approvals obtained (see checklist for approval levels)

## Deployment Checklist
*For detailed pre-deployment, deployment, and post-deployment procedures, see [Code Review Checklist](templates/code-review-checklist.md)*

### Quick Reference
- [ ] Deployment window scheduled (if needed)
- [ ] Backup or snapshot (if applicable)  
- [ ] Deploy to staging and run smoke tests
- [ ] All quality gates passed (see detailed checklist)
- [ ] Deploy to production (automated pipeline preferred)
- [ ] Run post-deploy verifications
- [ ] Monitor key metrics for 24 hours
- [ ] Announce release to stakeholders and support

## Rollback & Incident Playbook
- If a deployment fails or causes a critical issue:
  - Trigger incident response and notify on-call
  - Rollback to last known-good release if necessary
  - Triage root cause and capture action items

## Release Notes Template
- Release name / number:
- Date:
- Summary:
- Notable changes:
- Migration steps (if any):
- Known issues:
