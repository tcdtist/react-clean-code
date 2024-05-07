# Hướng dẫn Viết Code Sạch React JS

![Hướng dẫn Viết Code Sạch React JS](https://javascript.withcodeexample.com/React_JS_Clean_Code_Guide_l3cv4e_1342968072725724175.png)

React.js đã làm cách mạng hóa phát triển giao diện người dùng bằng cách cung cấp một cách mạnh mẽ và hiệu quả để xây dựng giao diện người dùng. Tuy nhiên, khi ứng dụng React của bạn ngày càng phức tạp, việc duy trì code sạch, dễ đọc và dễ bảo trì trở nên cực kỳ quan trọng. Trong hướng dẫn này, chúng ta sẽ khám phá các phương pháp hay nhất để viết code React.js sạch không chỉ hoạt động tốt mà còn dễ hiểu và bảo trì.

## 1. Component Structure and Organization - Cấu trúc và tổ chức thành phần

Một hệ thống phân cấp thành phần được cấu trúc tốt sẽ đơn giản hóa việc điều hướng và hỗ trợ trong việc hiểu luồng của ứng dụng của bạn. Hãy tuân theo những hướng dẫn này:

- **Nguyên tắc Trách nhiệm Đơn lẻ (SRP):** Giữ cho các thành phần của bạn tập trung vào một trách nhiệm duy nhất. Nếu một thành phần trở nên quá lớn, hãy xem xét việc chia nhỏ nó thành các phần nhỏ hơn, dễ quản lý hơn.

- **Thành phần Container và Presentation:** Phân loại các thành phần của bạn thành hai hạng mục: các thành phần container (chịu trách nhiệm về dữ liệu và logic) và các thành phần presentation (tập trung vào việc hiển thị giao diện người dùng). Sự phân tách này làm tăng độ rõ ràng và khả năng tái sử dụng của code.

- **Cấu trúc Thư mục:** Tổ chức các thành phần của bạn trong một cấu trúc thư mục hợp lý. Nhóm các thành phần liên quan lại với nhau và xem xét sử dụng các thư mục như `components`, `containers`, và `utils` để giữ mọi thứ được tổ chức.

## 2. Descriptive Naming - Đặt tên mô tả

Việc đặt tên mô tả trong React đề cập đến việc chọn các tên có ý nghĩa và tự giải thích cho các biến, hàm, thành phần, tệp và các yếu tố khác trong cơ sở code của ứng dụng React của bạn. Mục tiêu của việc đặt tên mô tả là làm cho mục đích và chức năng của mỗi yếu tố ngay lập tức trở nên rõ ràng đối với các nhà phát triển khác đọc hoặc hợp tác trên code. Thực hành này làm tăng khả năng đọc, bảo trì và hiểu biết chung về ứng dụng.

### Hướng dẫn cho Việc Đặt Tên Mô Tả trong React

- **Thành phần:** Chọn tên thành phần mô tả chính xác mục đích hoặc vai trò của chúng trong ứng dụng. Sử dụng danh từ hoặc cụm danh từ mô tả rõ ràng những gì thành phần làm.

  ```jsx
  // Tốt: Tên thành phần mô tả
  <UserProfile />

  // Tránh: Tên thành phần mơ hồ hoặc không rõ ràng
  <Component1 />
  ```

- **Biến và Hàm:** Chọn tên biến và hàm mô tả mục đích hoặc dữ liệu mà chúng giữ/manipulate. Sử dụng camelCase cho biến và hàm.

  ```jsx
  // Tốt: Tên biến và hàm mô tả
  const userDisplayName = "John Doe";

  function calculateTotalPrice(items) {
    // ...
  }

  // Tránh: Tên không rõ ràng hoặc viết tắt
  const uName = "John Doe";

  function calc(items) {
    // ...
  }
  ```

- **Tệp và Thư mục:** Đặt tên các tệp và thư mục của bạn một cách phản ánh nội dung của chúng. Sử dụng chữ cái thường, dấu gạch ngang và dấu gạch dưới để cải thiện khả năng đọc.

  ```plaintext
  // Tốt: Tên tệp và thư mục mô tả
  UserProfile.js
  user-profile/
  ```

- **Props và State:** Khi truyền props hoặc định nghĩa trạng thái thành phần, đặt tên cho chúng chỉ ra mục đích và dữ liệu mà chúng giữ.

  ```jsx
  // Tốt: Tên props và trạng thái mô tả
  <ProfileCard name={user.name} />;

  class UserProfile extends React.Component {
    state = {
      isLoading: true,
      userData: null,
    };
    // ...
  }

  // Tránh: Tên chung chung hoặc không rõ ràng
  <ProfileCard n={user.name} />;

  class UserProfile extends React.Component {
    state = {
      flag: true,
      data: null,
    };
    // ...
  }
  ```

- **Bộ xử lý sự kiện:** Khi định nghĩa các hàm xử lý sự kiện, sử dụng các tên mô tả hành động mà chúng thực hiện hoặc sự kiện mà chúng xử lý.

```jsx
// Tốt: Tên bộ xử lý sự kiện mô tả
function handleButtonClick() {
  // ...
}

// Tránh: Tên bộ xử lý sự kiện chung chung
function handleClick() {
  // ...
}
```

- **Chú thích:** Nếu cần thiết, hãy sử dụng chú thích để cung cấp bối cảnh hoặc giải thích bổ sung cho code phức tạp. Tuy nhiên, ưu tiên viết code tự giải thích mà không cần quá nhiều chú thích.

Việc đặt tên mô tả thúc đẩy giao tiếp rõ ràng và giúp các nhà phát triển tương lai (kể cả bạn trong tương lai) hiểu được mục đích và chức năng của các yếu tố khác nhau trong ứng dụng React của bạn. Khi đặt tên các yếu tố, hãy xem xét lợi ích lâu dài của việc có code dễ đọc, dễ bảo trì và dễ hợp tác.

## 3. Consistent Formatting - Định dạng Nhất quán

Định dạng nhất quán trong React liên quan đến việc tuân thủ một tập hợp các quy tắc và quy ước cho bố cục code, thụt lề, khoảng cách và các khía cạnh phong cách khác trên toàn bộ ứng dụng của bạn. Sự nhất quán trong định dạng cải thiện khả năng đọc code, khả năng bảo trì và sự hợp tác giữa các nhà phát triển.

### Hướng dẫn cho Định dạng Nhất quán trong React

- **Thụt lề:** Sử dụng thụt lề nhất quán cho mỗi cấp độ lồng nhau. Một lựa chọn phổ biến là sử dụng hai hoặc bốn khoảng trắng cho mỗi cấp độ. Chọn một kiểu và tuân theo nó trong suốt dự án.

  ```jsx
  // Ví dụ sử dụng thụt lề bốn khoảng trắng
  function MyComponent() {
    return (
      <div>
        <p>Hello, world!</p>
      </div>
    );
  }
  ```

- **Vị trí dấu ngoặc:** Đặt dấu ngoặc mở trên cùng một dòng với khối mà chúng được liên kết. Đây là một thực hành phổ biến trong JavaScript.

  ```jsx
  // Tốt: Dấu ngoặc mở trên cùng một dòng
  function MyComponent() {
    // ...
  }

  // Tránh: Dấu ngoặc mở trên một dòng mới
  function MyComponent() {
    // ...
  }
  ```

- **Khoảng trắng và Định dạng:** Sử dụng khoảng trắng nhất quán xung quanh các toán tử, bên trong các ký tự đối tượng và trước/sau dấu ngoặc. Thêm khoảng trắng sau dấu phẩy và dấu hai chấm.

  ```jsx
  // Tốt: Khoảng trắng nhất quán xung quanh các toán tử và đối tượng
  const user = { name: "John", age: 30 };

  // Tránh: Khoảng trắng không nhất quán
  // const user =  {   name :  "John"  ,   age:   30 };
  ```

- **Chiều dài Dòng:** Cố gắng giữ các dòng có độ dài hợp lý (thường là khoảng 80-100 ký tự) để cải thiện khả năng đọc code. Nếu một dòng quá dài, hãy xem xét chia nó thành nhiều dòng.

  ```jsx
  // Tốt: Ngắt dòng để giữ chiều dài dòng có thể quản lý được
  <MyComponent prop1={value1} prop2={value2} prop3={value3} />

  // Tránh: Dòng dài làm giảm khả năng đọc
  <MyComponent prop1={value1} prop2={value2} prop3={value3} prop4={value4} prop5={value5} />
  ```

- **Đặt tên Nhất quán:** Sử dụng các quy ước đặt tên nhất quán cho các biến, hàm, thành phần và các định danh khác. Chọn một kiểu đặt tên (camelCase, PascalCase, v.v.) và áp dụng nó một cách đồng nhất.

- **Chú thích:** Tuân theo các kiểu chú thích nhất quán. Sử dụng chú thích một dòng (`//`) cho các lời giải thích ngắn và chú thích nhiều dòng (`/* */`) cho các lời giải thích dài hơn hoặc chú thích khối.

- **Tổ chức Imports:** Giữ cho các lệnh import của bạn được tổ chức và nhóm một cách hợp lý. Bạn có thể sử dụng các công cụ như ESLint hoặc Prettier để tự động định dạng các lệnh import của bạn.

- **Canh lề Code:** Canh lề các khối code tương tự theo chiều dọc để tạo sự nhóm hợp lý và rõ ràng hơn về mặt hình ảnh.

  ```jsx
  // Tốt: Canh lề code để dễ đọc hơn
  const firstName = "John";
  const lastName = "Doe";

  // Tránh: Code không được canh lề
  //         const    firstName =    "John";
  // const lastName    =     "Doe";
  ```

- **Sử dụng Công cụ Định dạng Code:** Hãy xem xét sử dụng các công cụ định dạng code như Prettier để tự động áp dụng định dạng nhất quán trên toàn bộ cơ sở code của bạn. Những công cụ này có thể được tích hợp vào quy trình làm việc phát triển của bạn để đảm bảo rằng định dạng luôn nhất quán mà không cần nỗ lực thủ công.

Bằng cách duy trì các thực hành định dạng nhất quán trong suốt cơ sở code React của bạn, bạn làm cho các nhà phát triển dễ dàng hiểu và đóng góp vào code hơn, giảm thiểu rủi ro sai sót và nâng cao chất lượng code tổng thể.

## 4. Avoid Magic Numbers and Strings - Tránh Sử dụng Số và Chuỗi Ma Thuật

Trong lập trình, một "số ma thuật" là một giá trị số xuất hiện trực tiếp trong code mà không có bất kỳ giải thích nào. Tương tự, một "chuỗi ma thuật" là một giá trị chuỗi được sử dụng trực tiếp trong code mà không có ngữ cảnh. Cả hai điều này có thể làm cho code khó hiểu và khó bảo trì.

### Ví dụ

```jsx
// Thay vì
if (status === 2) { ... }

// Sử dụng hằng số
const STATUS_COMPLETED = 2;
if (status === STATUS_COMPLETED) { ... }
```

## 5. Destructuring - Phân rã

Phân rã là một tính năng trong ngôn ngữ lập trình cho phép bạn trích xuất các phần tử riêng lẻ từ các cấu trúc dữ liệu như mảng, đối tượng hoặc bộ và gán chúng cho các biến theo cách ngắn gọn và trực quan hơn. Nó đơn giản hóa quá trình trích xuất giá trị từ các cấu trúc dữ liệu phức tạp, làm cho code của bạn sạch hơn và dễ đọc hơn.

### Ví dụ

```jsx
// Thay vì
const username = user.name;
const age = user.age;

// Sử dụng phân rã
const { name: username, age } = user;
```

## 6. Avoid Nested Ternaries - Tránh Lồng Các Ternary

Một toán tử ba ngôi, thường được gọi đơn giản là "ternary", là một cách ngắn gọn để viết một biểu thức điều kiện. Nó cho phép bạn nhanh chóng đánh giá một điều kiện và trả về một trong hai giá trị dựa trên việc điều kiện đó có đúng hay không. Toán tử ba ngôi có dạng:

```jsx
condition ? expression_if_true : expression_if_false;
```

Mặc dù các toán tử ba ngôi có thể ngắn gọn, hãy tránh lồng chúng quá sâu, vì nó có thể làm cho code khó theo dõi. Thay vào đó, hãy xem xét sử dụng các câu lệnh if hoặc phân rã logic phức tạp thành các hàm riêng biệt.

## 7. Comments and Documentation - Chú thích và Tài liệu

Chú thích được sử dụng để cung cấp các giải thích, ghi chú hoặc ngữ cảnh trong code của bạn. Chúng không được thực thi bởi trình thông dịch JavaScript và không ảnh hưởng đến hành vi của code. Chú thích là thiết yếu để làm cho code của bạn dễ hiểu đối với các nhà phát triển khác, bao gồm cả bản thân bạn trong tương lai. Có hai loại chú thích trong JavaScript: chú thích một dòng và chú thích nhiều dòng.

Sử dụng chú thích để giải thích logic phức tạp, ý định hoặc quyết định trong code của bạn. Tuy nhiên, hãy cố gắng viết code tự giải thích mà không cần quá nhiều chú thích.

### Ví dụ

```jsx
// Hook đặt tiêu đề tài liệu dựa trên tham số đầu vào
function useDocumentTitle(title) {
  useEffect(() => {
    document.title = title; // Đặt tiêu đề trang web
  }, [title]);
}

// Thành phần này hiển thị hồ sơ người dùng và mong đợi một prop `user`
function UserProfile({ user }) {
  useDocumentTitle(user.name); // Sử dụng hook tùy chỉnh để thay đổi tiêu đề tài liệu

  return (
    <div className="user-profile">
      <h1>{user.name}</h1> {/* Hiển thị tên người dùng */}
      <p>{user.bio}</p> {/* Hiển thị tiểu sử người dùng */}
    </div>
  );
}
```

## 8. Reuse and Modularization - Tái sử dụng và Mô-đun hóa

Tái sử dụng code bằng cách tạo các thành phần và hàm tiện ích có thể tái sử dụng. Thực hành này giảm sự trùng lặp code và làm cho cơ sở code của bạn dễ bảo trì hơn.

### Ví dụ

```jsx
// Thành phần Nút có thể tái sử dụng
function Button({ onClick, children }) {
  return (
    <button onClick={onClick} className="custom-button">
      {children}
    </button>
  );
}

// Sử dụng trong các phần khác của ứng dụng
function App() {
  return (
    <div>
      <Button onClick={() => console.log("Clicked!")}>Nhấn vào đây!</Button>
    </div>
  );
}
```

## 9. State Management - Quản lý Trạng thái

Quản lý trạng thái trong React đề cập đến quá trình quản lý và kiểm soát dữ liệu xác định hành vi và hình thức hiển thị của một thành phần hoặc ứng dụng. Các thành phần React có thể có trạng thái nội bộ, là dữ liệu có thể thay đổi theo thời gian và kích hoạt việc tái hiển thị khi được cập nhật. Tuy nhiên, khi ứng dụng của bạn phát triển, việc quản lý trạng thái giữa các thành phần có thể trở nên phức tạp. Các giải pháp quản lý trạng thái giúp xử lý sự phức tạp này bằng cách cung cấp các cách thức có cấu trúc để quản lý, chia sẻ và cập nhật trạng thái.

### Giải pháp Quản lý Trạng thái cho React

1. **Trạng thái Thành phần Địa phương:** Đối với các thành phần đơn giản với tương tác hạn chế, việc quản lý trạng thái trong thành phần sử dụng hook `useState` hoặc các phương thức `this.state` và `this.setState` (đối với các thành phần dạng class) là đủ.

2. **API Context:** API Context là một giải pháp tích hợp sẵn để chia sẻ trạng thái giữa nhiều thành phần mà không cần phải truyền props qua các thành phần trung gian. Nó phù hợp cho các mức độ chia sẻ trạng thái vừa phải.

3. **Redux:** Redux là một thư viện quản lý trạng thái phổ biến cung cấp một kho lưu trữ trung tâm cho trạng thái ứng dụng. Nó đặc biệt hữu ích cho các ứng dụng phức tạp với lượng lớn trạng thái được chia sẻ hoặc tương tác thường xuyên giữa các thành phần.

4. **MobX:** MobX là một thư viện quản lý trạng thái khác nhằm đơn giản hóa quản lý trạng thái bằng cách sử dụng các đối tượng quan sát được. Nó phù hợp với các ứng dụng nơi một cách tiếp cận phản ứng với quản lý trạng thái được ưa chuộng.

5. **React Query:** React Query tập trung vào quản lý dữ liệu bất đồng bộ, chẳng hạn như tải và lưu vào bộ nhớ đệm các phản hồi API. Nó đặc biệt hữu ích cho việc quản lý dữ liệu từ xa và xử lý việc tải dữ liệu, lưu vào bộ nhớ đệm, đồng bộ hóa và hơn thế nữa.

6. **Apollo Client:** Nếu ứng dụng của bạn làm việc với các API GraphQL, Apollo Client cung cấp một giải pháp mạnh mẽ để quản lý dữ liệu, truy vấn và thay đổi. Nó cung cấp các công cụ cho việc lưu vào bộ nhớ đệm, chuẩn hóa dữ liệu và hỗ trợ đăng ký.

Chọn một giải pháp quản lý trạng thái dựa trên độ phức tạp của ứng dụng và các yêu cầu cụ thể của dự án của bạn. Bất kể giải pháp nào, các mục tiêu chính của quản lý trạng thái là giữ cho dữ liệu của ứng dụng của bạn nhất quán, dễ bảo trì và có thể truy cập được cho các thành phần cần nó trong khi giảm thiểu việc tái hiển thị không cần thiết.

### Ví dụ

```jsx
// Sử dụng API Context để quản lý và chia sẻ dữ liệu người dùng giữa các thành phần
const UserContext = createContext();

function UserProvider({ children }) {
  const [user, setUser] = useState(null);

  const login = (username) => {
    setUser({ name: username });
  };

  return (
    <UserContext.Provider value={{ user, login }}>
      {children}
    </UserContext.Provider>
  );
}

function UserProfile() {
  const { user } = useContext(UserContext);

  return user ? (
    <div>Xin chào, {user.name}</div>
  ) : (
    <div>Vui lòng đăng nhập</div>
  );
}

function App() {
  return (
    <UserProvider>
      <UserProfile />
    </UserProvider>
  );
}
```

## 10. Error Handling - Xử lý Lỗi

Xử lý lỗi trong React liên quan đến việc quản lý và phản hồi đối với các lỗi không mong đợi có thể xảy ra trong quá trình thực thi ứng dụng của bạn. Việc xử lý lỗi đúng cách làm tăng trải nghiệm người dùng bằng cách cung cấp phản hồi có ý nghĩa và ngăn ngừa sự cố. Dưới đây là một ghi chú ngắn về việc xử lý lỗi trong React:

### Ranh giới Lỗi

React cung cấp một khái niệm gọi là "ranh giới lỗi" để xử lý một cách nhẹ nhàng các lỗi xảy ra trong các thành phần. Ranh giới lỗi là một thành phần React bắt các lỗi JavaScript ở bất cứ đâu trong cây thành phần con của nó và hiển thị một giao diện người dùng dự phòng thay vì làm sập toàn bộ ứng dụng. Bạn có thể định nghĩa các ranh giới lỗi sử dụng phương thức vòng đời `componentDidCatch`.

```jsx
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  componentDidCatch(error, errorInfo) {
    this.setState({ hasError: true });
    // Ghi lại lỗi hoặc gửi báo cáo lỗi
    console.error(error, errorInfo);
  }

  render() {
    if (this.state.hasError) {
      return <h1>Có điều gì đó không ổn.</h1>;
    }
    return this.props.children;
  }
}

// Cách sử dụng
<ErrorBoundary>
  <MyComponent />
</ErrorBoundary>;
```

### Khối Try-Catch

Để xử lý các lỗi trong các phương thức thành phần, bạn có thể sử dụng các khối try và catch tiêu chuẩn của JavaScript. Điều này đặc biệt hữu ích cho các hoạt động bất đồng bộ như các cuộc gọi API.

```jsx
class MyComponent extends React.Component {
  async fetchData() {
    try {
      const response = await fetch("https://api.example.com/data");
      const data = await response.json();
      // Xử lý dữ liệu
    } catch (error) {
      console.error("Lỗi khi tải dữ liệu:", error);
      // Hiển thị thông báo lỗi cho người dùng
    }
  }

  render() {
    // ...
  }
}
```

### Hiển thị Thông báo Lỗi

Khi xảy ra lỗi, điều quan trọng là phải hiển thị thông báo lỗi rõ ràng và thân thiện với người dùng để giúp người dùng hiểu điều gì đã xảy ra. Bạn có thể hiển thị thông báo lỗi trong các thành phần của mình dựa trên trạng thái xử lý lỗi.

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { error: null };
  }

  async fetchData() {
    try {
      // ...
    } catch (error) {
      console.error("Lỗi khi tải dữ liệu:", error);
      this.setState({ error: "Đã xảy ra lỗi trong quá trình tải dữ liệu." });
    }
  }

  render() {
    const { error } = this.state;

    return (
      <div>
        {error ? <p>{error}</p> : <p>Dữ liệu đã được tải thành công!</p>}
        {/* ... */}
      </div>
    );
  }
}
```

Bằng cách triển khai các ranh giới lỗi, sử dụng các khối try-catch và cung cấp thông báo lỗi thông tin, bạn có thể tạo ra một ứng dụng React mạnh mẽ và thân thiện với người dùng hơn, có khả năng xử lý các lỗi không mong đợi một cách nhẹ nhàng và cải thiện sự hài lòng của người dùng.

## 11. Testing - Kiểm thử

Kiểm thử là một khía cạnh quan trọng của phát triển phần mềm, đảm bảo rằng các ứng dụng React của bạn hoạt động như mong đợi và vẫn đáng tin cậy ngay cả khi chúng phát triển. Kiểm thử đúng cách giúp phát hiện lỗi sớm, cung cấp sự tự tin trong các thay đổi code và đóng góp vào sự ổn định tổng thể của ứng dụng. Dưới đây là một ghi chú ngắn về kiểm thử trong React:

### Các Loại Kiểm thử trong React

- **Kiểm thử Đơn vị:** Điều này liên quan đến việc kiểm thử các thành phần hoặc chức năng riêng lẻ một cách độc lập để xác minh rằng chúng hoạt động như dự định. Các thư viện phổ biến để kiểm thử đơn vị các thành phần React bao gồm Jest và React Testing Library.

- **Kiểm thử Tích hợp:** Các bài kiểm thử tích hợp tập trung vào các tương tác giữa các thành phần khác nhau, đảm bảo chúng hoạt động chính xác cùng nhau.

Những bài kiểm thử này giúp xác định các vấn đề có thể phát sinh khi các thành phần được kết hợp.

- **Kiểm thử Đầu cuối (E2E):** Các bài kiểm thử E2E mô phỏng tương tác người dùng với toàn bộ ứng dụng. Các công cụ như Cypress và Selenium được sử dụng để kiểm tra các luồng và tương tác của người dùng.

### Lợi ích của Kiểm thử trong React

- **Phòng ngừa Lỗi:** Việc viết các bài kiểm thử giúp xác định và giải quyết các lỗi trước khi chúng đạt đến sản xuất, giảm thiểu khả năng xảy ra các vấn đề không mong muốn đối với người dùng.

- **Tin cậy vào Code:** Code được kiểm thử tốt cho bạn sự tự tin rằng các thay đổi của bạn sẽ không làm hỏng chức năng hiện có khi bạn tái cấu trúc hoặc thêm các tính năng mới.

- **Tài liệu:** Các bài kiểm thử phục vụ như tài liệu cho cách code của bạn được dự định hoạt động. Chúng cung cấp cái nhìn sâu sắc về hành vi mong đợi của các thành phần.

### Các Thư viện Kiểm thử trong React

- **Jest:** Một khung kiểm thử phổ biến cho các ứng dụng JavaScript, Jest được biết đến với sự dễ sử dụng, các phép xác nhận tích hợp và khả năng chạy các bài kiểm thử song song.

- **React Testing Library:** Thư viện này tập trung vào việc kiểm thử các thành phần theo cách người dùng tương tác với chúng. Nó khuyến khích viết các bài kiểm thử giống như cách người dùng sẽ tương tác với ứng dụng của bạn.

- **Cypress:** Một khung kiểm thử E2E, Cypress cho phép bạn viết các bài kiểm thử chạy trong một trình duyệt thực. Nó cung cấp một cách trực quan và tương tác để kiểm thử ứng dụng của bạn.

### Kiểm thử Mẫu trong React sử dụng Jest và React Testing Library

```jsx
// MyComponent.js
import React from "react";

