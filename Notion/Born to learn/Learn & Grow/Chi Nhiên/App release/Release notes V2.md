---
App name: Inventory Porting V2
Last edited: 2021-12-28T21:23
Version: "1.000218"
---
**TO TRY:**  
APP : [https://www.appsheet.com/newshortcut/8345ab63-379d-4d01-b38d-feddc2947b4a](https://www.appsheet.com/newshortcut/8345ab63-379d-4d01-b38d-feddc2947b4a)  
Web : [https://www.appsheet.com/start/8345ab63-379d-4d01-b38d-feddc2947b4a](https://www.appsheet.com/start/8345ab63-379d-4d01-b38d-feddc2947b4a)  
**FEATURES:**

- Mains:
    - Add view: Thêm sản phẩm / Thêm nhà cung cấp.
        - Role: Admin only.
        - Vị trí: Menu.
        - Chọn lần lượt: Mã nhóm hàng → Mã sản phẩm → Những thứ còn lại.
    - Add view: Đổi trả đơn
        - Role: Any.
        - Vị trí: Xử lí đơn.
        - Có thể xem các mặt hàng trong đơn.
        - Lý do hủy/trả sẽ được gợi ý tùy theo sàn (Có thể đưa ra lý do khác).
- Chores:
    - Update UX:
        - Vị trí: Xử lí đơn → (Xuất kho, Đóng gói, Vận chuyển).
        - Có thể bấm vào bất cứ chỗ nào trong hàng để switch trạng thái.
    - Update UI:
        - Vị trí: Xử lí đơn → (Xuất kho, Đóng gói, Vận chuyển).
        - Mỗi lần thỏa điều kiện thì các nút sẽ sáng lên.
    - Update UI:
        - Vị trí: Kiểm kê.
        - Thêm nút reset (Trước khi kiểm kê nên bấm nút để reset giá trị về 0).
        - Sắp xếp lại cách hiển thị sản phẩm.
    - Fix cứng quy cách đóng gói:
        - Vị trí: Kiểm kê.
        - Quy cách đóng gói sẽ được set sẵn trong "Danh mục".
    - Update Backend:
        - Xuất kho sẽ được thực hiện ở backend.
        - Ưu điểm: Nhanh chóng, không cần đợi sync.
        - Nhược điểm: Không show được dữ liệu xuất kho trên APP (trừ khi bấm sync dữ liệu).

**TEST:**

- Time sync:
    - 2 phút / 25 tasks.
    - 9 phút / 110 tasks.
- Sync chưa xog nhưng APP bị tắt.
    - Vẫn mở lên sync dữ liệu về excel được.

**TODO:**

- Chị Nhiên:
    - Cách tính đơn trễ.
    - Cách lấy hàng theo Heijunka.
- Đạt:
    - Tìm cách chỉnh chiều rộng cột.
    - Tìm cách tính doanh thu của shop.