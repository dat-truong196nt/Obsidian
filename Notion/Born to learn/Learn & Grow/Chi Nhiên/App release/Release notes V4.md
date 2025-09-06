---
App name: Inventory Porting V4
Last edited: 2022-01-11T06:00
---
**TO TRY:**

APP :  
Web :  
**FEATURES:**

- Mains:
    - Objective: App có thể vận hành mượt mà với dữ liệu lớn.
        - KRs:
            - Độ trễ cho mỗi thao tác dưới 1s.
            - App có thể lưu trữ tối đa 500,000 đơn.
            - Thời gian sync lúc ban đầu dưới 5s.
        - Why:
            - Cần tổng kết dữ liệu cho cả 1 năm vận hành.
            - Cần xử lý đơn nhanh chóng.
        - How:
            - Tách ra 2 sheet riêng biệt:
                - 1 sheet để thao tác với đơn hàng hiện tại (Lấy hàng, Đóng gói, Vận chuyển, Hoàn thành, Trả, Hủy).
                - 1 sheet để lưu dữ liệu cũ ( > 1 tháng kể từ lần cập nhật đơn cuối cùng).
- Chores (Fix lỗi):
    - [Nhập] hiển thị unexpected value (Reset số liệu):
        

**TEST:**

- Objective: Test từng phần của app và fix lỗi
    - KRs:
        - 3 phần: Kiểm kê, Nhập, Xử lý đơn hoàn thành hết checklist.
        - Tất cả các lỗi phát sinh được lưu trữ lại.
        - Checklist phải theo User Behavior.
    - Why:
        - Chuẩn bị cho release tiếp theo 2 - Dec
        - Temporary close project.
    - How:
        - Suy nghĩ về những trường hợp trong từng phần (Kiểm kê, Nhập, Xử lý đơn).
        - Đưa ra checklist cho từng phần.
        - Test theo checklist (Step by step).
        - Log bug.
        - Fix 1 by 1.

**TODO:**

- Chị Nhiên:
    - Cách tính đơn trễ.
    - Cách lấy hàng theo Heijunka.
- Đạt:
    - Học lại lý thuyết Heijunka (Nói cho trẻ 10 tuổi hiểu).
    - Test lại với 500,000 đơn lưu.

#### Testing

|Name|Assign|Status|
|---|---|---|
|[[Nhập hàng- Tự điền (Mã nhóm, nhóm hàng, tên sản phẩm, nhà cung cấp, vị trí quầy kệ) khi QA code valid]]||In progress|
|[[Nhập hàng- Tự động tính tổng tiền]]||Not started|
|[[Nhập hàng- Update đúng tất cả các cột trong sheet “Nhập”]]||Not started|
|[[Kiểm kê- Thể hiện được kiểm kê đúng (green) - sai (red)]]||Not started|
|[[Kiểm kê- Tự động cân bằng kiểm kê ngày tiếp theo (Lấy số liệu nhập làm số liệu hiện có)]]||Not started|
|[[Xử lý đơnXuất kho lấy đúng số lượng đơn và sản phẩm]]||Not started|
|[[Xử lý đơnXuất kho hiển thị được hàng đã nhận và tên sàn TMĐT]]||Not started|
|[[Xử lý đơnXuất kho Bấm nút xuất kho → tất cả đơn sẽ hiển thị ở Xử lý đơnĐóng gói]]||Not started|
|[[Xử lý đơnĐóng gói Bấm nút đóng gói → tất cả đơn đã đóng gói (Green) sẽ hiển thị ở Xử lý đơnVận chuyển]]||Not started|
|[[Xử lý đơnVận chuyển Bấm nút (Hoàn thành) thì tất cả đơn đã vận chuyển (Green) sẽ hiển thị ở Xử lý đơnĐổi trả đơn]]||Not started|
|[[Xử lý đơnĐổi trả đơn Xem được thông tin đơn hàng]]||Not started|
|[[Xử lý đơnĐổi trả đơn Chuyển trạng thái sang (Đổi, Trả) và bắt buộc điền lý do cụ thể]]||Not started|