function MyComponent(props) {
  const { value } = props;
  return <div>{value}</div>;
}

export default MyComponent;
```

```jsx
// MyComponent.test.js
import React from "react";
import { render } from "@testing-library/react";
import MyComponent from "./MyComponent";

test("hiển thị giá trị prop một cách chính xác", () => {
  const { getByText } = render(<MyComponent value="Giá trị Kiểm thử" />);
  const valueElement = getByText("Giá trị Kiểm thử");
  expect(valueElement).toBeInTheDocument();
});
```

Trong ví dụ này, một bài kiểm thử đơn giản kiểm tra xem giá trị prop được truyền cho MyComponent có được hiển thị chính xác hay không.

## 12. Code Reviews - Đánh giá Code

Đánh giá code trong React, như trong bất kỳ quy trình phát triển phần mềm nào, bao gồm việc xem xét cộng tác các thay đổi code bởi các thành viên trong nhóm. Thực hành này giúp đảm bảo chất lượng, độ chính xác và khả năng bảo trì của cơ sở code. Dưới đây là một ghi chú ngắn về đánh giá code trong React:

### Mục đích của Đánh giá Code

- **Đảm bảo Chất lượng:** Đánh giá code giúp phát hiện lỗi, sai sót logic và các vấn đề tiềm ẩn trước khi chúng đạt đến sản xuất. Điều này góp phần vào một ứng dụng ổn định và đáng tin cậy hơn.

- **Chia sẻ Kiến thức:** Việc đánh giá code cho phép các thành viên trong nhóm tiếp xúc với các phong cách code khác nhau, các phương pháp hay nhất và các giải pháp, thúc đẩy việc học tập và cải thiện kỹ năng.

- **Nhất quán:** Đánh giá code thực thi các tiêu chuẩn code, quy ước đặt tên và mẫu thiết kế, dẫn đến code nhất quán và liền mạch trên toàn dự án.

- **Tinh chỉnh:** Đánh giá code cung cấp cơ hội để đề xuất cải tiến, tối ưu hóa và các giải pháp tinh tế hơn.

### Ví dụ

```jsx
// Ví dụ về bình luận đánh giá code:
/**
 * Bình luận của người đánh giá:
 * Hãy xem xét sử dụng hàm `map()` ở đây thay vì vòng lặp for để đọc dễ dàng hơn và tiếp cận chức năng.
 */

