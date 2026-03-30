# 🚀 JavaScript OOP Masterclass (2026 Edition)

Welcome to the definitive guide on Modern Object-Oriented Programming (OOP) in JavaScript. This guide is designed for students and developers who want to master the cutting-edge patterns used in 2026.

---

## 🏛️ 1. The Modern Class Syntax
Classes in 2026 are more than just syntax sugar for prototypes; they are powerful, declarative blueprints.

```javascript
class Student {
  // Public Field
  school = "Global Tech Academy";

  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // Method
  introduce() {
    console.log(`Hi, I'm ${this.name} from ${this.school}.`);
  }
}

const alex = new Student("Alex", 20);
alex.introduce();
```

---

## 🔒 2. Encapsulation with Private Fields
True privacy is now native. Use the `#` prefix to hide internal state from the outside world.

```javascript
class BankAccount {
  #balance = 0; // Private field

  constructor(initialDeposit) {
    this.#balance = initialDeposit;
  }

  deposit(amount) {
    if (amount > 0) this.#balance += amount;
  }

  showBalance() {
    console.log(`Current Balance: $${this.#balance}`);
  }
}
```

> [!IMPORTANT]
> Private fields cannot be accessed outside the class, not even by subclasses. This is "Hard Privacy."

---

## 🎭 3. Getters, Setters, and Properties
The `get` and `set` keywords allow you to define "computed properties" that look like regular values but run logic behind the scenes.

### Using `get` and `set`
```javascript
class User {
  #firstName;
  #lastName;

  constructor(first, last) {
    this.#firstName = first;
    this.#lastName = last;
  }

  // Getter
  get fullName() {
    return `${this.#firstName} ${this.#lastName}`;
  }

  // Setter
  set fullName(value) {
    [this.#firstName, this.#lastName] = value.split(" ");
  }
}

const user = new User("Jane", "Doe");
console.log(user.fullName); // Jane Doe (Looks like a property, calls a function)
user.fullName = "John Smith"; 
```

---

## ⚡ 4. Auto-Accessors (The 2026 Standard)
Auto-accessors simplify the boilerplate of `get`/`set` patterns. They automatically create a private storage slot.

```javascript
class ThemeManager {
  // Automatically creates a private #theme and a getter/setter
  accessor theme = "dark"; 

  toggle() {
    this.theme = this.theme === "dark" ? "light" : "dark";
  }
}
```

---

## 🎨 5. Decorators
Decorators provide a declarative way to add behavior to classes, methods, or properties.

```javascript
function log(target, context) {
  console.log(`Entering ${context.name}...`);
}

class Service {
  @log
  fetchData() {
    return { data: "Success" };
  }
}
```

---

## 🏗️ 6. Inheritance & Static Blocks
Modern inheritance allows for complex initialization using `static` blocks.

```javascript
class Admin extends User {
  static #count = 0;

  static {
    // Complex static initialization
    console.log("Admin class initialized");
    this.#count = 100; 
  }

  constructor(name) {
    super(name, "Admin");
  }
}
```

---

## 📝 Summary Table for Students

| Concept | Keyword | Purpose |
| :--- | :--- | :--- |
| **Encapsulation** | `#` | Hide data from external access. |
| **Abstraction** | `get` / `set` | Expose logic as simple properties. |
| **Persistence** | `static` | Properties that belong to the class, not instances. |
| **Logic Injection** | `@decorator` | Add functionality without changing core code. |

---

> [!TIP]
> Always favor **Composition** over deep **Inheritance** trees for more maintainable code in 2026!
