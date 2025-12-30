# Angular Interview Questions and Answers (with Examples)

Yeh document Angular ke zaroori concepts ko **Hindi/Hinglish** mein samjhata hai aur har concept ke saath **code examples** bhi deta hai taaki aapki understanding behtar ho sake.

---

**1. Angular kya hai?**

**Answer:** Angular ek **open-source front-end framework** hai jo Google ne develop kiya hai. Iska use modern, **single-page applications (SPA)** banane ke liye hota hai jo fast aur responsive hoti hain.

---

**2. Angular ke main features kya hain?**

**Answer:** Angular ke kuch khaas features:

*   **Component-based architecture:** App ko chhote-chhote, independent hisson mein baant dena.
*   **Two-way data binding:** Model (TypeScript) aur View (HTML) ka sync rehna. Jab ek jagah change hota hai, toh doosri jagah automatically update ho jaati hai.
*   **Dependency Injection (DI):** Code ko modular aur reusable banana. Angular automatically required services component ko provide karta hai.
*   **Directives:** DOM elements ko extra power aur functionality dena.
*   **Routing:** Bina poora page reload kiye, app ke different views ke beech navigation.
*   **Forms aur HTTP support:** Data handling aur backend API calls ke liye built-in modules.

**Example (Two-way Data Binding):**

```html
<!-- app.component.html -->
<input [(ngModel)]="userName" placeholder="Apna naam likhein">
<p>Aapka naam hai: {{ userName }}</p>
```

```typescript
// app.component.ts
import { Component } from '@angular/core';

@Component({ ... })
export class AppComponent {
  userName: string = 'Guest';
}
```
Jaise hi aap input field mein kuch likhoge, `userName` variable aur `<p>` tag ka content turant update ho jayega.

---

**3. TypeScript kya hai aur Angular ise kyon use karta hai?**

**Answer:** **TypeScript** JavaScript ka advanced version (superset) hai jo **static typing** provide karta hai. Iska matlab hai ki hum variables ka type (jaise `string`, `number`, `boolean`) define kar sakte hain.

Angular ise isliye use karta hai taaki:
1.  **Errors detect ho jayein:** Development ke waqt hi errors pakde ja sakein, run-time errors kam ho.
2.  **Code maintain karna aasan rahe:** Bade projects mein code ko samajhna aur refactor karna aasan ho jata hai.

**Example (TypeScript vs JavaScript):**

| TypeScript | Plain JavaScript |
| :--- | :--- |
| `let age: number = 25;` | `let age = 25;` |
| `function greet(name: string): string { ... }` | `function greet(name) { ... }` |

TypeScript mein `age` hamesha `number` hi rahega, agar galti se aapne `age = "pachis"` likha toh compiler error de dega.

---

**4. Angular Component kya hota hai?**

**Answer:** Component Angular app ka **basic building block** hota hai. Har component screen ke ek chote hisse (jaise header, sidebar, button) ko control karta hai.

Har component ke 3 main parts hote hain:
1.  **HTML (template):** UI (User Interface) ke liye.
2.  **CSS (style):** Look aur feel ke liye.
3.  **TypeScript (logic):** Functionality aur data handling ke liye.

**Example (Basic Component Structure):**

```typescript
// hello-world.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-hello-world', // HTML tag jisse component use hoga
  templateUrl: './hello-world.component.html', // Component ka HTML
  styleUrls: ['./hello-world.component.css'] // Component ki CSS
})
export class HelloWorldComponent {
  message = 'Namaste, Angular!';
}
```

```html
<!-- hello-world.component.html -->
<div>
  <h1>{{ message }}</h1>
  <button>Click Me</button>
</div>
```

---

**5. Angular Module kya hota hai?**

**Answer:** Module related components, services, aur directives ko ek saath group karta hai. Yeh ek **container** ki tarah hai jo batata hai ki kaun-kaun se parts ek doosre ke saath kaam karenge.

