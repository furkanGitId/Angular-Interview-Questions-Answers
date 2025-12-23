# 🚀 Angular Interview Questions (Hinglish Edition) - 30+ Q&A

**👋 Hello Dosto!**

Yeh repository un sabhi ke liye hai jo **Angular interviews** ki taiyari kar rahe hain. Yahan humne **30 se zyada** sabse zaroori sawalon (questions) ko **Hinglish** (Hindi aur English ka mix) mein jawab ke saath pesh kiya hai. Isse aapko concepts ko samajhne aur interview mein confidently bolne mein madad milegi. Yeh questions **Beginner** se lekar **Advanced** level tak cover karte hain.

---

## 🌟 Part 1: Basic Concepts (Buniyadi Sawal)

### 1. Angular Kya Hai? (What is Angular?)

**Jawab (Answer):**
**Angular** ek **TypeScript-based** open-source framework hai jise Google ne banaya hai. Iska main kaam **Single Page Applications (SPAs)** banana hai. Yeh ek complete **frontend development platform** hai jo aapko bade aur maintainable applications banane mein help karta hai.

### 2. TypeScript Kya Hai aur Angular isse kyon use karta hai? (What is TypeScript and why does Angular use it?)

**Jawab (Answer):**
**TypeScript** Microsoft dwara develop ki gayi ek **superset of JavaScript** hai. Iska matlab hai ki yeh JavaScript ke saare features ko support karta hai, aur usmein **Static Typing** jaisi extra features add karta hai. Angular isse isliye use karta hai kyunki static typing se code mein **errors compile-time** par hi pakde jaate hain, jisse bade projects mein code **zyada reliable** aur **maintainable** banta hai.

### 3. Components Kya Hote Hain? (What are Components?)

**Jawab (Answer):**
**Components** Angular application ke **building blocks** hote hain. Har component ka apna ek **view** (HTML template) aur **logic** (TypeScript class) hota hai. Yeh milkar UI ke ek chote, independent part ko represent karte hain.

### 4. Data Binding Kya Hai? (What is Data Binding?)

**Jawab (Answer):**
**Data Binding** woh mechanism hai jisse aap component ki **TypeScript data** aur uske **HTML view** ke beech connection establish karte hain. Isse data automatically sync rehta hai.

| Type | Flow | Hinglish Explanation | Example |
| :--- | :--- | :--- | :--- |
| **One-Way Binding** | Component -> View | Data sirf component se view tak jaata hai. | `{{ data }}` (Interpolation), `[property]="data"` (Property Binding) |
| **Two-Way Binding** | Component <-> View | Data dono taraf flow karta hai. | `[(ngModel)]="data"` |

### 5. Directives Kitne Types Ki Hoti Hain? (What are the types of Directives?)

**Jawab (Answer):**
Directives woh classes hain jo DOM elements par apply hokar unka behavior ya appearance change karti hain. Teen main types hain:

1.  **Component Directives:** Yeh sabse common hain, inka apna template hota hai.
2.  **Structural Directives:** Yeh DOM structure ko change karte hain (elements ko add/remove karte hain). **Example:** `*ngIf`, `*ngFor`.
3.  **Attribute Directives:** Yeh element ke appearance ya behavior ko change karte hain. **Example:** `[ngClass]`, `[ngStyle]`.

### 6. `NgModule` Kya Hai? (What is an NgModule?)

**Jawab (Answer):**
**`NgModule`** Angular application mein code ko organize karne ka tareeka hai. Yeh ek container hai jo related components, services, directives, aur pipes ko ek saath group karta hai. Har Angular app mein kam se kam ek **Root Module** (`AppModule`) zaroor hota hai.

### 7. Services aur Dependency Injection (DI) kya hain?

**Jawab (Answer):**
*   **Services:** Yeh woh classes hain jo **business logic** aur **data sharing** ke liye use hoti hain. Jaise ki, API calls karna ya data ko cache karna. Services ka koi view nahi hota.
*   **Dependency Injection (DI):** Yeh ek design pattern hai jismein ek class (jaise ki component) apni dependencies (jaise ki service) ko khud create nahi karti, balki Angular framework use provide karta hai. Isse code **reusable** aur **testable** banta hai.

### 8. Routing ka kya kaam hai? (What is the purpose of Routing?)

