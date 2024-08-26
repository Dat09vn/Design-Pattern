Command pattern là một pattern cho phép bạn chuyển đổi một request thành một object độc lập chứa tất cả thông tin về request. Việc chuyển đổi này cho phép bạn tham số hoá các methods với các yêu cầu khác nhau như log, queue (undo/redo), transtraction.
Các thành phần trong mô hình command:
  - Command : là một interface hoặc abstract class, chứa một phương thức trừu tượng thực thi (execute) một hành động (operation). Request sẽ được đóng gói dưới dạng Command.
  - ConcreteCommand : là các implementation của Command. Định nghĩa một sự gắn kết giữa một đối tượng Receiver và một hành động. Thực thi execute() bằng việc gọi operation đang hoãn trên Receiver.
  - Client: tiếp nhận request từ phía người dùng, đóng gói request thành ConcreteCommand thích hợp và thiết lập receiver của nó.
  - Invoker: tiếp nhận ConcreteCommand từ Client và gọi execute() của ConcreteCommand để thực thi request.
  - Receiver : đây là thành phần thực sự xử lý business logic cho case request. Trong phương thức execute() của ConcreteCommand chúng ta sẽ gọi method thích hợp trong Receiver.
Dưới đây chúng ta có thể liệt kê một số trường hợp mà khi gặp sẽ phải cân nhắc sử dụng Command pattern:
  - Khi cần tham số hóa các đối tượng theo một hành động thực hiện (biến action thành parameter)
  - Khi cần tạo và thực thi các yêu cầu vào các thời điểm khác nhau (delay action)
  - Khi cần hỗ trợ tính năng undo, log, callback hoặc transaction
  - Phối hợp nhiều Command với nhau theo thứ tự

Hãy tưởng tượng khi tạo ra một UIButton đẹp lung linh và muốn đưa nó ra toàn thể ae sử dụng về sau và ứng dụng trong nhiều mảng khác nhau tuy nhiên vấn đề là bạn chưa biết nó sẽ sử dụng cho những mục đích khác nhau nào.
Các bạn có thể nghĩ đến trường hợp inheritance - tạo các sub class cho button mà bạn đã tạo ra để từ đó xử lí cho mỗi trường hợp khác nhau nhưng với 1 ứng dụng phức tạp việc tạo ra quá nhiều sub class cho 1 component cũng là 1 cái gi đó khá là không ổn đúng không ạ.
Chúng ta có thể xử lí vấn đề theo hướng command - đóng gói ý tưởng, những action cần làm khi button được ấn hoặc menu item được chọn. Tức là gom code để xử lý việc ấn button hoặc chọn menu trong object riêng. Những action này chính là những commands của Command pattern.

Why we use command pattern:
We have so many button need to design such as: Copy button, Paste button, Cut button, ... --> The simplest solution is to create tons of subclasses for each place where the button is used.
But, Some operations, such as copying/pasting text, would need to be invoked from multiple places. For example, a user could click a small “Copy” button on the toolbar, or copy something via the context menu, or just hit Ctrl+C on the keyboard.
--> we need to use command pattern to seperate Command Copy and (Button Copy or Shortcut Ctrl+C)

Example:
![image](https://github.com/user-attachments/assets/30f93609-57bb-43a2-acd8-353eceb01962)