Har Angular app mein kam se kam ek **AppModule** (`app.module.ts`) hona zaroori hai, jise **Root Module** kehte hain.

**Example (App Module):**

```typescript
// app.module.ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';
import { HeaderComponent } from './header/header.component'; // Naya component

@NgModule({
  declarations: [
    AppComponent,
    HeaderComponent // Humne naye component ko declare kiya
  ],
  imports: [
    BrowserModule // Browser mein chalne ke liye zaroori module
  ],
  providers: [],
  bootstrap: [AppComponent] // Root component jahan se app start hogi
})
export class AppModule { }
```

---

**6. Directives kya hote hain?**

**Answer:** Directives HTML elements ko extra functionality dete hain. Yeh teen tarah ke hote hain:

1.  **Component Directives:** Yeh sabse common hain, jo template ke saath aate hain (jaise `AppComponent`).
2.  **Structural Directives:** Jo **DOM ka structure** badalte hain (elements ko add/remove karte hain).
    *   *Example:* `*ngIf`, `*ngFor`.
3.  **Attribute Directives:** Jo element ka **look ya behavior** badalte hain (DOM element ko modify karte hain).
    *   *Example:* `ngClass`, `ngStyle`.

**Example (Structural and Attribute Directives):**

```html
<!-- Structural Directive (*ngIf) -->
<p *ngIf="isAdmin">Aap admin hain.</p>

<!-- Attribute Directive (ngStyle) -->
<button [ngStyle]="{ 'background-color': 'blue', 'color': 'white' }">
  Styled Button
</button>
```

---

**7. Data Binding kya hoti hai?**

**Answer:** Yeh component (TypeScript) aur template (HTML) ke beech **communication ka tarika** hai. Iske 4 main types hain:

| Type | Direction | Syntax | Use Case |
| :--- | :--- | :--- | :--- |
| **Interpolation** | Component to View | `{{ value }}` | Text display karna |
| **Property Binding** | Component to View | `[property]="value"` | HTML element ki property set karna |
| **Event Binding** | View to Component | `(event)="handler()"` | User action (click, keyup) par function call karna |
| **Two-way Binding** | Both ways | `[(ngModel)]="value"` | Forms mein data sync karna |

**Example (All 4 Types):**

```html
<!-- app.component.html -->
<!-- 1. Interpolation -->
<p>Mera naam hai: {{ name }}</p>

<!-- 2. Property Binding -->
<img [src]="imageUrl" alt="Profile Picture">

<!-- 3. Event Binding -->
<button (click)="incrementCount()">Count Badhao</button>

<!-- 4. Two-way Binding -->
<input [(ngModel)]="name">
```

---

**8. Dependency Injection (DI) kya hota hai?**

**Answer:** DI ek **design pattern** hai jisme Angular automatically required services ya dependencies component ko provide karta hai. Humein manually `new Service()` karke objects create nahi karne padte. Isse code loose-coupled aur testable banta hai.

**Example (Injecting a Service):**

```typescript
// app.component.ts
import { Component } from '@angular/core';
import { UserService } from './user.service'; // Service import kiya

@Component({ ... })
export class AppComponent {
  // Constructor mein service ko declare kiya, Angular khud hi iska object de dega
  constructor(private userService: UserService) {
    const users = this.userService.getUsers();
    console.log(users);
  }
}
```

---

**9. Angular Services kya hoti hain?**

**Answer:** Services ka use **common logic** (jaise API calls, data sharing, logging) ko multiple components mein share karne ke liye hota hai. Yeh code reusability badhati hain aur components ko sirf UI logic tak seemit rakhti hain.

**Example (Basic Service):**

```typescript
// user.service.ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root' // Isse service poori app mein available ho jaati hai
})
export class UserService {
  private users = ['Alice', 'Bob', 'Charlie'];

  getUsers() {
    return this.users;
  }

  addUser(name: string) {
    this.users.push(name);
  }
}
```

---

**10. Angular Routing kya hai?**

