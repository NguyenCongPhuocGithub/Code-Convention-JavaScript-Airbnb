# **HƯỚNG DẪN CODE CONVENTION JAVASCRIPT AIRBNB ESLINT**

## **MỤC LỤC**

[**I. Thứ tự import của một page hoặc component**](#I_link)

[**II. Thứ tự viết style cho css/sass**](#II_link)

[**III. Thứ tự viết api/ action**](#III_link)

[**IV. Thứ tự props**](#IV_link)

[**V. Thứ tự viết style cho css/sass**](#V_link)

<a id="V_link">VI. Convention cho react</a>

## **NỘI DUNG**
### **<a id="I_link">I. Thứ tự import của một page hoặc component</a>**
1. Import từ node_modules:

   - react
   - react-router-dom
   - proptypes
   - thư viện UI (reactstrap)
   - các phần con lại là bảng chữ cái
   - css của thư viện

2. Import theo chức năng:

   - api
   - assets
   - constants
   - routes
   - store
   - utils

3. Import theo component:

   - Layout: Theo bảng chữ cái
   - pages: Theo bảng chữ cái
   - components: : Theo bảng chữ cái

4. Import static nội bộ của page/ component

   - css/ sass

**<a id="II_link">II. Thứ tự viết style cho css/sass</a>**

// block
- display
- width
- height
- padding top => bottom => left => right
- padding top => bottom => left => right
- margin top => bottom => left => right
- margin top => bottom => left => right

// position
- position
- top
- bottom
- left
- right

// text
- color
- fontFamily
- fontSize,
- textDecoration

// effect
- animation
- tranform

// layout
- z-index

**<a id="III_link">III. Thứ tự viết api/ action</a>**

    1. Get all
    2. Get list
    3. Get detail
    4. Add new
    5. Edit | Update
    6. Delete
    7. Restore

**<a id="IV_link">IV. Thứ tự props</a>**
Thư viện truyền từ APP hoặc index vào component (ví dụ: match, navigate)

    - bool
    - number
    - string
    - object
    - arr
    - function

**<a id="V_link">V. Thứ tự tạo biến | hàm trong component</a>**

    1. props
    2. useRef | useHistory | other use... sắp xếp theo thứ tự bảng chữ cái
    3. useState
    4. state of library (useFormik)
    5. useEffect
    6. render Html
    7. function (sắp xếp linh hoạt theo Eslint)
    8. return
    9. prop types
       9.1 Thứ tự prop types
       Khai báo default trước ví dụ: match, navigate,...
       Thứ tự bool - num - string - object - arr - func tương tự 'Thứ tự props'
    10. default props
        Thứ tự bool - num - string - object - arr - func tương tự 'Thứ tự props'

**<a id="V_link">V. Thứ tự tạo biến | hàm trong component</a>**

1. Tên của component:</br>
   - Đặt tên đề cập tới trách nhiệm của component
   - Rõ ràng và duy nhất trong chương trình
   - Sử dụng đuôi file .js với trường hợp chỉ có xử lý javaScript và đặt đuôi file .jsx với trường hợp có xử lý javaScript và return UI.
2. Sử dụng component:</br>
   - Giữ component nhỏ
   - Mỗi component cho một file

VII. Sử dụng phong cách build code airbnb</br>
1.  Type:</br>
    1.2 Kiểu phức tạp: Khi bạn truy cập một giá trị kiểu phức tạp, bạn làm việc trên tham chiếu giá trị của nó. - object - array - function</br>
    Ví dụ:

    const foo = [1, 2];
    const bar = foo;

            bar[0] = 9;

            console.log(foo[0], bar[0]); // => 9, 9

2.  References:</br>
    2.1 Sử dụng const đối với tất cả các tham chiếu; tránh sử dụng var. eslint: prefer-const, no-const-assign</br>
    Ví dụ:

    // không tốt
    var a = 1;
    var b = 2;

    // tốt
    const a = 1;
    const b = 2;
    2.2 Nếu bạn bắt buộc phải gán lại các tham chiếu, sử dụng let, thay vì var. eslint: no-var</>
    Ví dụ:

    // không tốt
    var count = 1;
    if (true) {
      count += 1;
    }

    // tốt, sử dụng let.
    let count = 1;
    if (true) {
      count += 1;
    }

    2.3 Lưu ý rằng cả let và const đều thuộc phạm vi khối, còn var thuộc phạm vi hàm.</br>
    Ví dụ:

    // const và let chỉ tồn tại trong phạm vi khối tạo ra chúng.
    {
      let a = 1;
      const b = 1;
      var c = 1;
    }
    console.log(a); // ReferenceError
    console.log(b); // ReferenceError
    console.log(c); // In ra 1

Note: Chỉ sử dụng var cho trường hợp khi const và let không thể đáp ứng.

3. Objects</br>
3.1 Sử dụng cú pháp nguyên văn {} để khởi tạo đối tượng. eslint: no-new-object</br>
    Ví dụ:

    // không tốt
    const item = new Object();

    // tốt
    const item = {};

3.2 Sử dụng các tên được tính của thuộc tính [key()] khi tạo các đối tượng có các tên của thuộc tính là động.</br>
    Ví dụ:

    function getKey(k) {
      return `tên của thuộc tính là ${k}`;
    }

    // không tốt
    const obj = {
      id: 5,
      name: 'San Francisco',
    };
    obj[getKey('enabled')] = true;

    // tốt
    const obj = {
      id: 5,
      name: 'San Francisco',
      [getKey('enabled')]: true,
    };

