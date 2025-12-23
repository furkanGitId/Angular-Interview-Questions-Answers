# Angular Beginner Interview Questions & Answers (Hinglish) 🚀

Yeh repository Angular beginners ke liye banayi gayi hai jo interview ki taiyari kar rahe hain ya apna basics strong karna chahte hain. Ismein total 30 questions hain jo simple Hinglish bhasha mein samjhaye gaye hain.

### 1. Angular kya hai?
**Answer:** Angular ek open-source front-end framework hai jo Google ne develop kiya hai. Iska use modern, single-page applications (SPA) banane ke liye hota hai jo fast aur responsive hoti hain.

### 2. Angular ke main features kya hain?
**Answer:** - **Component-based architecture**: App ko chhote-chhote hisson mein baant dena.
- **Two-way data binding**: Model aur View ka sync rehna.
- **Dependency Injection**: Code ko modular aur reusable banana.
- **Directives**: DOM elements ko power dena.
- **Routing**: Bina page reload kiye navigation.
- **Forms aur HTTP support**: Data handling aur API calls.

### 3. TypeScript kya hai aur Angular ise kyon use karta hai?
**Answer:** TypeScript JavaScript ka advanced version (superset) hai jo static typing provide karta hai. Angular ise isliye use karta hai taaki development ke waqt hi errors detect ho jayein aur code maintain karna aasan rahe.

### 4. Angular Component kya hota hai?
**Answer:** Component Angular app ka basic building block hota hai. Har component ke 3 main parts hote hain:
- **HTML (template)**: UI ke liye.
- **CSS (style)**: Look aur feel ke liye.
- **TypeScript (logic)**: Functionality ke liye.

### 5. Angular Module kya hota hai?
**Answer:** Module related components, services, aur directives ko ek saath group karta hai. Har Angular app mein kam se kam ek **AppModule** hona zaroori hai.

### 6. Directives kya hote hain?
**Answer:** Directives HTML elements ko extra functionality dete hain.
- **Component Directives**: Jo template ke saath aate hain.
- **Structural Directives**: Jo DOM ka structure badalte hain (`*ngIf`, `*ngFor`).
- **Attribute Directives**: Jo element ka look badalte hain (`ngClass`, `ngStyle`).

### 7. Data Binding kya hoti hai?
**Answer:** Yeh component (TypeScript) aur template (HTML) ke beech communication ka tarika hai.
- **Interpolation**: `{{ value }}`
- **Property Binding**: `[property]="value"`
- **Event Binding**: `(click)="doSomething()"`
- **Two-way Binding**: `[(ngModel)]="name"`

### 8. Dependency Injection (DI) kya hota hai?
**Answer:** DI ek design pattern hai jisme Angular automatically required services ya dependencies component ko provide karta hai. Humein manually objects create nahi karne padte.

### 9. Angular Services kya hoti hain?
**Answer:** Services ka use common logic (jaise API calls) ko multiple components mein share karne ke liye hota hai. Yeh code reusability badhati hain.

### 10. Angular Routing kya hai?
**Answer:** Routing ke zariye hum app ke different views ya components ke beech navigate kar sakte hain bina poora page reload kiye.

### 11. ngIf kya karta hai?
**Answer:** Yeh ek structural directive hai jo condition `true` hone par hi element ko DOM mein add karta hai.
```html
<div *ngIf="isLoggedIn">Swagat hai!</div>
```

### 12. ngFor kya karta hai?
**Answer:** Yeh list ya array ko loop karke data display karne ke kaam aata hai.
```html
<li *ngFor="let item of items">{{ item }}</li>
```

### 13. Angular CLI kya hai?
**Answer:** CLI (Command Line Interface) ek tool hai jo project create karne (`ng new`), component banane (`ng g c`), aur server run karne (`ng serve`) mein help karta hai.

### 14. ngModel kya hai?
**Answer:** Yeh forms mein two-way data binding ke liye use hota hai. Input field mein jo likhoge, wo turant TypeScript variable mein update ho jayega.

### 15. Angular Pipe kya hota hai?
**Answer:** Pipes data ko display karne se pehle transform karte hain.
```html
{{ today | date:'fullDate' }} <!-- Date ko format karega -->
{{ name | uppercase }} <!-- Text ko capital karega -->
```

### 16. Single Page Application (SPA) kya hai?
**Answer:** SPA aisi website hoti hai jo sirf ek baar load hoti hai. Jab aap kisi link par click karte ho, toh sirf zaroori content change hota hai, poora page reload nahi hota.

### 17. Angular lifecycle hooks kya hote hain?
**Answer:** Jab koi component banta hai, update hota hai, ya delete hota hai, toh Angular kuch specific moments par functions run karta hai, jinhe hooks kehte hain (e.g., `ngOnInit`, `ngOnDestroy`).

### 18. ngOnInit() ka use kab karte hain?
**Answer:** Yeh hook tab chalta hai jab component initialize ho jata hai. Iska use mostly API calls ya data setup karne ke liye kiya jata hai.

### 19. Interpolation aur Property Binding mein kya fark hai?
**Answer:** - **Interpolation**: Text display karne ke liye (`{{ }}`).
- **Property Binding**: HTML element ki properties set karne ke liye (`[]`).

### 20. Template-driven vs Reactive Forms?
**Answer:** - **Template-driven**: Chhote forms ke liye, logic HTML template mein hota hai.
- **Reactive Forms**: Bade aur complex forms ke liye, logic TypeScript file mein hota hai.

### 21. Angular mein 'ViewChild' kya hai?
**Answer:** `ViewChild` ka use kisi child component ya DOM element ko parent component ke TypeScript mein access karne ke liye hota hai.

### 22. 'Input' aur 'Output' decorators kya hain?
**Answer:** - **@Input()**: Parent se Child mein data bhejne ke liye.
- **@Output()**: Child se Parent ko event bhejne ke liye.

### 23. Observable aur Promise mein kya fark hai?
**Answer:** - **Promise**: Ek baar data deta hai.
- **Observable**: Data ki stream handle karta hai aur multiple values de sakta hai.

### 24. HttpClient kya hai?
**Answer:** Backend API se data fetch karne ya bhejne ke liye built-in service.

### 25. Bootstrapping kya hota hai?
**Answer:** Wo process jisse Angular app start hoti hai aur main component load hota hai.

### 26. Transpilation kya hai?
**Answer:** TypeScript code ko browser-friendly JavaScript mein convert karna.

### 27. Angular Universal kya hai?
**Answer:** Angular apps ko server-side render (SSR) karne ke liye tool.

### 28. 'AOT' vs 'JIT' compilation?
**Answer:** - **JIT**: Browser mein runtime par compile hota hai.
- **AOT**: Build ke waqt pehle hi compile ho jata hai.

### 29. Interpolation ka syntax kya hai?
**Answer:** Double Curly Braces `{{ variable_name }}`.

### 30. Angular mein Interface ka kya role hai?
**Answer:** Data ka structure ya shape define karne ke liye, taaki type safety bani rahe.

**Happy Coding!** 💻✨
        