**Jawab (Answer):**
**Routing** Single Page Applications (SPAs) mein different views (pages) ko manage karta hai. Yeh user ko application ke alag-alag parts mein navigate karne deta hai, bina poore page ko reload kiye. Hum `RouterModule` aur `Routes` array ka use karke paths define karte hain.

### 9. Pipes kya hote hain? (What are Pipes?)

**Jawab (Answer):**
**Pipes** data ko **transform** karne ke liye use hote hain, jisse woh user ko display hone se pehle ek naye format mein aa jaaye. Jaise ki, date ko format karna, text ko uppercase karna, ya currency symbol add karna.

*   **Example:** `{{ dateValue | date:'shortDate' }}`

### 10. Angular aur AngularJS mein kya farak hai? (Difference between Angular and AngularJS?)

**Jawab (Answer):**
**AngularJS** (version 1.x) aur **Angular** (version 2+) do alag frameworks hain.

| Feature | AngularJS (v1.x) | Angular (v2+) |
| :--- | :--- | :--- |
| **Language** | JavaScript | TypeScript |
| **Architecture** | MVC (Model-View-Controller) | Component-based |
| **Mobile Support** | Limited | Excellent (Mobile-first) |
| **Performance** | Slower (Two-way binding, dirty checking) | Faster (One-way binding, better Change Detection) |

---

## 🛠️ Part 2: Intermediate Concepts (Thode Mushkil Sawal)

### 11. `ngOnInit` aur `constructor` mein kya difference hai?

**Jawab (Answer):**
*   **`constructor`:** Yeh ek **TypeScript/JavaScript** feature hai. Iska use **Dependency Injection (DI)** ke liye hota hai. Jab component class ka object banta hai, tab yeh sabse pehle chalta hai.
*   **`ngOnInit`:** Yeh ek **Angular Lifecycle Hook** hai. Yeh component ke **initialization** ke liye best place hai. Jab Angular component ko initialize kar deta hai aur uski saari **input properties** set ho jaati hain, tab yeh chalta hai. **API calls** aur complex initialization logic yahan likhna chahiye.

### 12. Observables aur Promises mein kya farak hai?

**Jawab (Answer):**
Dono hi **asynchronous operations** ko handle karte hain, par unmein bade differences hain:

| Feature | Observable | Promise |
| :--- | :--- | :--- |
| **Values** | **Multiple** values over time (Stream) | **Single** value (ya error) |
| **Cancellation** | **Cancellable** (Subscription ko unsubscribe kar sakte hain) | **Non-cancellable** |
| **Execution** | **Lazy** (Jab tak subscribe nahi karte, tab tak chalta nahi) | **Eager** (Jaise hi define kiya, turant execute hona shuru) |

### 13. Lifecycle Hooks kya hote hain? (What are Lifecycle Hooks?)

**Jawab (Answer):**
**Lifecycle Hooks** woh methods hain jinhe Angular component ya directive ki life cycle ke specific points par automatically call karta hai.

*   **Main Hooks:** `ngOnChanges`, `ngOnInit`, `ngDoCheck`, `ngAfterContentInit`, `ngAfterContentChecked`, `ngAfterViewInit`, `ngAfterViewChecked`, aur `ngOnDestroy`.

### 14. Component mein data kaise share karte hain? (How to share data between components?)

**Jawab (Answer):**
Data share karne ke kai tareeke hain:

1.  **Parent to Child:** `@Input()` decorator ka use karke.
2.  **Child to Parent:** `@Output()` decorator aur `EventEmitter` ka use karke.
3.  **Unrelated Components:** **Services** ka use karke, jismein hum `BehaviorSubject` ya `Subject` (RxJS) ka use karte hain.

### 15. Decorators kya hote hain? (What are Decorators?)

**Jawab (Answer):**
**Decorators** woh functions hain jo classes, properties, methods, ya parameters par metadata attach karte hain. Yeh TypeScript ka feature hai. Angular inka use karke classes ko special meaning deta hai.

*   **Examples:** `@Component`, `@NgModule`, `@Injectable`, `@Input`, `@Output`.

### 16. AOT (Ahead-of-Time) aur JIT (Just-in-Time) compilation mein kya farak hai?

**Jawab (Answer):**
*   **JIT (Just-in-Time):** Compilation browser mein **runtime** par hota hai. Yeh development ke dauran use hota hai.
*   **AOT (Ahead-of-Time):** Compilation **build process** ke dauran hota hai, browser mein load hone se pehle. Yeh production build ke liye use hota hai.
    *   **Fayde:** Faster rendering, smaller application size, aur zyada security.

### 17. Template Reference Variable kya hai? (What is a Template Reference Variable?)

**Jawab (Answer):**
Yeh ek tareeka hai jisse hum **HTML template** mein kisi DOM element ya component instance ko **reference** de sakte hain. Isse hum component class mein us element ya component ko access kar sakte hain.

*   **Syntax:** `#myVariable` (e.g., `<input #myInput>`)

### 18. Pure Pipe aur Impure Pipe mein kya farak hai?

**Jawab (Answer):**
*   **Pure Pipe:** Yeh pipe tabhi re-calculate hota hai jab uski **input value change** hoti hai (primitive value ya object reference change ho). Yeh zyada efficient hota hai.
*   **Impure Pipe:** Yeh pipe har **change detection cycle** mein re-calculate hota hai, chahe input value change ho ya na ho. Yeh performance ko affect kar sakta hai, isliye kam use karna chahiye.

### 19. RxJS kya hai aur iska kya role hai? (What is RxJS and its role?)

**Jawab (Answer):**
**RxJS** (Reactive Extensions for JavaScript) ek library hai jo **reactive programming** ke liye use hoti hai. Yeh **Observables** ka use karke asynchronous data streams ko handle karti hai. Angular mein yeh **HTTP requests**, **event handling**, aur **state management** mein bahut zaroori hai.

### 20. Interceptors ka kya use hai? (What is the use of Interceptors?)

**Jawab (Answer):**
**HTTP Interceptors** woh services hain jo outgoing **HTTP requests** ko aur incoming **HTTP responses** ko handle karte hain. Inka use common tasks ke liye hota hai, jaise ki:

*   Har request mein **Authentication Token** add karna.
*   Request/Response ko **log** karna.
*   **Error handling** karna.

---

## 🧠 Part 3: Advanced Concepts (Gehre Sawal)

### 21. Change Detection aur `OnPush` strategy kya karti hai?

**Jawab (Answer):**
*   **Change Detection:** Yeh woh mechanism hai jisse Angular data model mein changes ko view (HTML) mein update karta hai.
*   **`OnPush` Strategy:** Yeh ek optimization technique hai. Jab hum kisi component ki change detection strategy ko `OnPush` set karte hain, toh Angular us component ko sirf tabhi check karta hai jab:
    1.  Uski **Input properties** ka **reference** change ho.
    2.  Component ya uske children mein koi **event** fire ho.
    *   *Isse application ki performance bahut improve hoti hai.*

### 22. Lazy Loading kya hai aur iska kya fayda hai?

**Jawab (Answer):**
*   **Lazy Loading:** Yeh ek technique hai jismein application ke modules ko **on-demand** load kiya jaata hai. Jab user kisi particular route par jaata hai, tabhi us route se associated module load hota hai.
*   **Fayda (Benefit):** Iska sabse bada fayda yeh hai ki **initial load time** kam ho jaata hai, jisse user experience (UX) behtar hota hai.

### 23. State Management kyon zaroori hai? (Why is State Management necessary?)

**Jawab (Answer):**
Jab application bada ho jaata hai, toh data ko components ke beech pass karna mushkil ho jaata hai. **State Management** libraries (jaise ki **NgRx** ya **NgXs**) ek **single source of truth** provide karte hain. Saara data ek hi jagah (Store) par rehta hai, aur components ko jab bhi data chahiye hota hai, woh store se le lete hain. Isse data flow **clear**, **traceable**, aur **debug** karna aasan ho jaata hai.

### 24. Angular application ki performance kaise optimize karte hain? (How to optimize Angular application performance?)

**Jawab (Answer):**
Performance optimize karne ke kai tareeke hain:

1.  **Lazy Loading** ka use karna.
2.  **`OnPush` Change Detection Strategy** ka use karna.
3.  Production ke liye **AOT Compilation** use karna.
4.  **TrackBy** function ka use `*ngFor` mein karna.
5.  **Unsubscribe** karna saare Observables ko `ngOnDestroy` mein.
6.  Bade lists ke liye **Virtual Scrolling** ka use karna.

