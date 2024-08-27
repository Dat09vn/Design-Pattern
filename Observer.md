1.0 Định nghĩa: Observer pattern là một mẫu thiết kế phần mềm mà một đối tượng, gọi là subject, duy trì một danh sách các thành phần phụ thuộc nó, gọi là observer, và thông báo tới chúng một cách tự động về bất cứ thay đổi nào.

2.0 Observer Pattern được áp dụng khi:
Sự thay đổi trạng thái ở 1 đối tượng có thể được thông báo đến các đối tượng khác mà không phải giữ chúng liên kết quá chặt chẽ. Cần mở rộng dự án với ít sự thay đổi nhất.

2.1 When to use the Observer Design Pattern?

- One-to-Many Dependence:
  
  - Use the Observer pattern when there is a one-to-many relationship between objects, and changes in one object should notify multiple dependent objects.
    
  - This is particularly useful when changes in one object need to propagate to several other objects without making them tightly coupled.
    
- Decoupling:
  
  - Use the Observer pattern to achieve loose coupling between objects.

  - This allows the subject (publisher) and observers (subscribers) to interact without being aware of each other’s specific details. It promotes a flexible and maintainable system.

- Change Propagation:

  - When changes in the state of one object should automatically trigger updates in other objects, the Observer pattern is beneficial.

  - This helps ensure that all dependent objects are informed and can respond accordingly to changes in the subject.

- Dynamic Composition:

  - If you need to support dynamic composition of objects with runtime registration and deregistration of observers, the Observer pattern is suitable.

  - New observers can be added or existing ones removed without modifying the subject.

- Event Handling:

  - The Observer pattern is often used in event handling systems.

  - When events occur in a system, observers (listeners) can react to those events without requiring the source of the events to have explicit knowledge of the observers.

![image](https://github.com/user-attachments/assets/cfaf8f24-ea10-4a4a-978c-4996b849249d)

Image1:

![image](https://github.com/user-attachments/assets/e0fdebe9-8ef3-4624-b610-4ad43074c165)

Image2:

![image](https://github.com/user-attachments/assets/35a1bf04-d07c-4e43-adb7-b84abc4d6ade)

Image3:
