# Angular Interview Quiz - Beginner to Expert

**Duration:** 20-25 minutes
**Format:** Mix of multiple choice, true/false, and short answer
**Scoring:** 50 points total
**Progression:** Fundamentals → Advanced → Latest Features

---

## Section 1: Fundamentals (10 points) ⏱️ 5 minutes

### Q1. Multiple Choice (1 point)
What is Angular?

- A) A JavaScript library for building user interfaces
- B) A TypeScript-based framework for building web applications
- C) A CSS framework like Bootstrap
- D) A backend framework

**Answer:** ___

---

### Q2. Multiple Choice (2 points)
Which decorator is used to define an Angular component?

- A) `@NgModule`
- B) `@Injectable`
- C) `@Component`
- D) `@Directive`

**Answer:** ___

---

### Q3. True/False (1 point each, 3 total)

A) Angular uses two-way data binding with `[(ngModel)]`.

**Answer:** ___

B) Template expressions in `{{ }}` can contain any JavaScript code including if/else statements.

**Answer:** ___

C) Each component must have a template (inline or external).

**Answer:** ___

---

### Q4. Multiple Choice (2 points)
What are the core building blocks of an Angular application?

- A) Components, Services, Modules
- B) HTML, CSS, JavaScript
- C) Controllers, Views, Models
- D) Reducers, Actions, Store

**Answer:** ___

---

### Q5. Short Answer (2 points)
Name the THREE main ways to pass data in Angular templates.

**Answer:**
1. _______________________________________________
2. _______________________________________________
3. _______________________________________________

---

## Section 2: Intermediate Concepts (12 points) ⏱️ 7 minutes

### Q6. Multiple Choice (2 points)
What is the purpose of the `ngOnInit` lifecycle hook?

- A) Called when a component is destroyed
- B) Called once after the first `ngOnChanges` and after component initialization
- C) Called every time an input property changes
- D) Called before the component is created

**Answer:** ___

---

### Q7. Multiple Choice (2 points)
How do you make a service available across the entire application?

- A) Import it in every component
- B) `@Injectable({ providedIn: 'root' })`
- C) Add to the imports array
- D) Use `@NgModule` decorator on the service

**Answer:** ___

---

### Q8. Code Analysis (3 points)
What's wrong with this component?

```typescript
@Component({
  selector: 'app-user',
  template: '<h1>{{ user.name }}</h1>'
})
export class UserComponent {
  @Input() user: User;
}
```

**Issue:** _______________________________________________

**Fix:** _______________________________________________

---

### Q9. Multiple Choice (2 points)
Which RxJS operator would you use to transform data from an Observable?

- A) `filter()`
- B) `map()`
- C) `subscribe()`
- D) `catchError()`

**Answer:** ___

---

### Q10. True/False (1 point each, 3 total)

A) Services in Angular are singleton by default when provided in root.

**Answer:** ___

B) `*ngFor` can be used without a trackBy function, but it's better to use one.

**Answer:** ___

C) Child routes in Angular require their own `<router-outlet>`.

**Answer:** ___

---

## Section 3: Advanced Patterns (12 points) ⏱️ 6 minutes

### Q11. Multiple Choice (2 points)
What's the recommended way to inject dependencies in Angular 16+?

- A) Constructor injection: `constructor(private http: HttpClient)`
- B) Property injection: `@Inject() http: HttpClient`
- C) Function injection: `http = inject(HttpClient)`
- D) Manual injection: `http = Injector.get(HttpClient)`

**Answer:** ___

---

### Q12. Multiple Choice (2 points)
Which change detection strategy should you use for better performance?

- A) Default
- B) OnPush
- C) Detached
- D) CheckAlways

**Answer:** ___

**Why?** _______________________________________________

---

### Q13. Code Fix (3 points)
Fix the memory leak in this component:

```typescript
export class MyComponent implements OnInit {
  ngOnInit() {
    interval(1000).subscribe(count => {
      console.log('Count:', count);
    });
  }
}
```

**Fixed code:**
```typescript
// Write your fix here
```

---

### Q14. Multiple Choice (2 points)
What is the purpose of standalone components (Angular 14+)?

- A) Better performance than regular components
- B) Eliminates the need for NgModules
- C) Allows components to run independently in Web Workers
- D) Provides better type safety

**Answer:** ___

---

### Q15. True/False (1 point each, 3 total)

A) OnPush components only check for changes when `@Input()` references change or events occur.

**Answer:** ___

B) Using `async` pipe automatically handles subscription and unsubscription.

**Answer:** ___

C) Guards can be implemented as classes or functions in modern Angular.

**Answer:** ___

---

## Section 4: Signals & Modern Features (10 points) ⏱️ 5 minutes

### Q16. Multiple Choice (2 points)
What is the key difference between `signal()` and `computed()` in Angular 17+?

