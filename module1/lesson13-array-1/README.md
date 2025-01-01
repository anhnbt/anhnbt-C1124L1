# Tìm hiểu về mảng trong JavaScript

## Giới thiệu
Mảng trong JavaScript là một loại biến đặc biệt, được dùng để lưu trữ nhiều giá trị. Một mảng bao gồm một danh sách có thứ tự, có thể chứa nhiều kiểu dữ liệu khác nhau. Các phần tử trong mảng được truy cập bằng chỉ mục (index), bắt đầu từ 0.

Mảng giúp tổ chức mã nguồn một cách ngắn gọn, dễ đọc và bảo trì hơn. Chúng có thể chứa bất kỳ kiểu dữ liệu nào (Xem lại bài [7. Biến, kiểu dữ liệu và toán tử](https://james.codegym.vn/course/view.php?id=572#section-7)), bao gồm số (number), chuỗi (string) và đối tượng (object) (Chúng ta sẽ học ở buổi [16. Lập trình hướng đối tượng 1](https://james.codegym.vn/course/view.php?id=572#section-16)).

---

## Tạo một mảng

Có hai cách để tạo một mảng trong JavaScript:

**1. Sử dụng dấu ngoặc vuông []**

```javascript
const cars = [
    "Toyota",
    "Subaru",
    "BMW"
];
console.log(cars);  // ["Toyota", "Subaru", "BMW"]
```

**2. Sử dụng từ khóa `new`**

```javascript
const cars = new Array(
    "Toyota",
    "Subaru",,
    "BMW"
);
console.log(cars);  // ["Toyota", "Subaru", "BMW"]
```

---

## Truy cập phần tử trong mảng

Phần tử trong mảng được truy cập qua chỉ mục index:

```javascript
const cars = [
    "Toyota",
    "Subaru",
    "BMW"
];
console.log(cars[0]);  // Toyota
```

Truy cập một phần tử không tồn tại sẽ trả về `undefined`:

```javascript
console.log(cars[-1]);  // undefined
```

---

#### Thêm phần tử vào mảng

**1. Thêm vào cuối mảng**: Dùng phương thức `push()`:

```javascript
cars.push("KIA");
console.log(cars);  // ["Toyota", "Subaru", "BMW", "KIA"]
```

**2. Thêm vào đầu mảng**: Dùng phương thức `unshift()`:

```javascript
cars.unshift("Ferari");
console.log(cars);  // ["Ferari", "Toyota", "Subaru", "BMW", "KIA"]
```

---

## Xóa phần tử trong mảng

**1. Xóa một hoặc nhiều phần tử**: Dùng phương thức `splice()`:

```javascript
cars.splice(0, 2);
console.log(cars);  // ['Subaru', 'BMW', 'KIA']
```
Trong đó:
- Tham số đầu: Vị trí index bắt đầu xóa.
- Tham số thứ hai: Số phần tử cần xóa.

**2. Xóa phần tử cuối**: Dùng phương thức `pop()`:

```javascript
cars.pop();
console.log(cars);  // ['Subaru', 'BMW']
```

**3. Xóa phần tử đầu**: Dùng phương thức `shift()`:

```javascript
cars.shift();
console.log(cars);  // ["BMW"]
```

---

## Lặp qua các phần tử trong mảng

**1. Sử dụng vòng lặp `for`**:

```javascript
for (let i = 0; i < cars.length; i++) {
    console.log(i, cars[i]);  // 0 'BMW'
}
```

**2. Sử dụng vòng lặp `for...of`**:

```javascript
for (let car of cars) {
    console.log(car);  // BMW
}
```
Vòng lặp `for...of` ngắn gọn hơn nhưng không truy cập được index.

---

## Kết luận

Mảng là một phần cơ bản và linh hoạt trong JavaScript. Trong bài viết này, chúng ta đã học các tác vụ cơ bản như tạo, truy cập, thêm, xóa và lặp qua các phần tử trong mảng. Hy vọng bài viết này giúp bạn hiểu hơn về mảng trong JavaScript.

