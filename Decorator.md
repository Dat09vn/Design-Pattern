**1. Định nghĩa**

The Decorator Design Pattern is a structural design pattern that allows behavior to be added to individual objects dynamically, without affecting the behavior of other objects from the same class. It involves creating a set of decorator classes that are used to wrap concrete components.

Attach additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.

Decorator pattern là một trong những Pattern thuộc nhóm cấu trúc (Structural Pattern). Nó cho phép người dùng thêm chức năng mới vào đối tượng hiện tại mà không muốn ảnh hưởng đến các đối tượng khác.
Kiểu thiết kế này có cấu trúc hoạt động như một lớp bao bọc (wrap) cho lớp hiện có. Mỗi khi cần thêm tính năng mới, đối tượng hiện có được wrap trong một đối tượng mới (decorator class).

**2. Các thành phần trong mẫu thiết kế Decorator:**


![image](https://github.com/user-attachments/assets/57313c51-44cc-4540-b273-08644842682a)

- Component: là một interface quy định các method chung cần phải có cho tất cả các thành phần tham gia vào mẫu này.
- ConcreteComponent : là lớp hiện thực (implements) các phương thức của Component.
- Decorator : là một abstract class dùng để duy trì một tham chiếu của đối tượng Component và đồng thời cài đặt các phương thức của Component  interface.
- ConcreteDecorator : là lớp hiện thực (implements) các phương thức của Decorator, nó cài đặt thêm các tính năng mới cho Component.
- Client : đối tượng sử dụng Component.

**3. When we use:**
   
Thay vì việc phải tạo ra rất nhiều class để kết hợp các chức năng send thông báo đến các ứng dụng thì ta có thể dùng decorator để kết hợp các chức năng với nhau:


![image](https://github.com/user-attachments/assets/209f01b7-2911-4d55-8b94-9d2be57ce8c0)

3.1 Lợi ích của Decorator Pattern là gì?
- Tăng cường khả năng mở rộng của đối tượng, bởi vì những thay đổi được thực hiện bằng cách implement trên các lớp mới.
- Client sẽ không nhận thấy sự khác biệt khi bạn đưa cho nó một wrapper thay vì đối tượng gốc.
- Một đối tượng có thể được bao bọc bởi nhiều wrapper cùng một lúc.
- Cho phép thêm hoặc xóa tính năng của một đối tượng lúc thực thi (run-time).

**4. Sử dụng Decorator Pattern khi nào?**
- Khi muốn thêm tính năng mới cho các đối tượng mà không ảnh hưởng đến các đối tượng này.
- Khi không thể mở rộng một đối tượng bằng cách thừa kế (inheritance). Chẳng hạn, một class sử dụng từ khóa final, muốn mở rộng class này chỉ còn cách duy nhất là sử dụng decorator.
- Trong một số nhiều trường hợp mà việc sử dụng kế thừa sẽ mất nhiều công sức trong việc viết code. Ví dụ trên là một trong những trường hợp như vậy.

**5. Example:**


![image](https://github.com/user-attachments/assets/57978e28-845c-4825-9702-6ed8a5c29b71)


![image](https://github.com/user-attachments/assets/1eb2ab5b-f9f6-45d5-bf88-921d2e1b173e)


