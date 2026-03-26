# Angular 17+ Knowledge Quiz

**Duration:** 20 minutes
**Format:** Mix of multiple choice, true/false, and short answer
**Scoring:** 40 points total

---

## Section 1: Signals (10 points)

### Q1. Multiple Choice (2 points)
What is the key difference between `signal()` and `computed()`?

A) `signal()` is read-only, `computed()` is writable
B) `signal()` is writable, `computed()` is read-only and derives its value
C) They are identical, just different names
D) `computed()` doesn't trigger change detection

**Answer:** ___

---

### Q2. True/False (1 point)
Signals automatically trigger change detection in components using Default change detection strategy.

**Answer:** ___

---

### Q3. Multiple Choice (2 points)
When should you use `linkedSignal()` instead of `computed()`?

A) When you need a derived value that never changes
B) When you need a signal that resets based on specific dependencies
C) When you want better performance
D) `linkedSignal()` is deprecated in Angular 17+

**Answer:** ___

---

### Q4. Code Analysis (3 points)
What's wrong with this code?

```typescript
export class MyService {
  count = signal(0);
  double = signal(this.count() * 2); // Line A

  increment() {
    this.count.update(n => n + 1); // Line B
  }
}
```

**Issue:** _______________________________________________

**Fix:** _______________________________________________

---

### Q5. Short Answer (2 points)
What happens when you call `mySignal()` vs `mySignal.set(value)` vs `mySignal.update(fn)`?

**Answer:**
- `mySignal()`: _______________________________________________
- `mySignal.set(value)`: _______________________________________________
- `mySignal.update(fn)`: _______________________________________________

---

## Section 2: Memory Management (10 points)

### Q6. Multiple Choice (2 points)
Which operator should you use with `DestroyRef` to automatically unsubscribe from observables?

A) `takeUntil()`
B) `takeUntilDestroyed()`
C) `unsubscribeOn()`
D) `autoUnsubscribe()`

**Answer:** ___

---

### Q7. True/False (1 point each, 3 total)

A) Effects created with `effect()` are automatically cleaned up when the component is destroyed.

**Answer:** ___

B) If you add an event listener inside an `effect()`, you must return a cleanup function.

**Answer:** ___

C) Signals don't need cleanup because they don't create subscriptions.

**Answer:** ___

---

### Q8. Code Fix (3 points)
Fix the memory leak in this component:

```typescript
export class MyComponent {
  data$ = this.http.get('/api/data');

  constructor(private http: HttpClient) {
    this.data$.subscribe(data => console.log(data));
  }
}
```

**Fixed code:**
```typescript
// Write your fix here
```

---

### Q9. Short Answer (2 points)
Name THREE common sources of memory leaks in Angular applications.

**Answer:**
1. _______________________________________________
2. _______________________________________________
3. _______________________________________________

---

## Section 3: Modern Angular Patterns (10 points)

### Q10. Multiple Choice (2 points)
What's the recommended way to inject dependencies in Angular 17+?

A) Constructor injection: `constructor(private http: HttpClient)`
B) Property injection: `@Inject() http: HttpClient`
C) Function injection: `http = inject(HttpClient)`
D) Manual injection: `http = Injector.get(HttpClient)`

**Answer:** ___

---

### Q11. True/False (1 point each, 2 total)

A) Standalone components can import other standalone components directly without NgModules.

**Answer:** ___

B) You can mix standalone and module-based components in the same application.

**Answer:** ___

---

### Q12. Multiple Choice (2 points)
Which change detection strategy should you use with signal-based components?

A) Default - signals work best with default
B) OnPush - signals work perfectly with OnPush
C) Detached - to manually control when to check
D) None - signals don't need change detection

**Answer:** ___

---

### Q13. Code Completion (2 points)
Convert this template to use new control flow syntax:

**Before:**
```html
<div *ngIf="user; else loading">
  <h1>{{ user.name }}</h1>
  <ul>
    <li *ngFor="let item of user.items; trackBy: trackById">
      {{ item.name }}
    </li>
  </ul>
</div>
<ng-template #loading>Loading...</ng-template>
```

**After (write the new syntax):**
```html
<!-- Your answer here -->
```

---

### Q14. Short Answer (2 points)
What is the difference between `toSignal()` and `toObservable()`?

**Answer:** _______________________________________________

---

## Section 4: Performance & Best Practices (10 points)

### Q15. Multiple Choice (2 points)
What's the main problem with this template?

```typescript
@Component({
  template: `
    <div>Total: {{ calculateTotal() }}</div>
  `
})
export class MyComponent {
  items = signal([...]);

  calculateTotal() {
    let sum = 0;
    for (let i = 0; i < 10000; i++) {
      sum += this.items()[i % this.items().length].price;
    }
    return sum;
  }
}
```

A) Using signals in a method
B) Heavy computation runs on every change detection
C) The for loop is too large
D) Nothing wrong, this is optimal

**Answer:** ___

**How to fix:** _______________________________________________

---

### Q16. True/False (1 point each, 3 total)

A) OnPush components only check for changes when `@Input()` references change.

