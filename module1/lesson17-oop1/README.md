### Hiểu Và Tạo Đối Tượng Trong JavaScript  

**Mục tiêu:**  
Bài viết giúp các bạn ôn tập các kiến thức cơ bản về đối tượng (Object) trong JavaScript, bao gồm:  
- Khái niệm, lớp (class) và đối tượng (object).  
- Cách truy xuất và thiết lập thuộc tính, phương thức.  
- Ý nghĩa của từ khóa `this`.  
- Các cách định nghĩa, khởi tạo đối tượng và các tính chất OOP.  

---

### 1. Khái Niệm về Lớp và Đối Tượng

#### 1.1. Lớp (Class)  
- Một **lớp** là khuôn mẫu (blueprint) để tạo ra các đối tượng.  
- Lớp định nghĩa các thuộc tính (dữ liệu) và phương thức (hành vi) mà đối tượng của nó sẽ có.  

Trong JavaScript (ES6), bạn có thể định nghĩa một lớp như sau:  
```javascript
class Person {
    constructor(name, yearEstablished) {
        this.name = name; // Thuộc tính
        this.yearEstablished = yearEstablished;
    }

    greeting() { // Phương thức
        console.log(`Hi, I'm ${this.name}.`);
    }
}
```

#### 1.2. Đối Tượng (Object)  
- Một **đối tượng** là một thể hiện (instance) cụ thể của một lớp.  
- Đối tượng chứa các giá trị cụ thể của thuộc tính và hành vi được định nghĩa bởi lớp.  

Ví dụ, tạo đối tượng từ lớp `Person`:  
```javascript
let person = new Person("CodeGym", 2017); // Đối tượng `person`
console.log(person.name); // Output: CodeGym
person.greeting(); // Output: Hi, I'm CodeGym.
```

---

### 2. Tính Chất Cơ Bản Của OOP (Lập Trình Hướng Đối Tượng)

#### 2.1. Tính đóng gói (Encapsulation)  
- Đối tượng bao bọc dữ liệu (thuộc tính) và hành vi (phương thức) lại thành một đơn vị duy nhất.  
- Trong JavaScript, bạn có thể sử dụng các phương thức hoặc thuộc tính private (ES2022):  
```javascript
class BankAccount {
    #balance; // Thuộc tính private
    constructor(initialBalance) {
        this.#balance = initialBalance;
    }

    deposit(amount) {
        if (amount > 0) this.#balance += amount;
    }

    getBalance() {
        return this.#balance;
    }
}

let account = new BankAccount(100);
account.deposit(50);
console.log(account.getBalance()); // Output: 150
```

#### 2.2. Tính kế thừa (Inheritance)  
- Một lớp có thể kế thừa từ lớp khác, chia sẻ thuộc tính và phương thức mà không cần định nghĩa lại.  
- Trong JavaScript, sử dụng từ khóa `extends`:  
```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }

    speak() {
        console.log(`${this.name} makes a noise.`);
    }
}

class Dog extends Animal {
    speak() {
        console.log(`${this.name} barks.`);
    }
}

let dog = new Dog("Buddy");
dog.speak(); // Output: Buddy barks.
```

#### 2.3. Tính đa hình (Polymorphism)  
- Các lớp con có thể **ghi đè** (override) phương thức của lớp cha để cung cấp hành vi riêng.  
- Trong ví dụ trên, lớp `Dog` đã ghi đè phương thức `speak` của lớp `Animal`.

#### 2.4. Tính trừu tượng (Abstraction)  
- Ắn chi tiết triển khai bên trong, chỉ cung cấp giao diện (interface) cần thiết cho người dùng.  
- Trong JavaScript, bạn có thể kết hợp phương thức trừu tượng với lớp cơ bản (abstract class):  
```javascript
class Shape {
    area() {
        throw new Error("Method 'area()' must be implemented.");
    }
}

class Circle extends Shape {
    constructor(radius) {
        super();
        this.radius = radius;
    }

    area() {
        return Math.PI * this.radius ** 2;
    }
}

let circle = new Circle(5);
console.log(circle.area()); // Output: 78.53981633974483
```

---

### 3. Cách Truy Xuất và Thiết Lập Thuộc Tính

#### 3.1. Truy xuất thuộc tính  
- **Dùng ký hiệu chấm:**  
  ```javascript
  console.log(person.name); // Output: CodeGym
  console.log(person.yearEstablished); // Output: 2017
  ```
- **Dùng dấu ngoặc vuông:**  
  ```javascript
  console.log(person["name"]); // Output: CodeGym
  ```

#### 3.2. Thêm hoặc sửa thuộc tính  
Bạn có thể thêm hoặc thay đổi thuộc tính bất kỳ:  
```javascript
person.address = "Vietnam"; // Thêm thuộc tính
person.name = "CodeGym Vietnam"; // Sửa thuộc tính
```

---

### 4. Ý Nghĩa Của `this`

Trong một phương thức, từ khóa `this` tham chiếu đến đối tượng mà phương thức thuộc về. Ví dụ:  
```javascript
person.greeting = function() {
    console.log(`Hi, I'm ${this.name}.`); // "this.name" là "person.name"
};
person.greeting(); // Output: Hi, I'm CodeGym Vietnam.
```

---

### 5. Các Cách Tạo Đối Tượng

#### 5.1. Sử dụng Object Literal  
Đây là cách đơn giản và phổ biến nhất:  
```javascript
let person = {
    name: "CodeGym",
    yearEstablished: 2017,
    greeting: function() {
        console.log(`Hi, I'm ${this.name}.`);
    }
};
```

#### 5.2. Sử dụng Hàm Khởi Tạo (Constructor Function)  
Dùng hàm để khởi tạo nhiều đối tượng với cấu trúc tương tự:  
```javascript
function Person(name, yearEstablished) {
    this.name = name;
    this.yearEstablished = yearEstablished;
}

let person1 = new Person("CodeGym", 2017);
console.log(person1.name); // Output: CodeGym
```

#### 5.3. Prototype (Tối ưu Bộ Nhớ)  
Thêm phương thức vào `prototype` giúp các đối tượng chia sẻ chung hàm:  
```javascript
Person.prototype.greeting = function() {
    console.log(`Hi, I'm ${this.name}.`);
};

let person2 = new Person("CodeGym Vietnam", 2017);
person2.greeting(); // Output: Hi, I'm CodeGym Vietnam.
```

#### 5.4. Sử dụng Singleton  
Tạo một đối tượng dùng một lần:  
```javascript
let singletonPerson = new function() {
    this.name = "CodeGym Singleton";
    this.greeting = function() {
        console.log(`Hi, I'm ${this.name}.`);
    };
};
singletonPerson.greeting(); // Output: Hi, I'm CodeGym Singleton.
```

#### 5.5. Sử dụng Cú Pháp `class` Trong ES6  
Từ ES6, cú pháp `class` được giới thiệu để định nghĩa đối tượng giống các ngôn ngữ hướng đối tượng khác:  
```javascript
class Person {
    constructor(name, yearEstablished) {
        this.name = name;
        this.yearEstablished = yearEstablished;
    }

    greeting() {
        console.log(`Hi, I'm ${this.name}.`);
    }
}

let person3 = new Person("CodeGym ES6", 2017);
person3.greeting(); // Output: Hi, I'm CodeGym ES6.
```
