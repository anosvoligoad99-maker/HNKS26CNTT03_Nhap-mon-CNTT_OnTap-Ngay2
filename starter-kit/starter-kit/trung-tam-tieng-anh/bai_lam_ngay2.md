# BÀI LÀM – ÔN TẬP NGÀY 2

- **Họ tên:Lê Minh Quân**
- **Lớp:CNTT03**
- **Link repository:https://github.com/anosvoligoad99-maker/HNKS26CNTT03_Nhap-mon-CNTT_OnTap-Ngay2**
- **Hệ điều hành (Windows/macOS):Windows**

## Bài 1. Lọc log thủ công

### Lệnh đã chạy

```shell
Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\access.log | Select-String "ERROR" > .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\error_report.txt
Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\error_report.txt -head 2
```

### 2 dòng lỗi đầu tiên trong error_report.txt

```text
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
```

## Bài 2. Đếm bằng pipeline

### Lệnh

```shell
(Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\access.log | Select-String "WARNING").count
(Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\payment.log | Select-String "ERROR").count
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
WARNING trong access.log:4
ERROR trong payment.log:3
```

## Bài 3. Chạy script auto_warning (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
PS D:\starter-kit\starter-kit\trung-tam-tieng-anh> .\auto_warning.ps1                                                   

```

### Nội dung file logs/warning_report.txt

```text
=== CANH BAO THANH TOAN ===

2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi


```

## Bài 4. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
1 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\access.log | Select-String "ERROR"
   2 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\access.log | Select-String "ERROR" > logs/error_...
   3 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\access.log | Select-String "ERROR" > .\starter-k...
   4 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\error_report.txt
   5 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\error_report.txt -head2
   6 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\error_report.txt -head 2
   7 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\error_report.txt -head 2
   8 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\error_report.txt -head 2
   9 Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\access.log | Select-String "WARNING"
  10 (Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\access.log | Select-String "WARNING").count
  11 (Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\access.log | Select-String "ERROR").count
  12 (Get-content .\starter-kit\starter-kit\trung-tam-tieng-anh\logs\payment.log | Select-String "ERROR").count
  13 cd .\starter-kit\starter-kit\trung-tam-tieng-anh\
14 .\auto_warning.ps1


```

### Nội dung file logs/tong_hop_ngay2.txt

```text
2025-10-18 08:17:59 [ERROR] Khong tim thay trang /lich-thi (404)
2025-10-18 08:25:55 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:33:51 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:37:19 [ERROR] Ket noi may chu du lieu that bai
2025-10-18 08:49:43 [ERROR] Het thoi gian cho (timeout)
2025-10-18 08:53:11 [ERROR] Het thoi gian cho (timeout)

2025-10-18 09:19:13 [WARNING] Cong thanh toan phan hoi cham
2025-10-18 09:28:16 [WARNING] Nhieu lan nhap sai ma OTP
2025-10-18 09:43:01 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:46:22 [WARNING] So du vi gan bang hoc phi
2025-10-18 09:49:43 [WARNING] So du vi gan bang hoc phi
```

## Bài 5. Câu hỏi ngắn

- **a)>: Xóa cũ, ghi mới mất dữ liệu cũ,>>: Viết nối tiếp vào cuối giữ nguyên dữ liệu cũ.**
- **b) Ở Bài 4, nếu lệnh thứ hai (nối các dòng ERROR) dùng > thay cho >>, nội dung file tong_hop_ngay2.txt sẽ bị mất dòng chữ === TONG HOP ACCESS LOG ===**
- **c)Vì đường dẫn tuyệt đối chỉ chạy được trên đúng máy tính của bạn , còn đường dẫn tương đối giúp script chạy được trên mọi máy tính, mọi thư mục hay khi đưa lên server mà không bị lỗi.**

## Tự chấm (điền sau khi có đáp án)

- **Điểm tự chấm:** ..../100
- **Lỗi mình đã mắc và cách sửa:**