**Answer:** Routing ke zariye hum app ke different views ya components ke beech **navigate** kar sakte hain bina poora page reload kiye. Yeh SPA (Single Page Application) ka ek important hissa hai.

**Example (Route Configuration):**

```typescript
// app-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

const routes: Routes = [
  { path: 'home', component: HomeComponent },
  { path: 'about', component: AboutComponent },
  { path: '', redirectTo: '/home', pathMatch: 'full' } // Default route
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

---

**11. ngIf kya karta hai?**

**Answer:** Yeh ek **structural directive** hai jo condition true hone par hi element ko **DOM mein add** karta hai, aur false hone par DOM se **remove** kar deta hai.

**Example:**

```typescript
// app.component.ts
isLoggedIn: boolean = true;
```

```html
<!-- app.component.html -->
<div *ngIf="isLoggedIn">
  Swagat hai! Aap logged in hain.
</div>
<div *ngIf="!isLoggedIn">
  Kripya login karein.
</div>
```

---

**12. ngFor kya karta hai?**

**Answer:** Yeh ek **structural directive** hai jo list ya array ko loop karke data display karne ke kaam aata hai. Har item ke liye template ko repeat karta hai.

**Example:**

```typescript
// app.component.ts
items = ['Apple', 'Banana', 'Cherry'];
```

```html
<!-- app.component.html -->
<ul>
  <li *ngFor="let item of items; let i = index">
    {{ i + 1 }}. Fruit: {{ item }}
  </li>
</ul>
<!-- Output:
1. Fruit: Apple
2. Fruit: Banana
3. Fruit: Cherry
-->
```

---

**13. Angular CLI kya hai?**

**Answer:** **CLI (Command Line Interface)** ek tool hai jo Angular projects ko manage karne mein help karta hai.

**Example (Common CLI Commands):**

| Command | Description |
| :--- | :--- |
| `ng new my-app` | Naya project create karna |
| `ng serve` | Project ko local server par run karna |
| `ng generate component header` | Naya component banana (`ng g c header` bhi likh sakte hain) |
| `ng build` | Production ke liye code compile karna |

---

**14. ngModel kya hai?**

**Answer:** Yeh forms mein **two-way data binding** ke liye use hota hai. Yeh `FormsModule` ka hissa hai. Input field mein jo likhoge, wo turant TypeScript variable mein update ho jayega, aur variable mein change karne par input field bhi update ho jayega.

**Example:**

```html
<!-- app.component.html -->
<input [(ngModel)]="userFeedback" placeholder="Apna feedback likhein">
<p>Live Feedback: {{ userFeedback }}</p>
```

---

**15. Angular Pipe kya hota hai?**

**Answer:** Pipes data ko **display karne se pehle transform** karte hain. Yeh data ko modify nahi karte, sirf uska presentation badalte hain.

**Example:**

```typescript
// app.component.ts
today = new Date();
name = 'manus ai';
```

```html
<!-- app.component.html -->
<p>Date: {{ today | date:'fullDate' }}</p> <!-- Date ko format karega -->
<p>Name: {{ name | uppercase }}</p> <!-- Text ko capital letters mein convert karega -->
<p>Currency: {{ 1234.56 | currency:'INR' }}</p> <!-- Number ko currency format mein badlega -->
```

---

**16. Single Page Application (SPA) kya hai?**

**Answer:** SPA aisi website hoti hai jo **sirf ek baar load** hoti hai. Jab aap kisi link par click karte ho, toh sirf zaroori content change hota hai, poora page reload nahi hota. Isse user experience fast aur smooth ho jaata hai.

---

**17. Angular lifecycle hooks kya hote hain?**

**Answer:** Jab koi component banta hai, update hota hai, ya delete hota hai, toh Angular kuch specific moments par functions run karta hai, jinhe **lifecycle hooks** kehte hain.

**Example (Common Hooks):**

| Hook | Jab Chalta Hai | Use Case |
| :--- | :--- | :--- |
| `ngOnInit` | Component initialize hone ke baad | Initial data fetch (API calls) |
| `ngOnChanges` | Component ke `@Input` properties change hone par | Input changes par action lena |
| `ngOnDestroy` | Component destroy hone se pehle | Subscriptions ko unsubscribe karna |

---

**18. ngOnInit() ka use kab karte hain?**

**Answer:** Yeh hook tab chalta hai jab component initialize ho jata hai. Iska use mostly **API calls** ya **initial data setup** karne ke liye kiya jata hai, kyunki is waqt component ki saari properties set ho chuki hoti hain.

**Example:**

```typescript
// app.component.ts
import { Component, OnInit } from '@angular/core';

