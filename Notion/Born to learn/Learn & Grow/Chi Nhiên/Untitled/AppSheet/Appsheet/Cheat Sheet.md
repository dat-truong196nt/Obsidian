---
Created: 2021-08-14T11:27
---
INDEX(Hàng hóa [Nhóm hàng],FIND([Barcode], hàng hóa[Barcode]))  
IN(TODAY(), Kiểm kê[Ngày])  
Validif Nhà phân phối[Nhà phân phối]  
LOOKUP([_THISROW].[Barcode], "Hàng hóa", "Barcode", "Nhóm hàng")  
Mã hàng valid if `Danh mục[Mã hàng] - SELECT(Kiểm kê[Mã hàng], IN(TODAY(), Kiểm kê[Ngày]))`