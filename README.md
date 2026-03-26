# Angular 17+ Interview Exercises

**Total Duration: 30 minutes**

## Overview
These exercises test a confirmed Angular developer's knowledge of:
- ✅ **Signals** (signal, computed, linkedSignal, toSignal)
- ✅ **Memory leak prevention** (DestroyRef, takeUntilDestroyed, effect cleanup)
- ✅ **Modern patterns** (standalone components, inject(), OnPush)
- ✅ **New control flow** (@if, @for with track)
- ✅ **Production-ready code** (type safety, clean architecture)

## Exercise Structure

### Exercise 1: Signal-Based Counter (10 min) ⭐
**File:** `exercices.ts` - CounterService

Create a service with:
- `signal()` for state
- `computed()` for derived values
- `linkedSignal()` for conditional reset logic
- Tree-shakeable with `providedIn: 'root'`

**Tests:** `exercise-01-counter.spec.ts`

### Exercise 2: Memory Leaks + Component (15 min) ⭐⭐
**File:** `exercices.ts` - FixedComponent + UserListComponent

Part A: Fix 3 memory leaks
- Unsubscribed interval
- Effect without cleanup
- HTTP request not cancelled

Part B: Create modern component
- Standalone + OnPush
- Use `inject()` not constructor DI
- Use `toSignal()` for HTTP
- Use `@if/@for` syntax
- Track by id

**Tests:** `exercise-02-memory-component.spec.ts`

### Exercise 3: Performance Optimization (5 min - BONUS) ⭐
**File:** `exercices.ts` - OptimizedItemListComponent

Optimize slow component:
- Add OnPush change detection
- Convert to signals + computed
- Remove getter from template
- Proper track function

**Tests:** `exercise-03-performance.spec.ts`

## Running Tests

```bash
# Run all interview tests
npm run test Interview/

# Run specific exercise
npm run test Interview/exercise-01

# Watch mode
npm run test Interview/ -- --watch
```

## Evaluation Criteria

### ✅ Must Have (Pass)
- [ ] All memory leaks fixed correctly
- [ ] Proper signal usage (not just converted syntax)
- [ ] Modern DI with `inject()`
- [ ] OnPush change detection where required
- [ ] New control flow syntax (`@if`, `@for`)
- [ ] Type safety (no `any`)

### ⭐ Nice to Have (Strong Pass)
- [ ] linkedSignal used correctly
- [ ] Effect cleanup implemented properly
- [ ] Computed signals used efficiently
- [ ] Track function optimized
- [ ] Clean, production-ready code

### 🚫 Red Flags (Fail)
- ❌ Memory leaks remain
- ❌ Using old patterns (*ngIf, *ngFor, constructor DI)
- ❌ No OnPush where specified
- ❌ Type safety violations
- ❌ Doesn't understand signals vs observables

## Time Management

| Time | Exercise | Focus |
|------|----------|-------|
| 0-10 min | Exercise 1 | Signals fundamentals |
| 10-25 min | Exercise 2 | Memory + full component |
| 25-30 min | Exercise 3 | Performance (if time) |

## What This Tests

### Signal Mastery
- When to use `signal()` vs `computed()` vs `linkedSignal()`
- Understanding signal dependencies
- Effect cleanup patterns

### Memory Management
- Using `DestroyRef` with `takeUntilDestroyed()`
- Effect cleanup functions
- When to migrate observables to signals

### Modern Angular
- Standalone components
- `inject()` function over constructor
- OnPush optimization
- New control flow syntax

### Production Readiness
- Type safety
- Clean architecture
- No anti-patterns
- Testable code

## Sample Solutions

Sample solutions are tested in the spec files. Candidates should aim for similar patterns.

## Notes for Interviewers

- **10 min mark**: Candidate should be finishing Exercise 1
- **25 min mark**: Candidate should be finishing Exercise 2
- **Bonus**: Exercise 3 is optional, tests performance awareness

### Good Signs ✅
- Asks about linkedSignal behavior
- Mentions effect cleanup without prompting
- Suggests OnPush without being told
- Types everything properly

### Warning Signs ⚠️
- Confused about signal vs observable
- Forgets DestroyRef
- Uses old patterns by default
- Skips type annotations

### Deal Breakers 🚫
- Can't fix memory leaks
- Doesn't know new control flow
- Uses `any` everywhere
- Can't explain their code
