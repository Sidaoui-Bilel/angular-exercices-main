# Complete Angular 17+ Interview Guide

**Total Duration:** 50 minutes
**Target Level:** Confirmed/Senior Angular Developer

---

## Interview Structure

| Time | Activity | File | Points |
|------|----------|------|--------|
| 0-30 min | **Practical Exercises** | `exercices.ts` | Pass/Fail |
| 30-50 min | **Knowledge Quiz** | `quiz-questions.md` | 40 points |

---

## Part 1: Practical Exercises (30 minutes)

### Setup (2 minutes)
1. Share screen with candidate
2. Open `Interview/exercices.ts`
3. Explain: "Complete exercises 1 & 2, exercise 3 is bonus"
4. Show how to run tests: `npm run test Interview/`

### Exercise 1: Counter Service (10 min)
**What to observe:**
- ✅ Uses `signal()`, `computed()`, `linkedSignal()` correctly
- ✅ Understands when to use each type
- ✅ Implements `providedIn: 'root'`
- ❌ Confuses signal types
- ❌ Uses observables instead of signals

**Intervention Points:**
- **5 min:** If stuck on linkedSignal, give hint: "Think about conditional reset"
- **8 min:** If still on basic setup, they may be struggling with fundamentals
- **10 min:** Move to Exercise 2 regardless of completion

### Exercise 2: Memory Leaks + Component (15 min)
**What to observe:**

**Part A (5 min):**
- ✅ Injects `DestroyRef`
- ✅ Uses `takeUntilDestroyed()`
- ✅ Returns cleanup from effect
- ❌ Manual subscription management
- ❌ Forgets effect cleanup

**Part B (10 min):**
- ✅ Standalone + OnPush
- ✅ Uses `inject(HttpClient)`
- ✅ Uses `toSignal()` for HTTP
- ✅ Uses `@if/@for` syntax
- ❌ Constructor injection
- ❌ Old control flow syntax

**Intervention Points:**
- **15 min:** If Part A incomplete, discuss approach before moving to Part B
- **20 min:** Give hint about `toSignal()` if struggling
- **25 min:** Move to Exercise 3 or wrap up

### Exercise 3: Performance (5 min - BONUS)
**What to observe:**
- ✅ Adds OnPush immediately
- ✅ Converts to signals + computed
- ✅ Removes getter
- ❌ Doesn't see the performance issue

**Time Check:**
- **30 min:** Stop practical exercises, begin quiz

---

## Part 2: Knowledge Quiz (20 minutes)

### Administration
1. Give candidate `quiz-answers-sheet.md`
2. Share or show `quiz-questions.md` on screen
3. Set timer for 20 minutes
4. Tell them: "Some questions are harder than others, skip and come back if needed"

### Sections
- **Section 1:** Signals fundamentals (10 pts) - Should score 7+
- **Section 2:** Memory management (10 pts) - Should score 7+
- **Section 3:** Modern patterns (10 pts) - Should score 6+
- **Section 4:** Performance (10 pts) - Should score 6+
- **Section 5:** Bonus scenarios (5 pts) - Optional

### Observation Points

**During Quiz:**
- How quickly they answer basic questions (Q1, Q6, Q10)
- Whether they ask clarifying questions (good sign)
- If they skip hard questions strategically (good)
- If they struggle with fundamentals (red flag)

**After Quiz:**
- Review answers together
- Ask "Can you explain your reasoning for Q18?"
- Discuss any wrong answers: "What made you choose that?"

---

## Combined Scoring & Decision Matrix

### Practical Exercises (Pass/Fail per exercise)

| Exercise | Pass Criteria | Result |
|----------|--------------|--------|
| Exercise 1 | All tests pass, proper signal usage | ☐ Pass ☐ Fail |
| Exercise 2A | All leaks fixed, uses DestroyRef | ☐ Pass ☐ Fail |
| Exercise 2B | Component works, modern patterns | ☐ Pass ☐ Fail |
| Exercise 3 | OnPush + signals (bonus) | ☐ Pass ☐ Fail |

### Quiz Score: ___ / 40

---

## Final Assessment

### Hiring Matrix

| Practical | Quiz Score | Assessment | Recommendation |
|-----------|------------|------------|----------------|
| 3/3 Pass | 35-40 | **Senior** | ✅ Strong Yes |
| 3/3 Pass | 28-34 | **Confirmed** | ✅ Yes |
| 2/3 Pass | 28-34 | **Confirmed** | ⚠️ Yes (with conditions) |
| 2/3 Pass | 20-27 | **Intermediate** | ⚠️ Maybe (needs mentoring) |
| < 2 Pass | < 28 | **Below Target** | ❌ No |