// Code gốc:
for (let i = 0; i < items.length; i++) {
  console.log(items[i]);
}

// Cải tiến đề xuất:
items.map((item) => console.log(item));
```

## 13. Use Hooks for Component Lifecycle - Sử dụng Hooks cho Vòng đời Thành phần

React Hooks đơn giản hóa quản lý vòng đời trong các thành phần chức năng. Sử dụng `useEffect` cho các tác dụng phụ và `useState` cho quản lý trạng thái.

### Ví dụ

```jsx
import React, { useState, useEffect } from "react";

function TimerComponent() {
  const [time, setTime] = useState(0);

  useEffect(() => {
    const timer = setInterval(() => {
      setTime((prevTime) => prevTime + 1);
    }, 1000);

    return () => clearInterval(timer);
  }, []);

  return <div>Bộ đếm thời gian: {time} giây</div>;
}
```

## 14. Lazy Loading Components - Tải Trễ Thành phần

Cải thiện hiệu suất của ứng dụng bằng cách tải trễ các thành phần không ngay lập tức cần thiết.

### Ví dụ

```jsx
import React, { Suspense, lazy } from "react";

const LazyLoadedComponent = lazy(() => import("./LazyComponent"));

function App() {
  return (
    <div>
      <Suspense fallback={<div>Đang tải...</div>}>
        <LazyLoadedComponent />
      </Suspense>
    </div>
  );
}
```

## 15. Custom Hooks - Hooks Tùy chỉnh

Tạo hooks tùy chỉnh để chia sẻ logic giữa các thành phần. Điều này giữ cho các thành phần của bạn sạch sẽ và DRY (Đừng lặp lại chính mình).

### Ví dụ

```jsx
import { useState, useEffect } from "react";

function useDocumentTitle(title) {
  useEffect(() => {
    document.title = title;
  }, [title]);
}

export default function Component() {
  useDocumentTitle("Tiêu đề Trang");

  return <h1>Xin chào, Thế giới!</h1>;
}
```

## Kết luận

Việc viết code React.js sạch không chỉ về mặt thẩm mỹ; nó về việc đặt nền tảng cho một ứng dụng có thể bảo trì và mở rộng. Bằng cách tuân theo các phương pháp hay nhất này, bạn không chỉ tạo ra code hoạt động mà còn là code dễ hiểu, sửa đổi và hợp tác. Hãy nhớ rằng, code sạch là một nỗ lực liên tục, và khi bạn tiếp tục cải thiện kỹ năng lập trình của mình, các ứng dụng React của bạn sẽ được hưởng lợi từ sự rõ ràng và khả năng bảo trì tăng lên.

## Nguồn tham khảo:

- [Với Ví dụ Code](https://javascript.withcodeexample.com/blog/react-js-clean-code-best-practices/)
