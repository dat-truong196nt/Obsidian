Quá trình (50%)  
- Điểm danh (10%)  
- Bài tập nhóm (10%)  
- Tiều luận nhóm (30%) (29/12)  
+ FEM, REM: Fixed/Random Effect Model (Cộng điểm)  
+ Chương 4+5: slide 37  
+ WorkingJournal Paper  
+ Topic: Firm performance  
Cuối kỳ (50%)  
- Tự luận (50%): Bt sách chương 3,4,5,7  
  
Chú ý:  
- Trong điều kiện các yếu tố khác không đổi  
  
B1 = Cov(x, y)/Cov(x)  
B0 = Mean(y) - B1*Mean(x)  
Square(R) = SSE/SST (SSE: Sum of square explainable)  
Square(R) cao không giải thích mối quan hệ nhân quả của PT.  
  
  
  
Assumptions: Random sampling  
Purpose: evaluate → forecast  
Nonexperimental data  
  
Equations  
- u: unobserved factors  
- βx give directions and strength  
  
Data Structures  
- Cross-Sectional Data: At a given point of time (ordering is not matter)  
- Time Series Data: Chronological ordering is important, samples often strongly related, data frequency  
- Pooled Cross Sections: How cross-sectional data changes over time  
- Panel/Longitudinal Data: Same sectional **units** are followed over a given time period.  
Using cateris paribus to result causality  
  
Chapter 2:  
E(u|x) = E(u) → u is mean independent of x  
  
→ 23  
P2 bình phương nhỏ nhất = OLS = ordinary least square.  
  
Mẫu đại diện cho tổng thể → ước lượng thay đổi trong mẫu.  
  
ROA ← R&D  
1 cá thể có thể có hơn 1 quan sát.  
continuous: biến định lượng, biến liên tục (wage, educ, exper)  
dummy: biến định tính (female, maried)  
u: muy (biến không đo lường, ko quan sát được)  
  
xu thế (của bộ dữ liệu)  
  
  
  
Tiểu luận  
Tangibility = bombing + (Performance + leverage + size)  
(): controls  
  
Y: biến phụ thuộc (dependant var)  
x(k): biến độc lập, biến giải thích (independant var)  
  
OLS (đơn/đa biến)  
5 giả thuyết OLS  
  
Đọc bài [https://scholar.google.com/](https://scholar.google.com/)?  
  
  
Chương 2:  
y = Bo + B1x1 + u  
Bo: hệ số chặn, B1: hệ số góc.  
E(u/x) = 0: Kỳ vọng/Trung bình của y theo x = 0  
sd: standard deviation  
se: standard error  
  
  
Chương 3:  
ceteris paribus: trong điều kiện các yếu tố khác không đổi.  
multicollirearity: đa cộng tuyến  
BLUEs: Best linear unbiased estimations: Ước lượng tuyến tính không chệch tốt nhất.  
MLR 1→3: OLS có tồn tại  
- Tuyến tính theo tham số  
- Mẫu ngẫu nhiên.  
- Không có đa cộng tuyến hoàn hảo (VIF)  
MLR4: beta mũ j sẽ là ước lượng không chệch của beta j  
- E(u/x) = 0  
- E(beta mũ j) = Beta j  
MLR5: ct phương sai  
MLR6: u phân phối chuẩn  
Mức ý nghĩa alpha : Cơ hội mắc sai lầm  
1 - alpha: Độ tin cậy  
  
Chương 4:  
Phân phối: Với 1 mẫu ngẫu nhiên, phân phối cho biết xác xuất xuất hiện của một x.  
N(0;1): Phân phối chuẩn tắc.  
Mod(n): Giá trị  
n-(k+1): degree of freedom: Số bậc tự do.  
  
VD:  
H0: βexper = 0  
H1: βexper > 0  
  
tab: tabulate  
  
Chương 3: woorich: 1,2,3,4,5,7  
File BT1: 1, 2, 3  
  
Chọn H0 là thứ gây ra hậu quả lớn hơn → Bác bỏ giả thuyết.  
  
  
Loglink?  
Có thể phát biểu salary theo log(salary)  
  
  
  
Tính chất ước lượng OLS:  
- Không chệch  
- Hiệu quả  
  
  
  
2-slage  
iv  
  
  
ss: sum of square: tổng bình phương  
ss (model): SSE  
ss (Residual): SSR  
ss (Total): SST  
Prob > F: p-value  
  
Câu hỏi nghiên cứu → dữ liệu → hồi quy → kết quả → kết luận câu hỏi nghiên cứu.  
  
Không có đa cộng tuyến hoàn hảo (Dùng kiểm định VIF).  
Vẽ phân phối chuẩn(u).  
  
MLR (1→3): OLS tồn tại  
MLR (1→4): Không chệch (E(^Bj) = Bj)  
MLR (1→4’): Vững  
MLR (1-5): Hiệu quả  
MLR (1-6): BLUE  
  
  
hettest  
xtreg  
  
log(TA)  
log(khoảng cách)  
  
Ma trận hệ số tương quan  
Set dữ liệu panel (  
  
Thực hiện kiểm định White  
  
FEM, REM: Thay đổi mô hình để chạy FEM, REM.  
FEM: Theo thời gian, theo cá thể.  
absorb(id), absorb(year)  
group(id, year): two-way fixed effect.  
  
OLS:  
  
  
  
  
  
  
  
  
TODO:  
Import data to SQL query (AWS) (Hỏi Khánh)  
  
  
  
Bài tập lớn:  
- Các yếu tố đề cập tới trong đề tài là gì? CEO (0, 1) + Risk taking.  
- Mô hình hoá (x y): x-CEO, y-risktaking.  
Risk-taking(it) = Bo + B1CEO(it) + Controls + u  
sd(ROA) ← risk taking  
- Tìm controls: từ các nghiên cứu trước (literature) (phụ thuộc hoàn toàn vào literature)  
- Literature giữa x với y.  
- Câu hỏi nghiên cứu.  
- Giả thuyết: Ho: Việc … không ảnh hưởng tới … của doanh nghiệp.  
H1:  
- Regress → test (PEM, REM)  
  
- Viết cấu trúc 5 chương.  
- Đặt vấn đề → Tóm tắt  
- Lý do thực hiện đề tài.  
- Không viết tổng quan nghiên cứu (Vì định tính)  
- Nghiên cứu của nhóm tác giả, năm bn, nghiên cứu gì, kết quả.  
- Biến, định nghĩa, dấu kỳ vọng, nguồn (nói nhanh nghiên cứu đó muốn nói gì).  
- Kiểm định tương quan giữa các biến.  
-