@Component({ ... })
export class AppComponent implements OnInit {
  data: any;

  ngOnInit() {
    // API call yahan karte hain
    // this.http.get('/api/data').subscribe(res => this.data = res);
    console.log('Component successfully initialize ho gaya hai.');
  }
}
```

---

**19. Interpolation aur Property Binding mein kya fark hai?**

**Answer:** Dono hi Component se View mein data bhejte hain, lekin unka use alag hai:

*   **Interpolation (`{{ }}`):** Text display karne ke liye use hota hai. Yeh hamesha string value return karta hai.
*   **Property Binding (`[ ]`):** HTML element ki **property** (jaise `src`, `disabled`, `class`) set karne ke liye use hota hai. Yeh boolean, number, ya object values bhi set kar sakta hai.

**Example:**

```typescript
// app.component.ts
isButtonDisabled = true;
```

```html
<!-- app.component.html -->
<!-- Interpolation: Text set karta hai -->
<p>Button Status: {{ isButtonDisabled }}</p>

<!-- Property Binding: HTML property set karta hai -->
<button [disabled]="isButtonDisabled">Click Nahi Kar Sakte</button>
```

---

**20. Template-driven vs Reactive Forms?**

**Answer:** Angular mein forms banane ke do tareeke hain:

| Feature | Template-driven Forms | Reactive Forms |
| :--- | :--- | :--- |
| **Complexity** | Simple forms ke liye | Complex forms ke liye |
| **Logic** | Logic HTML template mein hota hai (`ngModel`) | Logic TypeScript file mein hota hai (`FormGroup`) |
| **Scalability** | Kam scalable | Bahut scalable aur testable |
| **Setup** | `FormsModule` import karna padta hai | `ReactiveFormsModule` import karna padta hai |

**Example (Reactive Form - TypeScript Logic):**

```typescript
// app.component.ts
import { FormGroup, FormControl } from '@angular/forms';

loginForm = new FormGroup({
  username: new FormControl(''),
  password: new FormControl('')
});
```

---

**21. Angular mein 'ViewChild' kya hai?**

**Answer:** `ViewChild` ek decorator hai jiska use kisi **child component** ya **DOM element** ko parent component ke TypeScript file mein access karne ke liye hota hai.

**Example:**

```html
<!-- app.component.html -->
<input #nameInput type="text">
<button (click)="focusInput()">Focus Karo</button>
```

```typescript
// app.component.ts
import { ViewChild, ElementRef } from '@angular/core';

@Component({ ... })
export class AppComponent {
  // 'nameInput' reference ko access kiya
  @ViewChild('nameInput') inputElement: ElementRef;

  focusInput() {
    this.inputElement.nativeElement.focus(); // Input field par focus set kiya
  }
}
```

---

**22. 'Input' aur 'Output' decorators kya hain?**

**Answer:** Yeh decorators components ke beech data transfer karne ke liye use hote hain:

*   **`@Input()`:** Parent component se Child component mein **data bhejne** ke liye.
*   **`@Output()`:** Child component se Parent component ko **event bhejne** ke liye.

**Example:**

```typescript
// child.component.ts
import { Component, Input, Output, EventEmitter } from '@angular/core';