**Answer:** ___

B) Signal updates trigger change detection in OnPush components.

**Answer:** ___

C) Using `trackBy` in `*ngFor` or track in `@for` improves performance by avoiding unnecessary DOM re-renders.

**Answer:** ___

---

### Q17. Multiple Choice (2 points)
What's the best way to provide a service that should be singleton across the entire app?

A) `@Injectable()` with no providedIn
B) `@Injectable({ providedIn: 'root' })`
C) Add to `providers: []` in AppModule
D) Add to `providers: []` in every component

**Answer:** ___

---

### Q18. Ranking Question (3 points)
Rank these approaches from BEST to WORST for managing component state:

```
___ A) Using getter methods that compute values on every access
___ B) Using computed() signals for derived state
___ C) Using BehaviorSubject with async pipe
___ D) Using class properties that update manually
```

(1 = best, 4 = worst)

**Explanation (optional):** _______________________________________________

---

## Section 5: Practical Scenarios (BONUS - 5 points)

### Q19. Scenario Analysis (3 points)
You have a component that fetches user data on init and displays it. The data rarely changes, but when the component is destroyed and recreated, it fetches the data again (unnecessary API call).

**What pattern would you use to cache this data?**

A) Store in a service with `providedIn: 'root'` and only fetch if not cached
B) Use `localStorage` to persist data
C) Use `shareReplay()` operator on the observable
D) All of the above are valid, depends on requirements

**Answer:** ___

**Your preferred approach and why:**
_______________________________________________

---

### Q20. Debug Question (2 points)
A developer reports: "My computed signal isn't updating when I change the source signal."

```typescript
count = signal(0);
double = computed(() => this.count() * 2);

updateCount() {
  this.count() = 5; // They wrote this
}
```

**What's the issue and how to fix it?**

**Issue:** _______________________________________________

**Fix:** _______________________________________________

---

# Answer Key

<details>
<summary>Click to reveal answers</summary>

## Section 1: Signals (10 points)
- **Q1:** B (2 pts)
- **Q2:** True (1 pt)
- **Q3:** B (2 pts)
- **Q4:** Issue: `double` should be `computed()` not `signal()`. Fix: `double = computed(() => this.count() * 2)` (3 pts)
- **Q5:**
  - Read the value (1 pt)
  - Set new value (0.5 pt)
  - Update based on previous value (0.5 pt)

## Section 2: Memory Management (10 points)
- **Q6:** B (2 pts)
- **Q7:** A: True (1 pt), B: True (1 pt), C: True (1 pt)
- **Q8:** Use `DestroyRef` with `takeUntilDestroyed()` OR use `toSignal()` (3 pts)
- **Q9:** Any 3 of: Unsubscribed observables, event listeners, intervals/timeouts, HTTP requests, manual DOM refs (2 pts)

## Section 3: Modern Patterns (10 points)
- **Q10:** C (2 pts)
- **Q11:** A: True (1 pt), B: True (1 pt)
- **Q12:** B (2 pts)
- **Q13:** Must use `@if/@else` and `@for` with track (2 pts)
- **Q14:** `toSignal()` converts Observable→Signal, `toObservable()` converts Signal→Observable (2 pts)

## Section 4: Performance (10 points)
- **Q15:** B - Use computed() (2 pts)
- **Q16:** A: False (signals also trigger), B: True, C: True (3 pts)
- **Q17:** B (2 pts)
- **Q18:** B(1), C(2), D(3), A(4) (3 pts)

## Section 5: Bonus (5 points)
- **Q19:** D - context dependent (3 pts)
- **Q20:** Can't assign to signal with `=`, use `.set(5)` (2 pts)

</details>

---

# Scoring Guide

| Score | Level | Assessment |
|-------|-------|------------|
| 35-40 | **Senior** | Excellent understanding, ready for complex tasks |
| 28-34 | **Confirmed** | Solid knowledge, minor gaps acceptable |
| 20-27 | **Intermediate** | Needs mentoring on modern patterns |
| < 20 | **Junior** | Fundamental gaps, not confirmed level |

---

# Time Management

- **Sections 1-2 (20 points):** 8 minutes - Core signals & memory
- **Section 3 (10 points):** 5 minutes - Modern patterns
- **Section 4 (10 points):** 5 minutes - Performance
- **Section 5 (5 points):** 2 minutes - Bonus if time permits

---

# Interviewer Notes

## 🚩 Red Flags
- Scores < 5 points in Section 2 (Memory Management) - Critical for production
- Can't answer Q1, Q6, Q10 - These are fundamentals
- Doesn't know new control flow syntax (Q13)
- Thinks getters in templates are fine (Q15)

## ✅ Strong Signals
- Answers Q4, Q8 correctly without hesitation
- Explains Q18 reasoning clearly
- Mentions OnPush without prompting
- Uses proper terminology (computed, effect cleanup, etc.)

## 💡 Discussion Points
Use wrong answers to start conversations:
- "Tell me more about why you chose that answer"
- "Have you encountered this issue in production?"
- "How would you debug this scenario?"

