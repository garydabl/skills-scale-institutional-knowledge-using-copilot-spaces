# Code Review and Deployment Checklist

*Use this checklist to ensure consistent, thorough code reviews and safe deployment practices*

## Pre-Review Checklist (Author)

### Code Preparation
- [ ] **Self-review completed**: Reviewed your own code for obvious issues
- [ ] **PR size appropriate**: ≤400 lines of changes (excluding generated files)
- [ ] **Single responsibility**: PR addresses one feature/fix/improvement  
- [ ] **Clean commit history**: Commits are logical and well-described
- [ ] **Branch naming**: Follows team convention (feature/fix/docs/[description])

### Documentation and Context
- [ ] **PR description complete**: Links to issue, explains what and why
- [ ] **Acceptance criteria**: Clearly stated or linked from related issue
- [ ] **Breaking changes**: Documented with migration guide if applicable
- [ ] **Configuration changes**: Documented with deployment instructions
- [ ] **Screenshots/demos**: Included for UI changes

### Testing Requirements  
- [ ] **Unit tests**: New tests written for new functionality
- [ ] **Test coverage**: Maintained or improved (no significant decreases)
- [ ] **Integration tests**: Added/updated for API or system changes
- [ ] **Manual testing**: Completed for user-facing changes
- [ ] **Edge cases**: Considered and tested (null values, error conditions, etc.)

### Technical Standards
- [ ] **Code style**: Follows team linting and formatting rules
- [ ] **Security review**: No hardcoded secrets, proper input validation
- [ ] **Performance**: No obvious performance regressions
- [ ] **Error handling**: Appropriate error messages and logging
- [ ] **Dependencies**: New dependencies justified and secure

## Code Review Checklist (Reviewer)

### Initial Review
- [ ] **PR context understood**: Read description and linked issues
- [ ] **Scope appropriate**: Change size and complexity are reasonable
- [ ] **Approach alignment**: Technical approach makes sense for the problem

### Functionality Review
- [ ] **Requirements met**: Code implements stated acceptance criteria
- [ ] **Logic correctness**: Algorithms and business logic are sound
- [ ] **Error handling**: Edge cases and error conditions properly handled
- [ ] **Data validation**: User inputs properly validated and sanitized
- [ ] **Security considerations**: No security vulnerabilities introduced

### Code Quality Assessment
- [ ] **Readability**: Code is clear, well-organized, and self-documenting
- [ ] **Maintainability**: Code follows established patterns and conventions
- [ ] **Performance**: No unnecessary complexity or performance issues
- [ ] **Reusability**: Common functionality properly abstracted
- [ ] **Documentation**: Complex logic is commented appropriately

### Testing Evaluation
- [ ] **Test coverage**: Tests cover main functionality and edge cases
- [ ] **Test quality**: Tests are clear, reliable, and maintainable
- [ ] **Test data**: Test data is realistic and doesn't expose sensitive information
- [ ] **Manual testing**: Reviewer has tested changes locally (for significant features)

### Integration and Dependencies
- [ ] **API compatibility**: Changes don't break existing integrations
- [ ] **Database changes**: Migrations are safe and backwards-compatible
- [ ] **Configuration**: New config values have sensible defaults
- [ ] **Dependencies**: New dependencies are necessary and up-to-date

## Approval Requirements

### Standard Approval (Required)
- [ ] **At least one approval** from team member
- [ ] **All CI checks passing** (tests, linting, security scans)
- [ ] **No unresolved review comments**
- [ ] **Branch up to date** with main/master branch

### Enhanced Approval (For significant changes)
*Required for: Database migrations, API changes, security-related changes, architecture changes*
- [ ] **Two approvals** including one from senior team member
- [ ] **Architecture review** (if applicable)
- [ ] **Security review** (if applicable)  
- [ ] **Performance testing** completed (if applicable)
- [ ] **Stakeholder sign-off** (for user-facing changes)

### Emergency/Hotfix Approval
*For critical production issues only*
- [ ] **One senior developer approval**
- [ ] **Incident ticket** linked and justified
- [ ] **Rollback plan** documented
- [ ] **Post-deployment verification** plan ready

## Pre-Deployment Checklist

