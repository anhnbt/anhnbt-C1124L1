# Luyện logic cơ bản 
---

**Bài 1 - kiểm tra mảng tăng dần đều (luyện logic cơ bản)**  
- Nhập một mảng số từ bàn phím với độ dài 𝑛(𝑛≤20).
- Hiển thị mảng sau khi thêm mới các phần tử.
- Kiểm tra mảng vừa nhập. Nếu mảng **tăng dần đều**, hiển thị `OK`; nếu không phải, trả về `NO`.

**Ví dụ:**  
| Input        | Output  |
|--------------|---------|
| 0,2,4,6,8    | TRUE    |
| 5,10,15,20   | TRUE    |
| 2,4,7,9      | FALSE   |

---

### Gợi ý:

1. **Nhập mảng từ bàn phím:**
   - Sử dụng `prompt` để nhập số lượng phần tử 𝑛 (kiểm tra 𝑛≤20).
   - Sử dụng vòng lặp `for` để nhập từng phần tử của mảng từ bàn phím.

2. **Hiển thị mảng:**
   - Sử dụng `console.log` để in ra mảng vừa nhập.

3. **Kiểm tra mảng tăng dần đều:**
   - Học viên tự viết logic để kiểm tra.

---

### Mẫu code gợi ý:
```javascript
// Bước 1: Nhập số lượng phần tử của mảng
let n;
do {
    n = parseInt(prompt("Nhập số lượng phần tử của mảng (n <= 20):"), 10);
} while (isNaN(n) || n <= 0 || n > 20);

// Bước 2: Nhập từng phần tử của mảng
let array = [];
for (let i = 0; i < n; i++) {
    let element = parseInt(prompt(`Nhập phần tử thứ ${i + 1}:`), 10);
    array.push(element);
}

// Bước 3: Hiển thị mảng vừa nhập
console.log("Mảng vừa nhập:", array);

// Bước 4: Kiểm tra mảng tăng dần đều
// Học viên tự viết logic tại đây

// Ví dụ:
// console.log("OK"); hoặc console.log("NO");
```

Học viên sẽ thực hành tự viết phần kiểm tra mảng tăng dần đều ở Bước 4, giúp hiểu rõ hơn về logic và thuật toán. Chúc học viên học tốt!