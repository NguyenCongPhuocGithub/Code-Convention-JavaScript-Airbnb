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
    

## **NỘI DUNG**
### **<span id="I_link">I. Thứ tự import của một page hoặc component</span>**
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
