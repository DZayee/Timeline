# Timeline
Để thêm **timeline năm** vào Google Sheets, bạn có thể dùng các công cụ sẵn có của Google Sheets như **Chart** hoặc **Conditional Formatting**. Dưới đây là cách thiết kế:  

---

### **1. Thêm cột cho timeline năm**  
Chỉnh sửa bảng hiện tại, thêm cột để xác định thời gian trong năm:  

| **Tên Dự án** | **Loại Sự kiện** | **Thời gian bắt đầu** | **Thời gian kết thúc** | **Mô tả công việc**        | **Tiến độ** | **Người phụ trách** | **Timeline**         |  
|---------------|------------------|-----------------------|-----------------------|---------------------------|-------------|---------------------|---------------------|  
| TOKI Finance  | TGE              | 01/12/2024           | 15/12/2024           | Lên kế hoạch chiến dịch PR | 30%         | Long                | Dec 2024 (W49-50)   |  
| BachMa Labs   | Testnet          | 05/12/2024           | 20/12/2024           | Quản lý cộng đồng Discord  | 50%         | Long                | Dec 2024 (W49-51)   |  

#### **Cách tạo cột "Timeline":**
1. **Timeline dạng tuần:**  
   - Sử dụng hàm **WEEKNUM** để tự động tính tuần trong năm:  
     ```
     =TEXT(A3,"MMM YYYY") & " (W" & WEEKNUM(A3,2) & ")"
     ```
   - Kết hợp thời gian bắt đầu và kết thúc.

---

### **2. Sử dụng Conditional Formatting cho màu sắc thời gian**  
- Tạo quy tắc:  
  - Tô màu theo tháng, ví dụ:  
    - Tháng 12: Màu xanh dương.  
    - Tháng 11: Màu vàng nhạt.  
  - Dùng **Custom Formula**, ví dụ:  
    ```
    =MONTH(C3)=12
    ```

---

### **3. Vẽ Gantt Chart hoặc Timeline Chart:**  
**Gantt Chart (dùng Bar Chart):**  
1. **Chèn thêm cột "Ngày (dạng số)":**  
   - Cột Start (thời gian bắt đầu):  
     ```
     =DATEVALUE(C3)
     ```
   - Cột Duration (Số ngày từ start đến end):  
     ```
     =DATEDIF(C3,D3,"d")
     ```
2. Chọn dữ liệu:  
   - **Dự án** (Tên dự án).  
   - **Start Date** và **Duration**.  
3. Vào **Insert > Chart > Stacked Bar Chart**.

**Timeline Chart:**  
1. Chọn dữ liệu: **Tên dự án**, **Thời gian bắt đầu**, **Thời gian kết thúc**.  
2. Vào **Insert > Chart > Timeline Chart**.  
3. Tùy chỉnh màu và phạm vi thời gian theo tháng, tuần, hoặc năm.  

---

Bạn muốn mình tạo sẵn template Google Sheets để bạn sử dụng không?
