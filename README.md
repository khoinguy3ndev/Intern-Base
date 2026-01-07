# Git Flow Process
1. Git commands:
  - git pull: Để kéo các thay đổi mới từ branch khác về branch hiện tại.
  - git push: Để đẩy các thay đổi mới từ branch hiện tại lên 1 branch.
  - git merge: Để trộn các thay đổi từ 1 branch khác với branch hiện tại.
  - git cherry-pick: Để lấy 1 hoặc 1 vài commit từ branch khác về branch hiện tại.
  - git rebase: Để đưa commit của branch hiện tại lên HEAD của branch khác.
  - git reset: Để di chuyển HEAD về commit cũ hơn.
2. Basic git flow:
  - Gitflow là một ý tưởng trừu tượng về quy trình sử dụng Git, nó chỉ ra cách thức setup các loại branchs khác nhau và cách thức để merge chúng lại với nhau.
  - Master: branch chứa mã nguồn khởi tạo của ứng dụng và các version đã sẵn sàng để realease cho người dùng có thể sử dụng.
  - Hotfix: Được base trên nhánh master để sửa nhanh những lỗi trên UIT hoặc sửa những cấu hình đặc biệt chỉ có trên môi trường productions.
  - Release: Trước khi Release một phần mềm dev team cần được tạo ra để kiểm tra lại lần cuối trước đi release sản phần để người dùng có thể sử dụng
  - Develop: Được khởi tạo từ master branch để lưu lại tất cả lịch sử thay đổi của mã nguồn. Develop branchs là merge code của tất cả các branchs feature.
  - Feature: Được base trên branch develop. Mỗi khi phát triển một feature mới chúng ta cần tạo một branchs để viết mã nguồn cho từng feature.
3. Git Structure Monolith, Multirepo, Monorepo
  - Monolith: Một ứng dụng duy nhất, các module gắn chặt, build & deploy cùng nhau.
  - Multirepo: Một ứng dụng như chia nhiều repo khác nhau cho từng chức năng hoặc project (FE, BE, ...)
      + Props: Dễ cho access control, build và deploy, scalability.
      + Cons: Phải setup cho thư viện,... cho từng repo, dễ dẫn tới xung đột.
  - Monorepo: Một ứng dụng sử dụng chung 1 repo duy nhất để quản lý
      + Props: Dễ cho dùng chung thư viện, components, utility giữa các dự án. Tất cả dự án đều dùng chung thư viện.
      + Cons: Repo sẽ phình to khi dự án càng lớn: khiến clone, pull,status lâu. CI/CD phức tạp, cần tool hỗ trợ, khó access control

# JSCore
1. Types & Grammar:
  - Variables: Khai báo var, let, const.
  - Data Types: Nguyên thủy (string, number, boolean, null, undefined, symbol), Object (array, object thường, function).
  - Operators: Số học, So sánh, &&, ||, !, Bitwise.
  - Boolean logic: Truthy và Falsy.
  - Functions: hàm thường và Arrow functions.
  - Loops: for, while, do-while,...
2. Scope & Closures:
  - Scope: Global scope, Function scope, Block scope (let/const).
  - Lexical Scope: Phạm vi sống của biến được quyết định bởi block scope.
  - Dynamic scope: Phạm vi sống của biến được quyết định bởi callstack
  - Hoisting: Cơ chế đưa khai báo được đưa lên đầu của hàm và tham số.
  - Closures: Là một hàm mà có thể truy cập biến thuộc scope chứa nó.
3. This and Object Prototypes:
  - this: trỏ tới object hoặc class đang gọi hàm.
  - Prototypes: Kế thừa, chuỗi prototype, __proto__, thuộc tính prototype.
4. Async:
  - Callback: Xử lý bất đồng bộ truyền thống, có thể gây ra callback hell.
  - Promise: Các trạng thái (pending, resolved, rejected), chuỗi (chaining), .then(), .catch(), .all() để xử lý tùy trường hợp.
  - Async/Await: Cú pháp mới cho Promise, giúp code dễ đọc hơn.
  - Event Loop: Có cách thành phần như Call Stack, Web APIs, Callback Queue, Task Queue. Là một cơ chế xử lý bất đồng bộ, các tác vụ bất đồng bộ sẽ được đẩy qua Web APIs xử lý, sau khi xử lý xong tác vụ đó sẽ được đưa cho Task Queue để chờ rồi đến Call Stack để thực thi.
5. ES6 and more:
  - Destructuring, Spread/Rest operators, Template Literals, Classes, Modules, Tham số mặc định.

# HTML CSS
1. Layout & Responsive:
  - Flexbox: Container (flex-direction, justify-content, align-items), Items (flex-grow, flex-basis).
  - Grid: Layout 2 chiều, rows, columns, areas.
  - CSS Specificity: * > Inline > ID > Class > Tag.
  - Responsive: Tùy vào các breakpoint mà điều chỉnh bố cục giao diện, media queries, đơn vị tương đối (rem, em, %, vw, vh).
2. Semantic HTML:
  - Sử dụng các thẻ mang ý nghĩa ngữ nghĩa: <header>, <nav>, <main>, <article>, <section>, <aside>, <footer> thay vì thẻ <div> chung chung. Lợi ích cho SEO và Accessibility.

# Restful API
1. Basics:
  - Methods:
    - GET: Lấy dữ liệu.
    - POST: Tạo mới tài nguyên.
    - PUT: Thay thế/Cập nhật toàn bộ tài nguyên.
    - PATCH: Cập nhật một phần tài nguyên.
    - DELETE: Xóa tài nguyên.
  - Request & Response: Cấu trúc (Head, Body).
2. Headers & Configuration:
  - Headers: Authorization (Tokens), Content-Type, Accept.
  - Content-Type: application/json, multipart/form-data,...
  - Allow Origin: CORS (Cross-Origin Resource Sharing) headers để kiểm soát truy cập từ các domain khác.
3. Error Status Codes:
  - 401 Unauthorized: Yêu cầu xác thực hoặc xác thực thất bại.
  - 403 Forbidden: Đã xác thực nhưng không có quyền truy cập.
  - Các dải phổ biến: 2xx (Thành công), 3xx (Chuyển hướng), 4xx (Lỗi phía Client), 5xx (Lỗi phía Server).
4. Advanced:
  - FormData: Xử lý upload file và dữ liệu form thông qua lập trình.
  - XML Request: Là công cụ xử lý request, xử lý định dạng XML cũ.