- A) `signal()` is read-only, `computed()` is writable
- B) `signal()` is writable, `computed()` is read-only and derives its value
- C) They are identical, just different names
- D) `computed()` doesn't trigger change detection

**Answer:** ___

---

### Q17. Code Analysis (3 points)
What's wrong with this code?

```typescript
export class MyService {
  count = signal(0);
  double = signal(this.count() * 2);

  increment() {
    this.count.update(n => n + 1);
  }
}
```

**Issue:** _______________________________________________

**Fix:** _______________________________________________

---

### Q18. Short Answer (2 points)
What are the THREE signal methods and their purposes?

**Answer:**
- `mySignal()`: _______________________________________________
- `mySignal.set(value)`: _______________________________________________
- `mySignal.update(fn)`: _______________________________________________

---

### Q19. True/False (1 point each, 3 total)

A) Signals automatically work with OnPush change detection.

**Answer:** ___

B) `computed()` signals are memoized and only recompute when dependencies change.

**Answer:** ___

C) `effect()` should be used for updating other signals.

**Answer:** ___

---

## Section 5: Expert Level - Latest Features & Performance (16 points) ⏱️ 7 minutes

### Q20. Code Completion (3 points)
Convert this template to use the NEW control flow syntax (Angular 17+):

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

**After:**
```html
<!-- Your answer here -->
```

---

### Q21. Multiple Choice (2 points)
Which operator should you use with `DestroyRef` to automatically unsubscribe from observables?

- A) `takeUntil()`
- B) `takeUntilDestroyed()`
- C) `unsubscribeOn()`
- D) `autoUnsubscribe()`

**Answer:** ___

---

### Q22. Multiple Choice (2 points)
What's the main problem with this template?

```typescript
@Component({
  template: `<div>Total: {{ calculateTotal() }}</div>`
})
export class MyComponent {
  items = signal([{price: 10}, {price: 20}]);

  calculateTotal() {
    let sum = 0;
    for (let i = 0; i < 10000; i++) {
      sum += this.items()[i % this.items().length].price;
    }
    return sum;
  }
}
```

- A) Using signals in a method
- B) Heavy computation runs on every change detection cycle
- C) The for loop is too large
- D) Nothing wrong, this is optimal

**Answer:** ___

**How to fix:** _______________________________________________

---

### Q23. Multiple Choice (2 points)
What is the difference between `toSignal()` and `toObservable()`?

- A) `toSignal()` converts Signal to Observable, `toObservable()` converts Observable to Signal
- B) `toSignal()` converts Observable to Signal, `toObservable()` converts Signal to Observable
- C) They do the same thing, just different names
- D) Both convert Promises to Signals

**Answer:** ___

---

### Q24. True/False (1 point each, 3 total)

A) Effects created with `effect()` are automatically cleaned up when the component is destroyed.

**Answer:** ___

B) `resource()` and `httpResource()` in Angular 19+ provide signal-based data fetching with automatic cleanup.

**Answer:** ___

C) Using `trackBy` in `@for` improves performance by avoiding unnecessary DOM re-renders.

**Answer:** ___

---

### Q25. Advanced Scenario (4 points)
You're building a real-time dashboard that:
- Fetches data from an API every 5 seconds
- Displays computed statistics from that data
- Must avoid memory leaks
- Should use modern Angular patterns

**Write the component skeleton using signals and proper cleanup:**

```typescript
// Your answer here
```

---

# Answer Key

<details>
<summary>Click to reveal answers</summary>

