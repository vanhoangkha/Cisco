# Switch
## **1) Collision domain - miền đụng độ**
- **Đụng độ** xảy ra khi có 2 hay nhiều máy truyền dữ liệu đồng thời trong 1 mạng chia sẻ .
- Khi **đụng độ** xảy ra , các gói tin đang được truyền đều bị phá hủy , các máy truyền sẽ ngưng việc truyền dữ liệu và chờ 1 khoảng thời gian ngẫu nhiên theo quy luật của **CSMA / CD** ( **Carrier Sense Multiple Access with Collision Detection** ) 
- Nếu **đụng độ** xảy ra quá nhiều , mạng có thể không hoạt động được .
## **2) Broadcast Domain - miền quảng bá**

<img src=https://i.imgur.com/Vb4nQ4Z.png>

- Khi một thiết bị muốn gửi gói tin quảng bá thì địa chỉ MAC đích của gói tin sẽ là `FF:FF:FF:FF:FF:FF` . Với địa chỉ như vậy , mọi địa chỉ đều nhận và xử lý gói quảng bá .
- **Miền quảng bá** là miền bao gồm tất cả các thiết bị có thể nhận được gói tin quảng bá từ 1 thiết bị nào đó trong **LAN** .
## **3) Hoạt động của Switch**
- Switch học địa chỉ MAC và bảng MAC từ source MAC của Ethernet Frame khi **frame** đi vào cổng nào đó của Switch .
- Switch forward **frame** ra 1 cổng thích hợp dựa vào destination MAC của **frame** . Có 2 trường hợp : 
    - Nếu destination MAC của **frame**  là 1 địa chỉ ***unicast*** MAC có sẵn trong bảng MAC , Switch chỉ cần chuyển **frame** ra cổng tương ứng với MAC trong bảng MAC .
    - Nếu destination MAC của **frame** là 1 địa chỉ ***unicast*** MAC chưa có trong bảng MAC hoặc là 1 MAC ***broadcast*** , Switch sẽ thực hiện flood **frame** này ra tất cả các cổng trừ cổng nhận vào .
- Công nghệ **Auto-MDIX** :
    - **Auto-MDIX** là một công nghệ được phát triển bởi HP cho phép người quản trị hệ thống mạng linh hoạt trong việc sử dụng cáp thẳng (Straight-Through) hoặc cáp chéo (Cross Over) bất chấp chúng ta đang tiến hành kết nối PC với router hay switch. 
## **4) Cấu hình Switch**
- Hiển thị bảng MAC :
    ```
    Switch# show mac-address-table
    ```