### 25. RxJS operators `forkJoin`, `combineLatest`, aur `merge` mein kya farak hai?

**Jawab (Answer):**
Yeh teeno operators multiple Observables ko combine karte hain, par alag tareeke se:

*   **`forkJoin`:** Yeh tabhi **single value** emit karta hai jab **saare** source Observables **complete** ho jaate hain. Yeh unki **last emitted value** ko combine karta hai. (Jaise `Promise.all`).
*   **`combineLatest`:** Yeh tabhi value emit karta hai jab **saare** source Observables ne **kam se kam ek value** emit kar di ho. Uske baad, jab bhi koi ek Observable nayi value emit karta hai, toh yeh sabki **latest value** ko combine karke emit karta hai.
*   **`merge`:** Yeh saare source Observables ki values ko **time ke hisaab se** combine karke ek single Observable mein emit karta hai.

### 26. Custom Decorator kaise banate hain? (How to create a Custom Decorator?)

**Jawab (Answer):**
Custom Decorator banane ke liye hum ek **TypeScript function** likhte hain jo target, property key, aur property descriptor ko as argument leta hai. Yeh function phir class, method, property, ya parameter par extra functionality add karta hai.

### 27. Server-Side Rendering (SSR) in Angular kya hai?

**Jawab (Answer):**
**SSR** (Server-Side Rendering) mein Angular application ko **server** par render kiya jaata hai, aur phir complete HTML ko browser par bheja jaata hai.

*   **Fayde:** **Better SEO** (Search Engine Optimization) aur **Faster initial load time** (kyunki user ko blank screen nahi dikhti). Angular mein hum **Angular Universal** ka use karke SSR implement karte hain.

### 28. Angular mein security ko kaise handle karte hain? (How to handle security in Angular?)

**Jawab (Answer):**
Angular mein security ke liye built-in mechanisms hain:

1.  **XSS (Cross-Site Scripting) Protection:** Angular by default data ko **sanitize** karta hai. Agar aapko koi HTML ya URL bind karna hai, toh aapko `DomSanitizer` ka use karke use manually **bypass security** karna padega.
2.  **CSRF (Cross-Site Request Forgery) Protection:** Hum `HttpClient` ka use karte hain, jo server se **CSRF token** ko read karke har request mein automatically add karta hai.
3.  **Content Security Policy (CSP):** `index.html` mein CSP headers set karna.

### 29. Unit Testing ke liye kaunse tools use hote hain? (Which tools are used for Unit Testing?)

**Jawab (Answer):**
Angular mein unit testing ke liye do main tools use hote hain:

1.  **Jasmine:** Yeh ek **testing framework** hai jo tests likhne ke liye syntax provide karta hai (e.g., `describe`, `it`, `expect`).
2.  **Karma:** Yeh ek **test runner** hai jo browser mein tests ko run karta hai aur results ko display karta hai.

### 30. `NgZone` ka kya role hai? (What is the role of NgZone?)

**Jawab (Answer):**
**`NgZone`** (ya Zone.js) Angular ka woh part hai jo **asynchronous operations** (jaise ki `setTimeout`, `Promise resolution`, `HTTP requests`) ko track karta hai. Jab bhi koi asynchronous operation complete hoti hai, `NgZone` Angular ko notify karta hai ki **Change Detection** run karna hai.

### 31. Difference between `ViewChild` and `ContentChild`?

**Jawab (Answer):**
Dono hi decorators hain jo child elements ko access karne ke liye use hote hain, par unka scope alag hai:

*   **`@ViewChild`:** Yeh component ke **apne template** ke andar ke elements ya components ko access karta hai.
*   **`@ContentChild`:** Yeh un elements ya components ko access karta hai jo **parent component** ne is component ke `<ng-content>` tag ke andar **project** kiye hain.

---

## 📚 References (Sandarbh)

*   [Angular Official Documentation](https://angular.io/)
*   [Top Angular Interview Questions](https://www.interviewbit.com/angular-interview-questions/)
*   [Angular Interview Questions & Answers - GitHub](https://github.com/sudheerj/angular-interview-questions)

**All the best for your interview! 👍**
