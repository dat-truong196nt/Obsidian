---
App name: Inventory Porting V3
Last edited: 2021-12-28T21:23
---
**TO TRY:**

APP : [https://www.appsheet.com/newshortcut/6708448a-5ac3-4233-9181-351f0fcaeb8a](https://www.appsheet.com/newshortcut/6708448a-5ac3-4233-9181-351f0fcaeb8a)  
Web : [https://www.appsheet.com/start/6708448a-5ac3-4233-9181-351f0fcaeb8a](https://www.appsheet.com/start/6708448a-5ac3-4233-9181-351f0fcaeb8a)  
**FEATURES:**

- Mains:
    - Chỉnh view của xuất kho:
        - Location: Xuất kho.
        - Details:
            - Thu gọn các cột, bỏ bớt những khoảng trống.
            - Bấm vào từng line để xem chi tiết sản phẩm.
            - Bấm vào dấu tick để check "đã đủ sản phẩm".
            - Thay đổi vị trí hiển thị tên sàn TMĐT.
        - Reason: Chỉ hiển thị dữ liệu cần, giúp tập trung.
    - Chỉnh view kiểm kê:
        - Location: Kiểm kê.
        - Details: Show đúng/sai (green/red) ngay trên số liệu.
        - Reason: Đỡ rối mắt.
    - Add nút reset số liệu:
        - Location: Kiểm kê.
        - Details: Khi bấm reset thì tất cả số liệu chuyển về 0.
        - Reason:
            - Biết được cái nào đã nhập rồi (green).
            - Nếu để như trước thì sẽ nhìn thấy dữ liệu ngày trước đó (All green).
    - Add kiểm kê từng sản phẩm:
        - Location: Kiểm kê.
        - Detail: Khi bấm vào các hàng thì sẽ xem được (Hình ảnh, tên, mã, nhà cung cấp của sản phẩm.
        - Reason: Giúp người nhập nhận diện được sản phẩm.
- Chores:
    - Assumption doanh thu của shop (Dựa vào file excel exported):
        - Shopee: [Tổng giá trị đơn hàng (VND)] - [Mã giảm giá của Shop]
        - Lazada: [paidPrice]
        - Tiki: [Doanh thu]
    - App::Change color
        - Location: all.
        - Reason: Cho đẹp.
    - UI::Remove icon
        - Location: Xử lý đơn → Xuất kho, Đóng gói, Vận chuyển.
        - Details: Bỏ icon ở các nút Call to action.
        - Reason: Rối mắt.

**TEST:**

- Test 500,000 line (1 year).
    - GG excel: Chỉ hiện được 5,000,000 ô (500,000 x 10).
    - Test thử 300,000 lines nhưng app sync rất chậm.
    - Khi chuyển qua lại giữa các tab chậm, hiển thị ko nổi.
    - Thao tác với phần (Đổi trả đơn) → App tự tắt.

**PROPOSAL**:

- Test 500,000 line (1 year).
    - App chỉ thao tác được với các đơn trong vòng 1 tháng (50,000 đơn).
    - Dùng (app, excel) tự lọc ra các đơn trong 1 tháng. (Để app tự lọc cũng mất nhiều tg).

**TODO:**

- Chị Nhiên:
    - Cách tính đơn trễ.
    - Cách lấy hàng theo Heijunka.
- Đạt:
    - Học lại lý thuyết Heijunka (Nói cho trẻ 10 tuổi hiểu).
    - Update app để có thể quản lý được dữ liệu cho 1 năm.