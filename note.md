1. Khi class có sử dụng parameter constructor --> cần phải tạo default constructor nếu muốn gọi default constructor, bởi nó sẽ không tự động tạo default constructor.

2. Khi Sub class kế thừa Base class, mà Sub class có thêm các phương thức bổ sung
  
   --> BASE *obj = new SUB();
  
   --> Nếu muốn gọi các phương thức bổ sung của Sub class thì ta phải cast obj về SUB