## Section 1: Fundamentals (10 points)
- **Q1:** B (1 pt)
- **Q2:** C (2 pts)
- **Q3:** A: True, B: False (template expressions can't contain statements), C: True (3 pts)
- **Q4:** A (2 pts)
- **Q5:** Interpolation `{{ }}`, Property binding `[property]`, Event binding `(event)` (2 pts)

## Section 2: Intermediate (12 points)
- **Q6:** B (2 pts)
- **Q7:** B (2 pts)
- **Q8:** Issue: `user` might be undefined. Fix: Add `!` or `?` or initialize: `@Input() user?: User` or `@Input() user!: User` (3 pts)
- **Q9:** B (2 pts)
- **Q10:** A: True, B: True, C: True (3 pts)

## Section 3: Advanced (12 points)
- **Q11:** C (2 pts)
- **Q12:** B - OnPush only checks when inputs change, events occur, or signals/observables update (2 pts)
- **Q13:** Use `takeUntilDestroyed()` with `inject(DestroyRef)` to cancel interval on component destroy. Must import from `@angular/core/rxjs-interop` (3 pts)
- **Q14:** B (2 pts)
- **Q15:** A: True, B: True, C: True (3 pts)

## Section 4: Signals (10 points)
- **Q16:** B (2 pts)
- **Q17:** Issue: `double` should use `computed()` not `signal()`. Fix: `double = computed(() => this.count() * 2)` (3 pts)
- **Q18:** Read value / Set new value / Update based on previous value (2 pts)
- **Q19:** A: True, B: True, C: False (effects are for side effects, not updating signals) (3 pts)

## Section 5: Expert (16 points)
- **Q20:** Use `@if/else` and `@for` with track (3 pts)
- **Q21:** B (2 pts)
- **Q22:** B - Use `computed()` to memoize (2 pts)
- **Q23:** B (2 pts)
- **Q24:** A: True, B: True, C: True (3 pts)
- **Q25:** Must include: signal state, computed values, effect for interval, DestroyRef cleanup (4 pts)

</details>

---

# Scoring Guide

| Score | Level | Assessment |
|-------|-------|------------|
| 45-50 | **Senior/Expert** | Excellent understanding, ready for complex architecture & latest features |
| 35-44 | **Mid-Senior** | Strong knowledge, comfortable with modern Angular patterns |
| 25-34 | **Intermediate** | Good fundamentals, needs practice with advanced concepts |
| 15-24 | **Junior+** | Solid basics, requires mentoring on advanced topics |
| < 15 | **Junior** | Fundamental gaps, needs training on core concepts |

---

# Time Management

- **Section 1 (10 points):** 5 minutes - Fundamentals
- **Section 2 (12 points):** 7 minutes - Intermediate concepts
- **Section 3 (12 points):** 6 minutes - Advanced patterns
- **Section 4 (10 points):** 5 minutes - Signals & modern features
- **Section 5 (16 points):** 7 minutes - Expert level & latest features

**Total:** 20-25 minutes with buffer time

---

# Interviewer Notes

## 🚩 Red Flags (Disqualifiers)
- **Scores < 5 in Section 1:** Fundamental Angular knowledge missing
- **Can't answer Q2, Q4, Q6, Q7:** Core concepts not understood
- **Scores < 3 in Section 5:** Not keeping up with modern Angular (acceptable for junior roles only)
- **Doesn't know signals (Q16-Q19):** Behind on Angular 16+ features
- **Doesn't know new control flow (Q20):** Not aware of Angular 17+ improvements

## ✅ Strong Signals (Hire Indicators)
- **Section 1 perfect score:** Strong fundamentals
- **Correctly answers Q8, Q13, Q17:** Understands memory management and best practices
- **Scores 8+ in Section 4:** Up to date with signals
- **Correctly solves Q25:** Can architect production-ready components with latest features
- **Uses proper terminology:** computed, effect, OnPush, inject(), resource()
- **Explains "why" in Q12, Q22:** Understanding over memorization

## 💬 Discussion Starters
Use answers to gauge depth:
- **If Q8 is wrong:** "How do you typically handle subscriptions in your current projects?"
- **If Q12 is partial:** "Tell me about a time when OnPush caused issues in your application"
- **If Q17 is wrong:** "Walk me through how you structure services in a large Angular app"
- **If Q22 is correct:** "What tools do you use to identify performance issues in Angular?"
- **If Q25 is impressive:** "How would you test this component?"

## 📊 Section-Based Assessment

### Section 1-2 (22 points): Foundation Check
- **< 10 points:** Not ready for professional Angular development
- **10-15 points:** Junior level, needs significant mentoring
- **16-20 points:** Solid foundation, ready for intermediate work
- **21-22 points:** Excellent fundamentals

### Section 3-4 (22 points): Professional Competency
- **< 8 points:** Needs training on modern patterns
- **8-14 points:** Intermediate, growing into advanced topics
- **15-19 points:** Strong professional knowledge
- **20-22 points:** Senior-level expertise

### Section 5 (16 points): Cutting Edge
- **< 5 points:** Not following Angular updates (OK for junior/mid)
- **5-9 points:** Aware of new features, needs practice
- **10-13 points:** Actively using modern Angular
- **14-16 points:** Expert level, stays current with ecosystem

## 🎯 Role Mapping

**Junior Developer (Target: 15-25 points)**
- Strong Section 1 (8+)
- Decent Section 2 (6+)
- Some Section 3 knowledge (3+)

**Mid-Level Developer (Target: 25-35 points)**
- Perfect Section 1 (10)
- Strong Section 2 (10+)
- Good Section 3 (8+)
- Basic Section 4 knowledge (5+)

**Senior Developer (Target: 35-45 points)**
- Perfect Sections 1-2 (22)
- Perfect Section 3 (12)
- Strong Section 4 (8+)
- Good Section 5 (10+)

**Expert/Lead (Target: 45+ points)**
- Near-perfect across all sections
- Explains reasoning clearly
- Provides alternative solutions
- Demonstrates production experience

