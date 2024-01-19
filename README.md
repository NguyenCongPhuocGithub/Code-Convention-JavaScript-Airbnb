# **HƯỚNG DẪN CODE CONVENTION JAVASCRIPT AIRBNB ESLINT**

## **MỤC LỤC**

[**I. Thứ tự import của một page hoặc component**](#I_link)

[**II. Thứ tự viết style cho css/sass**](#II_link)

[**III. Thứ tự viết api/ action**](#III_link)

[**IV. Thứ tự props**](#IV_link)

[**V. Thứ tự viết style cho css/sass**](#V_link)

[**VI. Sử dụng phong cách build code airbnb**](#VI_link)</br>
    [1. Type](#Type_link)</br>
    [2. References](#References_link)</br>
    [3. Objects](#Objects_link)<br>
    [4. Arrays](#Arrays_link)<br>
    [5. Destructuring](#Destructuring_link)<br>
    [6. Strings](#Strings_link)<br>
    [7. Functions](#Functions_link)<br>
    [8. Arrow Functions](#Arrow_Functionss_link)<br>
    [10. Modules](#Modules_link)<br>
    [11. Iterators and Generators](#Iterators_and_Generators_link)<br>
    [12. Properties](#Properties_link)<br>
    [13. Variables](#Variables_link)<br>
    [15. Comparison Operators & Equality](#Comparison_Operators_&_Equality_link)<br>
    [16. Blocks](#Blocks_link)<br>
    [17. Control_Statements](#Control_Statements_link)<br>
    [18. Comments](#Comments_link)<br>
    [19. Whitespace](#Whitespace_link)<br>
    [20. Commas](#Commas_link)<br>
    [21. Semicolons](#Semicolons_link)<br>
    [22. Type Casting & Coercion](#TypeCasting_&_Coercion_link)<br>
    [23. Naming Conventions](#Naming_Conventions_link)<br>
    

## **NỘI DUNG**
**<span id="I_link">I. Thứ tự import của một page hoặc component</span>**
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

**<span id="II_link">II. Thứ tự viết style cho css/sass</span>**

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

**<span id="III_link">III. Thứ tự viết api/ action</span>**

    1. Get all
    2. Get list
    3. Get detail
    4. Add new
    5. Edit | Update
    6. Delete
    7. Restore

**<span id="IV_link">IV. Thứ tự props</span>**

Thư viện truyền từ APP hoặc index vào component (ví dụ: match, navigate)

    - bool
    - number
    - string
    - object
    - arr
    - function

**<span id="V_link">V. Thứ tự tạo biến | hàm trong component</span>**

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

**<span id="V_link">V. Thứ tự tạo biến | hàm trong component</span>**

1. Tên của component:</br>
   - Đặt tên đề cập tới trách nhiệm của component
   - Rõ ràng và duy nhất trong chương trình
   - Sử dụng đuôi file .js với trường hợp chỉ có xử lý javaScript và đặt đuôi file .jsx với trường hợp có xử lý javaScript và return UI.
2. Sử dụng component:</br>
   - Giữ component nhỏ
   - Mỗi component cho một file

**<span id="VI_link">VII. Sử dụng phong cách build code airbnb</span>**</br>

**<span id="Type_link">1. Type</span></br>**
1.2 Kiểu phức tạp: Khi bạn truy cập một giá trị kiểu phức tạp, bạn làm việc trên tham chiếu giá trị của nó. - object - array - function </br>
    Ví dụ: </br>

```javascript
    const foo = [1, 2];
    const bar = foo;

            bar[0] = 9;

            console.log(foo[0], bar[0]); // => 9, 9
```

**<span id="References_link">2. References</span></br>**
 2.1 Sử dụng `const` đối với tất cả các tham chiếu; tránh sử dụng `var`. eslint: `prefer-const`, `no-const-assign` </br>
    Ví dụ: </br>

```javascript
    // không tốt
    var a = 1;
    var b = 2;

    // tốt
    const a = 1;
    const b = 2;
```

2.2 Nếu bạn bắt buộc phải gán lại các tham chiếu, sử dụng `let`, thay vì `var`. eslint: `no-var`</br>
    Ví dụ: </br>

```javascript
    // không tốt
    var count = 1;
    if (true) {
      count += 1;
    }

    // tốt, sử dụng `let`.
    let count = 1;
    if (true) {
      count += 1;
    }
```
    
2.3 Lưu ý rằng cả `let` và `const` đều thuộc phạm vi khối, còn `var` thuộc phạm vi hàm.</br>
    Ví dụ: <br/>

```javascript
    // `const` và `let` chỉ tồn tại trong phạm vi khối tạo ra chúng.
    {
      let a = 1;
      const b = 1;
      var c = 1;
    }
    console.log(a); // ReferenceError
    console.log(b); // ReferenceError
    console.log(c); // In ra 1
```

Note: Chỉ sử dụng var cho trường hợp khi const và let không thể đáp ứng.

**<span id="Objects_link">3. Objects</span></br>**
3.1 Sử dụng cú pháp nguyên văn `{}` để khởi tạo đối tượng. eslint: `no-new-object`</br>
    Ví dụ: </br>

```javascript
    // không tốt
    const item = new Object();

    // tốt
    const item = {};
```

3.2 Sử dụng các tên được tính của thuộc tính `[key()]` khi tạo các đối tượng có các tên của thuộc tính là động.</br>
    Ví dụ: </br>

```javascript
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
```

3.3 Sử dụng cú pháp định nghĩa method rút gọn để định nghĩa các method của đối tượng. eslint: `object-shorthand` </br>
    Ví dụ: </br>

```javascript
// không tốt
const atom = {
  value: 1,

  addValue: function (value) {
    return atom.value + value;
  },
};

// tốt
const atom = {
  value: 1,

  addValue(value) {
    return atom.value + value;
  },
};   
```

3.4 Sử dụng cú pháp định nghĩa thuộc tính `value` rút gọn để định nghĩa các thuộc tính `value` của đối tượng. eslint: `object-shorthand` </br>
    Ví dụ: </br>
```javascript
const lukeSkywalker = 'Luke Skywalker';

// không tốt
const obj = {
  lukeSkywalker: lukeSkywalker,
};

// tốt
const obj = {
  lukeSkywalker,
};
```

3.5 Gom tất cả các thuộc tính rút gọn ở trên cùng khi khai báo đối tượng. </br>
    Ví dụ: <br>

```javascript
const anakinSkywalker = 'Anakin Skywalker';
const lukeSkywalker = 'Luke Skywalker';

// không tốt
const obj = {
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
  lukeSkywalker,
  episodeThree: 3,
  mayTheFourth: 4,
  anakinSkywalker,
};

// tốt
const obj = {
  lukeSkywalker,
  anakinSkywalker,
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
  episodeThree: 3,
  mayTheFourth: 4,
};
```

3.6 Chỉ sử dụng dấu lược `' '` cho các thuộc tính có định danh không hợp lệ. eslint: `quote-props` 
</br>
    Ví dụ: </br>

```javascript
// không tốt
const bad = {
  'foo': 3,
  'bar': 4,
  'một-cái-tên': 5,
};

// tốt
const good = {
  foo: 3,
  bar: 4,
  'một-cái-tên': 5,
};
```

3.7 Không gọi các phương thức `Object.prototype` một cách trực tiếp, ví dụ như `hasOwnProperty`, `propertyIsEnumerable`, và `isPrototypeOf`. eslint: `no-prototype-builtins` </br>
    Ví dụ: </br>

```javascript
// không tốt
console.log(object.hasOwnProperty(key));

// tốt
console.log(Object.prototype.hasOwnProperty.call(object, key));

// tốt nhất
const has = Object.prototype.hasOwnProperty; // lưu tạm phương thức một lần, dùng cho cả mô-đun.
console.log(has.call(object, key));
/* hoặc */
import has from 'has'; // https://www.npmjs.com/package/has
console.log(has.call(object, key));
```

3.8 Ưu tiên sử dụng cú pháp liệt kê `...` so với `Object.assign` để tạo bản sao nhanh của một đối tượng. Sử dụng toán tử còn-lại `...` để tạo một đối tượng mới với một số thuộc tính đã bị loại bỏ. eslint: `prefer-object-spread` </br>
    Ví dụ: </br>

```javascript
// rất không tốt
const original = { a: 1, b: 2 };
const copy = Object.assign(original, { c: 3 }); // cái này làm biến đổi `original` ಠ_ಠ
delete copy.a; // cái này cũng vậy

// không tốt
const original = { a: 1, b: 2 };
const copy = Object.assign({}, original, { c: 3 }); // copy => { a: 1, b: 2, c: 3 }

// tốt
const original = { a: 1, b: 2 };
const copy = { ...original, c: 3 }; // copy => { a: 1, b: 2, c: 3 }

const { a, ...noA } = copy; // noA => { b: 2, c: 3 }
```

**<span id="Arrays_link">4. Arrays</span></br>**
4.1 Sử dụng cú pháp nguyên văn `[]` để khởi tạo mảng. eslint: `no-array-constructor` </br>
    Ví dụ: </br>

```javascript
// không tốt
const items = new Array();

// tốt
const items = [];
```

4.2 Sử dụng `Array#push`, thay vì phép gán, để thêm các mục cho một mảng. </br>
    Ví dụ: </br>

```javascript
const someStack = [];

// không tốt
someStack[someStack.length] = 'abracadabra';

// tốt
someStack.push('abracadabra');
```

4.3 Sử dụng toán tử liệt kê `...` để sao nhanh một mảng. </br>
    Ví dụ: </br>

```javascript
// không tốt
const len = items.length;
const itemsCopy = [];
let i;

for (i = 0; i < len; i += 1) {
  itemsCopy[i] = items[i];
}

// tốt
const itemsCopy = [...items];
```

4.4 Để chuyển đổi một đối tượng khả duyệt thành một mảng, sử dụng toán tử liệt kê `...` thay vì `Array.from.` </br>
    Ví dụ: </br>

```javascript
const foo = document.querySelectorAll('.foo');

// tốt
const nodes = Array.from(foo);

// tốt nhất
const nodes = [...foo];
```

4.5 Sử dụng `Array.from` để chuyển đổi một đối tượng giống-mảng thành một mảng. </br>
    Ví dụ: </br>

```javascript
const arrLike = { 0: 'foo', 1: 'bar', 2: 'baz', length: 3 };

// không tốt
const arr = Array.prototype.slice.call(arrLike);

// tốt
const arr = Array.from(arrLike);
```

4.8 Sử dụng dấu ngắt dòng trước và sau các dấu đóng và mở ngoặc vuông nếu một mảng nằm trên nhiều dòng.</br>
    Ví dụ: </br>

```javascript
// không tốt
const arr = [
  [0, 1], [2, 3], [4, 5],
];

const objectInArray = [{
  id: 1,
}, {
  id: 2,
}];

const numberInArray = [
  1, 2,
];

// tốt
const arr = [[0, 1], [2, 3], [4, 5]];

const objectInArray = [
  {
    id: 1,
  },
  {
    id: 2,
  },
];

const numberInArray = [
  1,
  2,
];
```

**<span id="Destructuring_link">5. Destructuring</span></br>**
5.1 Sử dụng trích xuất đối tượng khi truy cập và sử dụng nhiều thuộc tính của một đối tượng. eslint: `prefer-destructuring` </br>
    Ví dụ: </br>

```javascript
// không tốt
function getFullName(user) {
  const firstName = user.firstName;
  const lastName = user.lastName;

  return `${firstName} ${lastName}`;
}

// tốt
function getFullName(user) {
  const { firstName, lastName } = user;
  return `${firstName} ${lastName}`;
}

// best
function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`;
}
```

5.2 Hãy sử dụng trích xuất mảng. eslint: `prefer-destructuring` </br>
    Ví dụ: </br>

```javascript
const arr = [1, 2, 3, 4];

// không tốt
const first = arr[0];
const second = arr[1];

// tốt
const [first, second] = arr;
```

**<span id="Strings_link">6. Strings</span></br>**
6.1 Use single quotes `''` for strings. eslint: `quotes` </br>
    Ví dụ: </br>

```javascript
// bad
const name = "Capt. Janeway";

// bad - template literals should contain interpolation or newlines
const name = `Capt. Janeway`;

// good
const name = 'Capt. Janeway';
```

6.2 Các chuỗi, dù khiến cho độ dài của dòng lớn hơn 100 ký tự, không nên được viết thành nhiều dòng sử dụng ghép chuỗi. </br>
    Ví dụ: </br>

```javascript
// không tốt
const errorMessage = 'Đây là một lỗi rất dài mà được ném ra bởi \
Người Dơi. Khi bạn ngừng nghĩ về việc tại sao Người Dơi chẳng có liên \
quan gì với thứ này, bạn sẽ vẫn chẳng đi đến đâu với \
đâu.';

// không tốt
const errorMessage = 'Đây là một lỗi rất dài mà được ném ra bởi' +
    'Người Dơi. Khi bạn ngừng nghĩ về việc tại sao Người Dơi chẳng có liên' +
    'quan gì với thứ này, bạn sẽ vẫn chẳng đi đến đâu với' +
    'đâu.';

// tốt
const errorMessage = 'Đây là một lỗi rất dài mà được ném ra bởi Người Dơi. Khi bạn ngừng nghĩ về việc tại sao Người Dơi chẳng có liên quan gì với thứ này, bạn sẽ vẫn chẳng đi đến đâu với đâu.';
```

6.3 Khi xây dựng các chuỗi theo một chu trình, sử dụng mẫu chuỗi thay vì ghép chuỗi. eslint: `prefer-template` `template-curly-spacing` </br>
    Ví dụ: </br>

```javascript
// không tốt
function sayHi(name) {
  return 'Bạn có khỏe không, ' + name + '?';
}

// không tốt
function sayHi(name) {
  return ['Bạn có khỏe không, ', name, '?'].join();
}

// tốt
function sayHi(name) {
  return `Bạn có khỏe không, ${name}?`;
}
```

6.4 Không bao giờ sử dụng eval() cho một chuỗi, điều đó mở ra rất nhiều các lỗ hổng và rủi ro. eslint: `no-eval` </br>

6.5 Không sử dụng các ký tự thoát trong một chuỗi khi không cần thiết. eslint: `no-useless-escape` 
</br>
    Ví dụ: </br>

```javascript
// không tốt
const foo = '\'cái này\' \đư\ợc \"cho trong ngoặc\"';

// tốt
const foo = '\'cái này\' được "cho trong ngoặc"';
const foo = `tên của tôi là '${name}'`;
```

**<span id="Functions_link">7. Functions</span></br>**
7.1 Sử dụng biểu thức hàm hữu danh thay vì khai báo hàm. eslint: `func-style` </br>
    Ví dụ: </br>

```javascript
// không tốt
function foo() {
  // ...
}

// không tốt
const foo = function () {
  // ...
};

// tốt
// tên riêng của hàm, phân biệt với tên tham chiếu được gọi khi cần sử dụng
const short = function longUniqueMoreDescriptiveLexicalFoo() {
  // ...
};
```

7.3 Không bao giờ khai báo một hàm bên trong một khối không phải hàm (if, while, v.v.). Thay vào đó, hãy gán hàm cho một biến. Các trình duyệt đều sẽ cho phép bạn làm điều đó, nhưng tiếc là, cách mà chúng diễn dịch là khác nhau. eslint: `no-loop-func`

7.4 Ghi chú: ECMA-262 định nghĩa một khối là tập hợp một hoặc một vài câu lệnh. Một khai báo hàm không phải là một câu lệnh. </br>
    Ví dụ: </br>

```javascript
// không tốt
if (currentUser) {
  function test() {
    console.log('Đừng!');
  }
}

// tốt
let test;
if (currentUser) {
  test = () => {
    console.log('Tốt đó.');
  };
}
```

7.5 Không bao giờ đặt tên một tham số là `arguments`. Tham số này sẽ được ưu tiên hơn đối tượng `arguments` được cung cấp cho mỗi phạm vi hàm. </br>
    Ví dụ: </br>

```javascript
// không tốt
function foo(name, options, arguments) {
  // ...
}

// tốt
function foo(name, options, args) {
  // ...
}
```

7.6 Không bao giờ sử dụng `arguments`, thay vào đó, hãy sử dụng cú pháp còn-lại `...` . eslint: `prefer-rest-params` </br>
    Ví dụ: </br>

```javascript
// không tốt
function concatenateAll() {
  const args = Array.prototype.slice.call(arguments);
  return args.join('');
}

// tốt
function concatenateAll(...args) {
  return args.join('');
}
```

7.8 Tránh gây ra hiệu ứng phụ với tham số mặc định. </br>
    Ví dụ: </br>

```javascript
var b = 1;
// không tốt
function count(a = b++) {
  console.log(a);
}
count();  // 1
count();  // 2
count(3); // 3
count();  // 3
```

7.9 Luôn để các tham số mặc định ở sau cùng. eslint: `default-param-last` </br>
    Ví dụ: </br>

```javascript
// không tốt
function handleThings(opts = {}, name) {
  // ...
}

// tốt
function handleThings(name, opts = {}) {
  // ...
}
```

7.10 Không bao giờ sử dụng hàm tạo Function để tạo hàm. eslint: `no-new-func` </br>
    Ví dụ: </br>

```javascript
// không tốt
var add = new Function('a', 'b', 'return a + b');

// vẫn là không tốt
var subtract = Function('a', 'b', 'return a - b');
```

7.11 Sử dụng các dấu cách giữa các bộ phận hàm. eslint: `space-before-function-paren` `space-before-blocks` </br>
    Ví dụ: </br>

```javascript
// không tốt
const f = function(){};
const g = function (){};
const h = function() {};

// tốt
const x = function () {};
const y = function a() {};
```

7.12 Không bao giờ làm biến đổi các tham số. eslint: `no-param-reassign` </br>
    Ví dụ: </br>

```javascript
// không tốt
function f1(obj) {
  obj.key = 1;
}

// tốt
function f2(obj) {
  const key = Object.prototype.hasOwnProperty.call(obj, 'key') ? obj.key : 1;
}
```

7.13 Không bao giờ gán lại các tham số. eslint: `no-param-reassign` </br>
    Ví dụ: </br>

```javascript
// không tốt
function f1(a) {
  a = 1;
  // ...
}

function f2(a) {
  if (!a) { a = 1; }
  // ...
}

// tốt
function f3(a) {
  const b = a || 1;
  // ...
}

function f4(a = 1) {
  // ...
}
```

7.14 Ưu tiên sử dụng cú pháp liệt kê `...` để gọi các hàm bất định. eslint: `prefer-spread` </br>
    Ví dụ: </br>

```javascript
// không tốt
const x = [1, 2, 3, 4, 5];
console.log.apply(console, x);

// tốt
const x = [1, 2, 3, 4, 5];
console.log(...x);

// không tốt
new (Function.prototype.bind.apply(Date, [null, 2016, 8, 5]));

// tốt
new Date(...[2016, 8, 5]);
```

**<span id="Arrow_Functions_link">8. Arrow Functions</span></br>**
8.1 Khi bạn phải sử dụng một hàm vô danh (như khi cần truyền một hàm gọi lại trên cùng dòng), sử dụng ký pháp hàm mũi tên. eslint: `prefer-arrow-callback`, `arrow-spacing` </br>
    Ví dụ: </br>

```javascript
// không tốt
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});

// tốt
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

8.2 Nếu như phần thân hàm chỉ gồm một câu lệnh trả về một biểu thức mà không có hiệu ứng phụ, bỏ qua dấu ngoặc nhọn và sử dụng trả về ngầm định. Nếu không, giữ nguyên dấu ngoặc và sử dụng lệnh `return`. eslint: `arrow-parens`, `arrow-body-style` </br>
    Ví dụ: </br>

```javascript
// không tốt
[1, 2, 3].map((number) => {
  const nextNumber = number + 1;
  `Một chuỗi có chứa số ${nextNumber}.`;
});

// tốt
[1, 2, 3].map((number) => `Một chuỗi có chứa số ${number + 1}.`);

// tốt
[1, 2, 3].map((number) => {
  const nextNumber = number + 1;
  return `Một chuỗi có chứa số ${nextNumber}.`;
});

// tốt
[1, 2, 3].map((number, index) => ({
  [index]: number,
}));

// Không dùng trả về ngầm định khi có hiệu ứng phụ
function foo(callback) {
  const val = callback();
  if (val === true) {
    // Thực hiện gì đó nếu hàm gọi lại trả về true
  }
}

let bool = false;

// không tốt
foo(() => bool = true);

// tốt
foo(() => {
  bool = true;
});
```

8.3 Trong trường hợp biểu thức nằm trên nhiều dòng, nhóm nó trong ngoặc để dễ đọc hơn. </br>
    Ví dụ: </br>

```javascript
// không tốt
['get', 'post', 'put'].map((httpMethod) => Object.prototype.hasOwnProperty.call(
    httpMagicObjectWithAVeryLongName,
    httpMethod,
  )
);

// tốt
['get', 'post', 'put'].map((httpMethod) => (
  Object.prototype.hasOwnProperty.call(
    httpMagicObjectWithAVeryLongName,
    httpMethod,
  )
));
```

8.4 Luôn sử dụng ngoặc tròn xung quanh các đối số để rõ ràng và nhất quán. eslint: `arrow-parens` </br>
    Ví dụ: </br>

```javascript
// không tốt
[1, 2, 3].map(x => x * x);

// tốt
[1, 2, 3].map((x) => x * x);

// tốt
[1, 2, 3].map((number) => (
  `Một chuỗi thật là dài với số ${number}. Nó quá dài để chúng ta có thể viết cùng dòng với dòng .map!`
));

// không tốt
[1, 2, 3].map(x => {
  const y = x + 1;
  return x * y;
});

// tốt
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

8.5 Tránh gây dễ nhầm lẫn giữa cú pháp hàm mũi tên `(=>)` với các toán tử so sánh (`<=`, `>=`). eslint: `no-confusing-arrow` </br>
    Ví dụ: </br>

```javascript
// không tốt
const itemHeight = (item) => item.height <= 256 ? item.largeSize : item.smallSize;

// không tốt
const itemHeight = (item) => item.height >= 256 ? item.largeSize : item.smallSize;

// tốt
const itemHeight = (item) => (item.height <= 256 ? item.largeSize : item.smallSize);

// tốt
const itemHeight = (item) => {
  const { height, largeSize, smallSize } = item;
  return height <= 256 ? largeSize : smallSize;
};
```

8.6 Cách đặt vị trí của phần thân hàm mũi tên với trả về ngầm định. eslint: `implicit-arrow-linebreak` </br>
    Ví dụ: </br>

```javascript
// không tốt
(foo) =>
  bar;

(foo) =>
  (bar);

// tốt
(foo) => bar;
(foo) => (bar);
(foo) => (
   bar
)
```

**<span id="Modules_link">10. Modules</span></br>**
10.1 Luôn sử dụng mô-đun (`import`/`export`) thay vì một hệ thống mô-đun phi chuẩn. Bạn luôn có thể dịch mã sang hệ thống mô-đun mà bạn thích. </br>
    Ví dụ: </br>

```javascript
// bad
const AirbnbStyleGuide = require('./AirbnbStyleGuide');
module.exports = AirbnbStyleGuide.es6;

// ok
import AirbnbStyleGuide from './AirbnbStyleGuide';
export default AirbnbStyleGuide.es6;

// best
import { es6 } from './AirbnbStyleGuide';
export default es6;
```

10.2 Không sử dụng ký tự đại diện để nhập. </br>
    Ví dụ: </br>

```javascript
// không tốt
import * as AirbnbStyleGuide from './AirbnbStyleGuide';

// tốt
import AirbnbStyleGuide from './AirbnbStyleGuide';
```

10.3 Và không xuất trực tiếp từ một lệnh nhập. </br>
    Ví dụ: </br>

```javascript
// không tốt
// tên tệp es6.js
export { es6 as default } from './AirbnbStyleGuide';

// tốt
// tên tệp es6.js
import { es6 } from './AirbnbStyleGuide';
export default es6;
```

10.4 Chỉ nhập từ một đường dẫn ở chung một chỗ. eslint: `no-duplicate-imports` </br>
    Ví dụ: </br>

```javascript
// không tốt
import foo from 'foo';
// … và nhập một vài thứ nữa … //
import { named1, named2 } from 'foo';

// tốt
import foo, { named1, named2 } from 'foo';

// tốt
import foo, {
  named1,
  named2,
} from 'foo';
```

10.5 Không xuất các ràng buộc có thể bị biến đổi. eslint:` import/no-mutable-exports` </br>
    Ví dụ: </br>

```javascript
// không tốt
let foo = 3;
export { foo };

// tốt
const foo = 3;
export { foo };
```

10.6 Trong các mô-đun chỉ có một địa chỉ xuất, ưu tiên xuất mặc định thay vì xuất hữu danh. eslint: `import/prefer-default-export` </br>
    Ví dụ: </br>

```javascript
// không tốt
export function foo() {}

// tốt
export default function foo() {}
```

10.7 Đặt tất cả các lệnh import trên cùng. eslint: `import/first` </br>
    Ví dụ: </br>

```javascript
// không tốt
import foo from 'foo';
foo.init();

import bar from 'bar';

// tốt
import foo from 'foo';
import bar from 'bar';

foo.init();
```

10.8 Các lệnh nhập nhiều dòng nên được căn đầu dòng giống như các mảng hay đối tượng nguyên văn nhiều dòng. eslint: `object-curly-newline` </br>
    Ví dụ: </br>

```javascript
// không tốt
import {longNameA, longNameB, longNameC, longNameD, longNameE} from 'path';

// tốt
import {
  longNameA,
  longNameB,
  longNameC,
  longNameD,
  longNameE,
} from 'path';
```

10.9 Không cho phép cú pháp bộ tải Webpack trong các lệnh nhập mô-đun. eslint: `import/no-webpack-loader-syntax` </br>
    Ví dụ: </br>

```javascript
// không tốt
import fooSass from 'css!sass!foo.scss';
import barCss from 'style!css!bar.css';

// tốt
import fooSass from 'foo.scss';
import barCss from 'bar.css';
```

10.10 Không thêm phần mở rộng của tên tệp JavaScript. eslint: `import/extensions` </br>
    Ví dụ: </br>

```javascript
// không tốt
import foo from './foo.js';
import bar from './bar.jsx';
import baz from './baz/index.jsx';
// tốt
import foo from './foo';
import bar from './bar';
import baz from './baz';
```

**<span id="Iterators_and_Generators_link">11. Iterators and Generators</span></br>**
11.1 Không sử dụng các đối tượng duyệt. Ưu tiên sử dụng các hàm bậc cao hơn của JavaScript thay vì các vòng lặp như for-in hay for-of. eslint: `no-iterator ``no-restricted-syntax` </br>
    Ví dụ: </br>

```javascript
const numbers = [1, 2, 3, 4, 5];

// không tốt
let sum = 0;
for (let num of numbers) {
  sum += num;
}
sum === 15;

// tốt
let sum = 0;
numbers.forEach((num) => {
  sum += num;
});
sum === 15;

// tốt nhất, sử dụng hàm
const sum = numbers.reduce((total, num) => total + num, 0);
sum === 15;

// không tốt
const increasedByOne = [];
for (let i = 0; i < numbers.length; i++) {
  increasedByOne.push(numbers[i] + 1);
}

// tốt
const increasedByOne = [];
numbers.forEach((num) => {
  increasedByOne.push(num + 1);
});

// tốt nhất, vẫn là sử dụng hàm
const increasedByOne = numbers.map((num) => num + 1);
```

11.2 Không sử dụng các hàm sinh trị `function*` vào thời điểm này. </br>

11.3 Nếu bạn bắt buộc phải dùng các hàm sinh trị, hoặc bạn bỏ qua khuyến nghị của chúng tôi, hãy đảm bảo rằng bạn sử dụng dấu cách giữa các bộ phận hàm một cách hợp lý. eslint: `generator-star-spacing` </br>
    Ví dụ: </br>

```javascript
// không tốt
function * foo() {
  // ...
}

// không tốt
const bar = function * () {
  // ...
};

// không tốt
const baz = function *() {
  // ...
};

// không tốt
const quux = function*() {
  // ...
};

// không tốt
function*foo() {
  // ...
}

// không tốt
function *foo() {
  // ...
}

// rất tệ
function
*
foo() {
  // ...
}

// rất rất tệ
const wat = function
*
() {
  // ...
};

// tốt
function* foo() {
  // ...
}

// tốt
const foo = function* () {
  // ...
};
```

**<span id="Properties_link">10. Properties</span></br>**
12.1 Sử dụng ký pháp chấm `.` để truy cập các thuộc tính. eslint: `dot-notation` </br>
    Ví dụ: </br>

```javascript
const luke = {
  jedi: true,
  age: 28,
};

// không tốt
const isJedi = luke['jedi'];

// tốt
const isJedi = luke.jedi;
```

12.2 Sử dụng ký pháp ngoặc `[]` để truy cập thuộc tính với một biến. </br>
    Ví dụ: </br>

```javascript
const luke = {
  jedi: true,
  age: 28,
};

function getProp(prop) {
  return luke[prop];
}

const isJedi = getProp('jedi');
```

**<span id="Variables_link">13. Variables</span></br>**
13.1 Luôn sử dụng `const` hoặc `let` để khai báo biến. Không làm như vậy sẽ dẫn đến các biến toàn cục. Chúng ta muốn tránh việc làm ô nhiễm không gian tên toàn cục. Đội trưởng Hành tinh đã cảnh báo chúng ta. eslint: `no-undef` `prefer-const` </br>
    Ví dụ: </br>

```javascript
// không tốt
superPower = new SuperPower();

// tốt
const superPower = new SuperPower();
```

13.6 Tránh việc sử dụng các phép tăng và giảm một ngôi (`++`, `--`). eslint `no-plusplus` </br>
    Ví dụ: </br>

```javascript
// không tốt

const array = [1, 2, 3];
let num = 1;
num++;
--num;

let sum = 0;
let truthyCount = 0;
for (let i = 0; i < array.length; i++) {
  let value = array[i];
  sum += value;
  if (value) {
    truthyCount++;
  }
}

// tốt

const array = [1, 2, 3];
let num = 1;
num += 1;
num -= 1;

const sum = array.reduce((a, b) => a + b, 0);
const truthyCount = array.filter(Boolean).length;
```

13.7 Tránh các dấu ngắt dòng trước và sau `=` trong một phép gán. Nếu phép gán của bạn vi phạm `max-len`, hãy đặt giá trị trong ngoặc tròn. eslint `operator-linebreak`. </br>
    Ví dụ: </br>

```javascript
// không tốt
const foo =
  superLongLongLongLongLongLongLongLongFunctionName();

// không tốt
const foo
  = 'một chuỗi rất rất rất rất rất rất rất rất rất rất là dài';

// tốt
const foo = (
  superLongLongLongLongLongLongLongLongFunctionName()
);

// tốt
const foo = 'một chuỗi rất rất rất rất rất rất rất rất rất rất là dài';
```

**<span id="Comparison_Operators_&_Equality_link">15. Comparison Operators & Equality</span></br>**
15.1 Sử dụng `===` và `!==` thay vì `==` và `!=`. eslint: `eqeqeq` </br>

15.6 Các toán tử ba ngôi không nên được đặt trong ngoặc và thường được viết trên một dòng riêng. eslint: `no-nested-ternary` </br>
    Ví dụ: </br>

```javascript
// không tốt
const foo = maybe1 > maybe2
  ? "hi hi"
  : value1 > value2 ? "hi hi" : null;

// chia thành hai biểu thức ba ngôi riêng biệt
// là tốt nhất
const maybeNull = value1 > value2 ? 'hi hi' : null;
const foo = maybe1 > maybe2 ? 'hi hi' : maybeNull;
```

15.7 Tránh các câu lệnh ba ngôi không đáng có. eslint: `no-unneeded-ternary` </br>
    Ví dụ: </br>

```javascript
// không tốt
const foo = a ? a : b;
const bar = c ? true : false;
const baz = c ? false : true;

// tốt
const foo = a || b;
const bar = !!c;
const baz = !c;
```

15.8 Khi kết hợp các toán tử, nhớ đóng chúng trong ngoặc. Ngoại lệ duy nhất là các toán tử tiêu chuẩn: `+`, `-` và `**` vì chúng có thứ tự ưu tiên mà ai ai cũng hiểu. Chúng tôi khuyến khích việc sử dụng đóng ngoặc cho `/` và `*` vì thứ tự ưu tiên của chúng có thể bị nhầm lẫn khi chúng được sử dụng gần nhau. eslint: `no-mixed-operators` </br>
    Ví dụ: </br>

```javascript
// không tốt
const foo = a && b < 0 || c > 0 || d + 1 === 0;

// không tốt
const bar = a ** b - 5 % d;

// không tốt
// ai đó có thể bị rối và nghĩ nó là (a || b) && c
if (a || b && c) {
  return d;
}

// không tốt
const bar = a + b / c * d;

// tốt
const foo = (a && b < 0) || c > 0 || (d + 1 === 0);

// tốt
const bar = a ** b - (5 % d);

// tốt
if (a || (b && c)) {
  return d;
}

// tốt
const bar = a + (b / c) * d;
```

**<span id="Blocks_link">16. Blocks</span></br>**
16.1 Sử dụng các dấu ngoặc cho các khối nhiều dòng. eslint: `nonblock-statement-body-position` </br>
    Ví dụ: </br>

```javascript
// không tốt
if (test)
  return false;

// tốt
if (test) return false;

// tốt
if (test) {
  return false;
}

// không tốt
function foo() { return false; }

// tốt
function bar() {
  return false;
}
```

16.2 Nếu bạn đang sử dụng các khối nhiều dòng với `if` và `else`, đặt `else` trên cùng dòng với dấu đóng ngoặc của khối `if`. eslint: `brace-style` </br>
    Ví dụ: </br>

```javascript
// không tốt
if (test) {
  thing1();
  thing2();
}
else {
  thing3();
}

// tốt
if (test) {
  thing1();
  thing2();
} else {
  thing3();
}
```

16.3 Nếu một khối `if` luôn thực hiện lệnh `return`, những khối `else` tiếp theo là không cần thiết. Một lệnh return trong một khối `else if` theo sau một khối `if` mà có chứa return có thể được tách thành nhiều khối `if`. eslint: `no-else-return` </br>
    Ví dụ: </br>

```javascript
// không tốt
function foo() {
  if (x) {
    return x;
  } else {
    return y;
  }
}

// không tốt
function cats() {
  if (x) {
    return x;
  } else if (y) {
    return y;
  }
}

// không tốt
function dogs() {
  if (x) {
    return x;
  } else {
    if (y) {
      return y;
    }
  }
}

// tốt
function foo() {
  if (x) {
    return x;
  }

  return y;
}

// tốt
function cats() {
  if (x) {
    return x;
  }

  if (y) {
    return y;
  }
}

// tốt
function dogs(x) {
  if (x) {
    if (z) {
      return y;
    }
  } else {
    return z;
  }
}
```

**<span id="Control_Statements_link">17. Control Statements</span></br>**
17.1 Nếu trong trường hợp lệnh điều khiển (`if`, `while`, v.v.) của bạn trở lên quá dài và vượt quá giới hạn độ dài dòng, mỗi (nhóm) điều kiện có thể được đặt ở một dòng mới. Toán tử lô-gíc nên được đặt ở đầu dòng. </br>
    Ví dụ: </br>

```javascript
// không tốt
if ((foo === 123 || bar === 'abc') && doesItLookGoodWhenItBecomesThatLong() && isThisReallyHappening()) {
  thing1();
}

// không tốt
if (foo === 123 &&
  bar === 'abc') {
  thing1();
}

// không tốt
if (foo === 123
  && bar === 'abc') {
  thing1();
}

// không tốt
if (
  foo === 123 &&
  bar === 'abc'
) {
  thing1();
}

// tốt
if (
  foo === 123
  && bar === 'abc'
) {
  thing1();
}

// tốt
if (
  (foo === 123 || bar === 'abc')
  && doesItLookGoodWhenItBecomesThatLong()
  && isThisReallyHappening()
) {
  thing1();
}

// tốt
if (foo === 123 && bar === 'abc') {
  thing1();
}
```

17.2 Không sử dụng toán tử lựa chọn thay cho các câu lệnh điều khiển. </br>
    Ví dụ: </br>

```javascript
// không tốt
!isRunning && startRunning();

// tốt
if (!isRunning) {
  startRunning();
}
```

**<span id="Comments_link">18. Comments</span></br>**
18.1 Sử dụng `/** ... */` cho các chú thích nhiều dòng. </br>
    Ví dụ: </br>

```javascript
// không tốt
// make() trả về một phần tử
// dựa trên tag được truyền vào
//
// @param {String} tag
// @return {Element} element
function make(tag) {

  // ...

  return element;
}

// tốt
/**
 * make() trả về một phần tử
 * dựa trên tag được truyền vào
 */
function make(tag) {

  // ...

  return element;
}
```

18.2 Sử dụng `//` cho các chú thích một dòng. Đặt các chú thích một dòng ở một dòng riêng, bên trên chủ đề của chú thích. Để một dòng trống trước chú thích trừ khi chú thích là dòng đầu tiên của một khối. </br>
    Ví dụ: </br>

```javascript
// không tốt
const active = true;  // là thẻ hiện tại

// tốt
// là thẻ hiện tại
const active = true;

// không tốt
function getType() {
  console.log('đang lấy loại...');
  // đặt loại mặc định là 'không phân loại'
  const type = this.type || 'không phân loại';

  return type;
}

// tốt
function getType() {
  console.log('đang lấy loại...');

  // đặt loại mặc định là 'không phân loại'
  const type = this.type || 'không phân loại';

  return type;
}

// như này cũng tốt
function getType() {
  // đặt loại mặc định là 'không phân loại'
  const type = this.type || 'không phân loại';

  return type;
}
```

18.3 Bắt đầu tất cả các chú thích bằng một dấu cách để dễ đọc hơn. eslint: `spaced-comment` </br>
    Ví dụ: </br>

```javascript
// không tốt
//là thẻ hiện tại
const active = true;

// tốt
// là thẻ hiện tại
const active = true;

// không tốt
/**
 *make() trả về một phần tử
 *dựa trên tag được truyền vào
 */
function make(tag) {

  // ...

  return element;
}

// tốt
/**
 * make() trả về một phần tử
 * dựa trên tag được truyền vào
 */
function make(tag) {

  // ...

  return element;
}
```

18.4 Thêm `FIXME` hoặc `TODO` vào đầu chú thích giúp các nhà phát triển dễ dàng biết được rằng bạn đang chỉ ra một vấn đề cần được xem lại, hoặc bạn đang đề xuất cách giải quyết cho vấn đề nên mà được áp dụng. Các hành động có thể như `FIXME: -- cần xem xét về thứ này` hoặc `TODO: -- cần áp dụng`. 
</br>

18.5 Sử dụng `// FIXME`: để chú giải các vấn đề.</br>
    Ví dụ: </br>

```javascript
class Calculator extends Abacus {
  constructor() {
    super();

    // FIXME: không nên dùng biến toàn cục ở đây
    total = 0;
  }
}
```

18.6 Sử dụng `// TODO`: để chú giải các cách giải quyết cho các vấn đề. </br>
    Ví dụ: </br>

```javascript
class Calculator extends Abacus {
  constructor() {
    super();

    // TODO: giá trị của total nên được chuyển thành tham số
    this.total = 0;
  }
}
```

**<span id="Whitespace_link">19. Whitespace</span></br>**
19.1 Sử dụng các tab ngắn (dấu cách) đặt về 2 dấu cách. eslint: `indent` </br>
    Ví dụ: </br>

```javascript
// không tốt
function foo() {
∙∙∙∙let name;
}

// không tốt
function bar() {
∙let name;
}

// tốt
function baz() {
∙∙let name;
}
```

19.2 Đặt 1 cách trước dấu mở ngoặc. eslint: `space-before-blocks` </br>
    Ví dụ: </br>

```javascript
// không tốt
function test(){
  console.log('ví dụ');
}

// tốt
function test() {
  console.log('ví dụ');
}

// không tốt
dog.set('attr',{
  age: '1 năm',
  breed: 'Chó núi Bern',
});

// tốt
dog.set('attr', {
  age: '1 năm',
  breed: 'Chó núi Bern',
});
```

19.7 Để một dòng trống sau mỗi khối và trước câu lệnh tiếp theo. </br>
    Ví dụ: </br>

```javascript
// không tốt
if (foo) {
  return bar;
}
return baz;

// tốt
if (foo) {
  return bar;
}

return baz;

// không tốt
const obj = {
  foo() {
  },
  bar() {
  },
};
return obj;

// tốt
const obj = {
  foo() {
  },

  bar() {
  },
};

return obj;

// không tốt
const arr = [
  function foo() {
  },
  function bar() {
  },
];
return arr;

// tốt
const arr = [
  function foo() {
  },

  function bar() {
  },
];

return arr;
```

19.8 Không kê các khối với các dòng trống. eslint: `padded-blocks` </br>
    Ví dụ: </br>

```javascript
// không tốt
function bar() {

  console.log(foo);

}

// không tốt
if (baz) {

  console.log(qux);
} else {
  console.log(foo);

}

// không tốt
class Foo {

  constructor(bar) {
    this.bar = bar;
  }
}

// tốt
function bar() {
  console.log(foo);
}

// tốt
if (baz) {
  console.log(qux);
} else {
  console.log(foo);
}
```

19.10 Không thêm các dấu cách trong dấu ngoặc tròn. eslint: `space-in-parens` </br>
    Ví dụ: </br>

```javascript
// không tốt
function bar( foo ) {
  return foo;
}

// tốt
function bar(foo) {
  return foo;
}

// không tốt
if ( foo ) {
  console.log(foo);
}

// tốt
if (foo) {
  console.log(foo);
}
```

**<span id="Commas_link">20. Commas</span></br>**
20.1 Các `dấu phẩy` ở đầu: Đừng! eslint: `comma-style` </br>
    Ví dụ: </br>

```javascript
// không tốt
const story = [
    once
  , upon
  , aTime
];

// tốt
const story = [
  once,
  upon,
  aTime,
];

// không tốt
const hero = {
    firstName: 'Ada'
  , lastName: 'Lovelace'
  , birthYear: 1815
  , superPower: 'máy tính'
};

// tốt
const hero = {
  firstName: 'Ada',
  lastName: 'Lovelace',
  birthYear: 1815,
  superPower: 'máy tính',
};
```

20.2 Thêm một `dấu phẩy` ở cuối: Đúng đó! eslint: `comma-dangle` </br>
    Ví dụ: </br>

```javascript
// không tốt - so sánh git khi không có dấu phẩy ở cuối
const hero = {
     firstName: 'Florence',
-    lastName: 'Nightingale'
+    lastName: 'Nightingale',
+    inventorOf: ['coxcomb chart', 'modern nursing']
};

// tốt - so sánh git khi có các dấu phẩy ở cuối
const hero = {
     firstName: 'Florence',
     lastName: 'Nightingale',
+    inventorOf: ['coxcomb chart', 'modern nursing'],
};
```

```javascript
// không tốt
const hero = {
  firstName: 'Dana',
  lastName: 'Scully'
};

const heroes = [
  'Batman',
  'Superman'
];

// tốt
const hero = {
  firstName: 'Dana',
  lastName: 'Scully',
};

const heroes = [
  'Batman',
  'Superman',
];

// không tốt
function createHero(
  firstName,
  lastName,
  inventorOf
) {
  // không làm gì cả
}

// tốt
function createHero(
  firstName,
  lastName,
  inventorOf,
) {
  // không làm gì cả
}

// tốt (lưu ý là không được đặt dấu phẩy sau phần từ "còn-lại")
function createHero(
  firstName,
  lastName,
  inventorOf,
  ...heroArgs
) {
  // không làm gì cả
}

// không tốt
createHero(
  firstName,
  lastName,
  inventorOf
);

// tốt
createHero(
  firstName,
  lastName,
  inventorOf,
);

// tốt (lưu ý là không được đặt dấu phẩy sau phần từ "còn-lại")
createHero(
  firstName,
  lastName,
  inventorOf,
  ...heroArgs
);
```

**<span id="Semicolons_link">21. Semicolons</span></br>**
21.1 Dĩ nhiên. eslint: `semi` </br>
    Ví dụ: </br>

```javascript
// không tốt - ném ra một ngoại lệ
const luke = {}
const leia = {}
[luke, leia].forEach((jedi) => jedi.father = 'vader')

// không tốt - ngém ra một ngoại lệ
const reaction = "Không! Không thể nào!"
(async function meanwhileOnTheFalcon() {
  // xử lý `leia`, `lando`, `chewie`, `r2`, `c3p0`
  // ...
}())

// không tốt - trả về `undefined` thay vì giá trị ở dòng tiếp theo - điều luôn xảy ra khi `return` nằm một mình một dòng, do Quy tắc thêm dấu chấm phẩy tự động!
function foo() {
  return
    'search your feelings, you know it to be foo'
}

// tốt
const luke = {};
const leia = {};
[luke, leia].forEach((jedi) => {
  jedi.father = 'vader';
});

// tốt
const reaction = "Không! Không thể nào!";
(async function meanwhileOnTheFalcon() {
  // xử lý `leia`, `lando`, `chewie`, `r2`, `c3p0`
  // ...
}());

// tốt
function foo() {
  return 'search your feelings, you know it to be foo';
}
```

**<span id="TypeCasting_&_Coercion_link">22. Type Casting & Coercion</span></br>**
22.1 Thực hiện ép kiểu ở đầu mỗi câu lệnh. </br>

22.2 Đối với các chuỗi: eslint: `no-new-wrappers` </br>
    Ví dụ: </br>

```javascript
// => this.reviewScore = 9;

// không tốt
const totalScore = new String(this.reviewScore); // typeof totalScore là "object", không phải "string"

// không tốt
const totalScore = this.reviewScore + ''; // cái này gọi this.reviewScore.valueOf()

// không tốt
const totalScore = this.reviewScore.toString(); // không chắc chắn sẽ thu được một chuỗi

// tốt
const totalScore = String(this.reviewScore);
```

22.3 Đối với các số: Sử dụng Number để ép kiểu và parseInt luôn phải được dùng với một cơ số. eslint: `radix` `no-new-wrappers` </br>
    Ví dụ: </br>

```javascript
const inputValue = '4';

// không tốt
const val = new Number(inputValue);

// không tốt
const val = +inputValue;

// không tốt
const val = inputValue >> 0;

// không tốt
const val = parseInt(inputValue);

// tốt
const val = Number(inputValue);

// tốt
const val = parseInt(inputValue, 10);
```

22.6 Đối với các boolean: eslint: `no-new-wrappers` </br>
    Ví dụ: </br>

```javascript
const age = 0;

// không tốt
const hasAge = new Boolean(age);

// tốt
const hasAge = Boolean(age);

// tốt nhất
const hasAge = !!age;
```

**<span id="Naming_Conventions_link">23. Naming Conventions</span></br>**
23.1 Tránh sử dụng các tên chỉ có một chữ cái. Hãy đặt những cái tên thật ý nghĩa. eslint: `id-length` </br>
    Ví dụ: </br>

```javascript
// không tốt
function q() {
  // ...
}

// tốt
function query() {
  // ...
}
```

23.2 Sử dụng `camelCase` khi đặt tên các đối tượng, các hàm và các thực thể. eslint: `camelcase` </br>
    Ví dụ: </br>

```javascript
// không tốt
const OBJEcttsssss = {};
const this_is_my_object = {};
function c() {}

// tốt
const thisIsMyObject = {};
function thisIsMyFunction() {}
```

23.3 Sử dụng `PascalCase` chỉ khi đặt tên các hàm tạo hay các lớp. eslint: `new-cap` </br>
    Ví dụ: </br>

```javascript
// không tốt
function user(options) {
  this.name = options.name;
}

const bad = new user({
  name: 'đừnggg',
});

// tốt
class User {
  constructor(options) {
    this.name = options.name;
  }
}

const good = new User({
  name: 'đúng nè',
});
```

23.4 Không sử dụng các dấu gạch dưới ở đằng trước hoặc đằng sau. eslint: `no-underscore-dangle` </br>
    Ví dụ: </br>

```javascript
// không tốt
this.__firstName__ = 'Panda';
this.firstName_ = 'Panda';
this._firstName = 'Panda';

// tốt
this.firstName = 'Panda';

// tốt, đối với các môi trường hỗ trợ WeakMap
// xem https://kangax.github.io/compat-table/es6/#test-WeakMap
const firstNames = new WeakMap();
firstNames.set(this, 'Panda');
```

23.5 Đừng lưu các tham chiếu đến `this`. Hãy sử dụng hàm mũi tên hoặc `Function#bind`. </br>
    Ví dụ: </br

```javascript
// không tốt
function foo() {
  const self = this;
  return function () {
    console.log(self);
  };
}

// không tốt
function foo() {
  const that = this;
  return function () {
    console.log(that);
  };
}

// tốt
function foo() {
  return () => {
    console.log(this);
  };
}
```

23.6 Phần tên của một tên tệp nên giống với địa chỉ xuất mặc định của tệp đó. </br>
    Ví dụ: </br>

```javascript
// file 1 contents
class CheckBox {
  // ...
}
export default CheckBox;

// file 2 contents
export default function fortyTwo() { return 42; }

// file 3 contents
export default function insideDirectory() {}

// in some other file
// không tốt
import CheckBox from './checkBox'; // nhập PascalCase, tên camelCase
import FortyTwo from './FortyTwo'; // nhập/tên PascalCase, xuất camelCase
import InsideDirectory from './InsideDirectory'; // nhập/tên PascalCase, xuất camelCase

// không tốt
import CheckBox from './check_box'; // nhập/xuất PascalCase, tên snake_case
import forty_two from './forty_two'; // nhập/tên snake_case, xuất camelCase
import inside_directory from './inside_directory'; // nhập snake_case, xuất camelCase
import index from './inside_directory/index'; // ghi tên tệp index
import insideDirectory from './insideDirectory/index'; // ghi tên tệp index

// tốt
import CheckBox from './CheckBox'; // xuất/nhập/tên PascalCase
import fortyTwo from './fortyTwo'; // xuất/nhập/tên camelCase
import insideDirectory from './insideDirectory'; // xuất/nhập/tên camelCase; ngầm định "index"
// ^ hỗ trợ cả insideDirectory.js và insideDirectory/index.js
```

23.7 Sử dụng `camelCase` khi xuất mặc định một hàm. Tên tệp nên trùng với tên hàm. </br>
    Ví dụ: </br>

```javascript
function makeStyleGuide() {
  // ...
}

export default makeStyleGuide;
```

23.8 Sử dụng `PascalCase` khi xuất mặc định một hàm tạo / lớp / đối tượng độc nhật / một thư viện các hàm / đối tượng trần. </br>
    Ví dụ: </br>

```javascript
const AirbnbStyleGuide = {
  es6: {
  },
};

export default AirbnbStyleGuide;
```

23.9 Các từ viết tắt nên được viết hoa hoặc viết thường toàn bộ.
    Ví dụ: </br>

```javascript
// không tốt
import SmsContainer from './containers/SmsContainer';

// không tốt
const HttpRequests = [
  // ...
];

// tốt
import SMSContainer from './containers/SMSContainer';

// tốt
const HTTPRequests = [
  // ...
];

// như này cũng tốt
const httpRequests = [
  // ...
];

// tốt nhất
import TextMessageContainer from './containers/TextMessageContainer';

// tốt nhất
const requests = [
  // ...
];
```

23.10 Bạn có chọn viết hoa một hằng chỉ khi hằng đó (1) được xuất, và (2) một lập trình viên có thể tin tưởng rằng nó (và các thuộc tính của nó) là bất biến.</br>

-Thế còn các `const`? - Điều này là không cần thiết, vì việc viết hoa không nên được sử dụng cho các hằng ở trong cùng một tệp. Nó chỉ nên dùng cho các hằng được xuất.</br>
-Thế còn một đối tượng được xuất thì sao? - Chỉ viết hoa ở hàng cao nhất của đối tượng xuất (kiểu như: `EXPORTED_OBJECT.key)` và đảm bảo rằng những thuộc tính của nó không thay đổi.</br>

```javascript
// không tốt
const PRIVATE_VARIABLE = 'không nên viết hoa bừa bãi các biến trong một tệp';

// không tốt
export const THING_TO_BE_CHANGED = 'rõ ràng không nên viết hoa';

// không tốt
export let REASSIGNABLE_VARIABLE = 'đừng có sử dụng let với tên viết hóa';

// ---

// được cho phép, nhưng không không rõ về mặt ngữ nghĩa
export const apiKey = 'SOMEKEY';

// tốt hơn hầu hết các trường hợp khác
export const API_KEY = 'SOMEKEY';

// ---

// không tốt - viết hoa không cần thiết chẳng cung cấp gì trị gì về mặt ngữ nghĩa
export const MAPPING = {
  KEY: 'giá trị'
};

// tốt
export const MAPPING = {
  key: 'giá trị'
};
```