### Environment Preparation
- [ ] **Staging deployment**: Successfully deployed and tested in staging
- [ ] **Database migrations**: Executed and verified in staging
- [ ] **Configuration**: Environment-specific configs reviewed and updated
- [ ] **Dependencies**: All required services and dependencies available
- [ ] **Monitoring**: Alerts and dashboards ready for new code

### Release Planning
- [ ] **Deployment window**: Scheduled during appropriate maintenance window
- [ ] **Communication**: Stakeholders notified of deployment timing
- [ ] **Rollback plan**: Clear steps defined and tested
- [ ] **Smoke tests**: Post-deployment verification tests prepared
- [ ] **On-call coverage**: Team member available during and after deployment

### Documentation and Communication  
- [ ] **Release notes**: Prepared and reviewed
- [ ] **Migration instructions**: Documented for users (if needed)
- [ ] **Support team**: Briefed on changes and potential issues
- [ ] **Monitoring playbook**: Updated with new alerts or metrics

## Post-Deployment Verification

### Immediate Checks (0-30 minutes)
- [ ] **Deployment success**: Application started without errors
- [ ] **Smoke tests**: Critical user paths functioning
- [ ] **Database health**: Migrations completed successfully
- [ ] **API endpoints**: Key endpoints responding correctly
- [ ] **Error rates**: No significant increase in error rates

### Extended Monitoring (1-24 hours)
- [ ] **Performance metrics**: Response times within acceptable ranges
- [ ] **Usage patterns**: Traffic and user behavior as expected
- [ ] **Error monitoring**: No new error patterns or critical issues
- [ ] **Business metrics**: Key business indicators tracking normally
- [ ] **User feedback**: No critical user-reported issues

### Follow-up Actions
- [ ] **Deployment retrospective**: If issues occurred, document lessons learned
- [ ] **Monitoring tuning**: Adjust alerts based on actual behavior
- [ ] **Documentation updates**: Update runbooks or troubleshooting guides
- [ ] **Team communication**: Share deployment outcome with stakeholders

## Rollback Procedures

### Rollback Triggers
- **Critical functionality broken**: Core user flows not working
- **Significant performance degradation**: >50% increase in response times  
- **Security vulnerability**: Newly introduced security issue
- **Data corruption risk**: Risk of data loss or corruption
- **High error rates**: >5% increase in 5xx errors

### Rollback Process
1. **Immediate response** (0-15 minutes)
   - [ ] Assess severity and impact
   - [ ] Notify incident response team
   - [ ] Begin rollback procedure
   
2. **Execute rollback** (15-30 minutes)
   - [ ] Revert application deployment
   - [ ] Revert database migrations (if safe)
   - [ ] Restore previous configuration
   - [ ] Verify systems stability
   
3. **Post-rollback** (30+ minutes)
   - [ ] Confirm issue resolution
   - [ ] Document incident details
   - [ ] Plan fix strategy
   - [ ] Communicate resolution

## Quality Gates Summary

### Cannot Merge Until:
- [ ] All automated tests pass
- [ ] Security scans pass
- [ ] Code review approval(s) obtained
- [ ] All review comments resolved
- [ ] Branch is up-to-date with target

### Cannot Deploy Until:
- [ ] Staging deployment successful
- [ ] Smoke tests pass
- [ ] Rollback plan documented
- [ ] Stakeholder notification sent
- [ ] On-call coverage confirmed

### Must Monitor After:
- [ ] Error rates and performance
- [ ] User experience metrics
- [ ] Business impact measures
- [ ] System health indicators

---

## Usage Guidelines

### For Code Authors
- Complete the pre-review checklist before requesting review
- Respond to review feedback promptly and thoughtfully
- Don't take feedback personally - it's about the code, not you
- Ask questions if review feedback is unclear

### For Code Reviewers  
- Review within 24 hours of request (or communicate delays)
- Provide specific, actionable feedback
- Explain the "why" behind suggestions
- Acknowledge good practices and improvements
- Focus on code quality, not personal preferences

### For Deployment Managers
- Use appropriate approval level based on change risk
- Verify all quality gates before proceeding
- Have rollback plan ready before deployment
- Monitor actively after deployment

*This checklist is designed to catch issues early, ensure consistent quality, and enable safe, reliable deployments.*