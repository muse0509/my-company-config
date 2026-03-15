# MVP Design & UX - Critical Fixes List

## Current MVP Assessment

### ✅ What's Working Well
- **Design System:** Tailwind v4 + custom colors + glassmorphism (high quality)
- **Component Library:** 52 components (Discover, Create, Profile complete)
- **Service Integration:** Jupiter, DFlow, DexScreener, GeckoTerminal
- **Mobile Support:** Safe Area handling, custom scrollbars implemented
- **Architecture:** React 19, TypeScript strict mode, modern stack

### 🔴 CRITICAL Issues (Fix This Month)
| # | Issue | Impact | Time | Assigned To |
|----|-------|--------|------|------------|
| **C1** | Prediction token duplicate display | UX confusion | 10min | Engineer A |
| **C2** | WCAG AA accessibility violations | Legal risk + UX | 4-6h | Engineer B |
| **C3** | Deposit flow error handling incomplete | User friction | 2-3h | Engineer A |
| **C4** | Missing virtualization (800+ tokens) | Performance degradation | 3-4h | Engineer A |
| **C5** | Light mode missing (dark only) | User experience | 6-8h | Designer + Eng B |

**Total CRITICAL:** 21 hours (3 days)

### 🟠 HIGH Priority (This Month)
1. Form validation strengthening (4h) - Engineer B
2. Error message standardization (2h) - Designer
3. Mobile navigation improvements (5h) - Engineer B
4. Loading state visual clarity (3h) - Designer
5. Color contrast ratio fixes for WCAG AA (5h) - Designer

**Total HIGH:** 19 hours (2.5 days)

### 🟡 MEDIUM Priority (Next Month)
1. Design token system completion (15h)
2. Storybook integration (12h)
3. Code splitting for performance (18h)
4. E2E test implementation (12h)
5. Analytics strengthening (5h)

**Total MEDIUM:** 62 hours (8 days)

---

## Recommended Action Plan

### Immediate (This Week)
```
Day 1: Engineer A tackles C1 (10min) + starts C3 (2-3h)
Day 2-3: Engineer B begins C2 (accessibility) in parallel
Day 3: Designer reviews light mode requirements for C5
```

### Week 2-4 (This Month)
```
Parallel tracks:
- Engineer A: C3 + C4 completion (5-7h remaining)
- Engineer B: C2 completion + HIGH priority items
- Designer: C5 + color contrast fixes

Sync: Daily 15-min standup, Wednesday design review
```

### Week 4+ (Ongoing)
```
- Monitor C1-C5 in production
- Address HIGH priority items as bandwidth allows
- Plan MEDIUM tier work for next month
```

---

## Success Criteria

After CRITICAL + HIGH completion (40 hours, 5.5 days work):

- ✅ **WCAG AA:** 0 violations (Lighthouse 90+)
- ✅ **Performance:** LCP <2.5s, FID <100ms, CLS <0.1
- ✅ **UX:** All user flows complete (discover → trade → portfolio)
- ✅ **Accessibility:** Screen reader friendly, keyboard navigation
- ✅ **Mobile:** Responsive at 320px-1920px
- ✅ **Light Mode:** Full feature parity with dark mode

---

## Resource Allocation

| Role | Availability | Assignment |
|------|--------------|-----------|
| **Engineer A** (Sonnet) | 50% | C1, C3, C4 + code review |
| **Engineer B** (Haiku) | 80% | C2 (accessibility), HIGH items |
| **Designer** (Haiku) | 60% | C5, color contrast, design review |

---

## Deliverables Timeline

- **Day 1:** C1 complete (token duplication fixed)
- **Day 3:** C2 begins (accessibility sprint)
- **Day 5:** C3 complete (error handling)
- **Day 7:** C4 complete (virtualization)
- **Day 10:** C5 + HIGH items in progress
- **Day 14:** All CRITICAL + HIGH complete, QA sign-off

---

**Status: READY FOR EXECUTION**

Next: Muse approves sprint plan, Engineer A starts immediately.