### Critical Red Flags (Automatic No)
- ❌ Can't fix memory leaks in Exercise 2A
- ❌ Doesn't know `inject()` function (Q10)
- ❌ Scores < 5 in Memory section
- ❌ Uses `any` type everywhere
- ❌ Can't explain their own code

### Strong Positive Signals
- ✅ Completes Exercise 3 successfully
- ✅ Scores 35+ on quiz
- ✅ Asks insightful questions
- ✅ Explains reasoning clearly
- ✅ Mentions performance without prompting

---

## Interview Notes Template

**Candidate:** _______________________
**Date:** _______________________
**Interviewer:** _______________________

### Practical Performance

**Exercise 1 (10 min):**
- Completion time: ___
- Approach: _______________________________________________
- Issues: _______________________________________________

**Exercise 2 (15 min):**
- Part A completion: _______________________________________________
- Part B completion: _______________________________________________
- Code quality: _______________________________________________

**Exercise 3 (5 min - bonus):**
- Attempted: ☐ Yes ☐ No
- Result: _______________________________________________

### Quiz Results

**Total Score:** ___ / 40

**Section Breakdown:**
- Signals: ___ / 10
- Memory: ___ / 10
- Modern Patterns: ___ / 10
- Performance: ___ / 10
- Bonus: ___ / 5

### Technical Discussion

**Questions Asked:**
1. _______________________________________________
2. _______________________________________________

**Red Flags Observed:**
- _______________________________________________
- _______________________________________________

**Impressive Moments:**
- _______________________________________________
- _______________________________________________

### Overall Assessment

**Strengths:**
1. _______________________________________________
2. _______________________________________________
3. _______________________________________________

**Weaknesses:**
1. _______________________________________________
2. _______________________________________________
3. _______________________________________________

**Level:** [ ] Senior [ ] Confirmed [ ] Intermediate [ ] Junior

**Recommendation:** [ ] Strong Yes [ ] Yes [ ] Maybe [ ] No

**Confidence Level:** [ ] High [ ] Medium [ ] Low

**Additional Notes:**
_______________________________________________
_______________________________________________
_______________________________________________

---

## Follow-Up Questions (If time permits)

If interview finishes early or you want deeper insight:

1. **Architecture:** "How would you structure a large Angular application with 50+ components?"

2. **State Management:** "When would you use a state management library (NgRx, Signals store) vs plain signals?"

3. **Testing:** "How do you approach testing signal-based components?"

4. **Migration:** "You have an Angular 14 app with tons of RxJS. How do you approach migrating to signals?"

5. **Real Scenario:** "User reports 'the page is slow'. How do you debug and fix it?"

---

## Post-Interview Checklist

- [ ] Scored all exercises
- [ ] Scored quiz
- [ ] Completed assessment matrix
- [ ] Documented red flags and strengths
- [ ] Made hiring recommendation
- [ ] Saved notes for team discussion
- [ ] Sent thank you email to candidate

---

## Calibration Notes for Interviewers

### First Time Using This Interview?

**Expected results for a true "Confirmed" developer:**
- Completes Exercises 1 & 2 with 5-10 minutes to spare
- Exercise 1: 7-8 minutes
- Exercise 2: 12-15 minutes
- Quiz: 26-32 points
- Minimal hints needed

**If candidates consistently score low:**
- Review if instructions are clear
- Check if test environment is set up correctly
- Consider if "Confirmed" bar is set correctly for your team

**If candidates consistently score high:**
- Add more advanced scenarios
- Use Exercise 3 as required, not bonus
- Consider deeper architectural questions

---

## Quick Reference: Pass/Fail Indicators

### ✅ Clear Pass Signals
- Finishes all exercises with time to spare
- Quiz score 28+
- Uses modern patterns without prompting
- Code is clean and type-safe
- Explains reasoning clearly

### ⚠️ Borderline Signals
- Completes 2/3 exercises
- Quiz score 20-27
- Needs hints but applies them correctly
- Some old patterns but corrects when pointed out
- Understands concepts but slow to implement

### ❌ Clear Fail Signals
- Can't fix memory leaks
- Quiz score < 20
- Doesn't know basic Angular 17+ features
- Uses `any` everywhere
- Can't explain their own code
- Resistant to modern patterns

---

**Version:** 1.0
**Last Updated:** 2026-03-26
**Maintained By:** Engineering Team