@Component({ ... })
export class ChildComponent {
  @Input() parentData: string; // Parent se data receive hoga

  @Output() dataEvent = new EventEmitter<string>(); // Parent ko event bhejega

  sendDataToParent() {
    this.dataEvent.emit('Hello from Child!');
  }
}
```

---

**23. Observable aur Promise mein kya fark hai?**

**Answer:** Dono hi **asynchronous operations** handle karte hain, lekin unmein yeh main fark hain:

| Feature | Promise | Observable |
| :--- | :--- | :--- |
| **Values** | Single value deta hai | Data ki **stream** handle karta hai, multiple values de sakta hai |
| **Cancellation** | Cancel nahi kiya ja sakta | `unsubscribe()` karke cancel kiya ja sakta hai |
| **Libraries** | Built-in JavaScript | RxJS library use karta hai |
| **Laziness** | Eager (define karte hi chalu ho jata hai) | Lazy (jab tak `subscribe` nahi karte, chalu nahi hota) |

**Example (Conceptual):**

```typescript
// Observable: Multiple values over time
const stream = new Observable(observer => {
  observer.next(1);
  setTimeout(() => observer.next(2), 1000);
});
stream.subscribe(val => console.log(val)); // Output: 1, then 2 after 1s
```

---

**24. HttpClient kya hai?**

**Answer:** `HttpClient` Angular ka built-in service hai jo **backend API se data fetch** karne ya bhejne ke liye use hota hai. Yeh **Observables** return karta hai.

**Example (Fetching Data):**

```typescript
// app.component.ts
import { HttpClient } from '@angular/common/http';

constructor(private http: HttpClient) { }

fetchData() {
  this.http.get('https://api.example.com/data')
    .subscribe(data => {
      console.log('API se data mila:', data);
    });
}
```

---

**25. Bootstrapping kya hota hai?**

**Answer:** Wo process jisse Angular app **start** hoti hai aur **main component** (usually `AppComponent`) load hota hai. Yeh process `main.ts` file se shuru hota hai, jo `AppModule` ko load karta hai.

---

**26. Transpilation kya hai?**

**Answer:** TypeScript code ko **browser-friendly JavaScript** mein convert karna. Kyunki browsers sirf JavaScript samajhte hain, TypeScript code ko run karne se pehle Transpiler (jaise Babel ya TypeScript compiler) use karke JavaScript mein badla jata hai.

---

**27. Angular Universal kya hai?**

**Answer:** Angular apps ko **server-side render (SSR)** karne ke liye tool. Isse app ka pehla view server par hi render ho jata hai aur phir browser ko bheja jata hai. Isse **SEO (Search Engine Optimization)** aur initial load time behtar hota hai.

---

**28. 'AOT' vs 'JIT' compilation?**

**Answer:**

*   **JIT (Just-in-Time):** Compilation **browser mein run-time** par hota hai. Development ke dauran use hota hai.
*   **AOT (Ahead-of-Time):** Compilation **build ke waqt pehle hi** ho jata hai. Production build ke liye use hota hai. AOT se app fast load hoti hai aur size chota ho jata hai.

---

**29. Interpolation ka syntax kya hai?**

**Answer:** Double Curly Braces: `{{ variable_name }}`.

**Example:**
```html
<p>Current Year: {{ 2025 }}</p>
```

---

**30. Angular mein Interface ka kya role hai?**

**Answer:** Interface ka use **data ka structure ya shape define** karne ke liye hota hai, taaki **type safety** bani rahe. Yeh sirf development ke waqt help karta hai aur compilation ke baad JavaScript code mein gayab ho jata hai.

**Example:**

```typescript
// user.interface.ts
interface User {
  id: number;
  name: string;
  email: string;
  isActive: boolean;
}

// app.component.ts
let currentUser: User = {
  id: 1,
  name: 'Manus',
  email: 'manus@ai.com',
  isActive: true
};
// Agar aap 'id' ko string dene ki koshish karoge, toh TypeScript error de dega.
```
