# Phân tích rủi ro vỡ nợ khoản vay thế chấp từ bộ dữ liệu Loan Default (Chủ đề 10)

Bài giữa kỳ 2 học phần Khoa học dữ liệu trong kinh tế và kinh doanh, lớp học phần AEP.TOKT1138.LS(126)_01, giảng viên Trần Đức Minh.

## Nhóm 2

| STT | Họ và tên | Mã sinh viên |
|---|---|---|
| 1 | Phạm Hùng Anh | 11240220 |
| 2 | Trần Thành Lộc | 11242555 |
| 3 | Tạ Minh Quang | 11240798 |
| 4 | Nguyễn Trọng Hoàn | 11248012 |
| 5 | Vũ Huy Anh | 11246422 |

## Các file trong repository

| File | Nội dung |
|---|---|
| `Loan_Default_Analysis.ipynb` | Notebook Colab gồm 4 giai đoạn của đề bài, chạy Run all từ đầu đến cuối không lỗi, đã lưu sẵn kết quả và biểu đồ |
| `Bao_cao_Giua_ky_2_Nhom_2.pdf` | Báo cáo của nhóm |

Dữ liệu dùng trong bài là [Loan Default Dataset trên Kaggle](https://www.kaggle.com/datasets/yasserh/loan-default-dataset), gồm 148.670 khoản vay và 34 thuộc tính.

## Cách chạy lại notebook

Mở Google Colab, chọn File rồi Open notebook, sang thẻ GitHub và dán đường dẫn của repository này. Sau khi notebook mở ra, chọn Runtime rồi Run all.

Notebook sẽ tự tìm dữ liệu theo thứ tự file `Loan_Default.csv` nằm cạnh notebook, sau đó là Kaggle qua thư viện `kagglehub` (không cần đăng nhập), cuối cùng là bản sao trên GitHub. Các biểu đồ được lưu vào thư mục `figures`. Nếu vì lý do nào đó không tải được dữ liệu, bạn có thể kéo file `Loan_Default.csv` vào thanh thư mục bên trái của Colab rồi chạy lại.

Các thư viện cần dùng gồm pandas, NumPy, SciPy, scikit-learn, Matplotlib và Seaborn, tất cả đều có sẵn trên Colab.

## Một vài kết quả chính

Tỷ lệ vỡ nợ chung của bộ dữ liệu là 24,64%.

Dữ liệu bị thiếu không xảy ra ngẫu nhiên. Tất cả các khoản vay thiếu thông tin lãi suất đều là khoản vỡ nợ, nên nếu dùng nguyên dữ liệu thì mô hình đạt AUC 1,000 nhưng kết quả này không có giá trị thực tế. Sau khi bỏ các thuộc tính gây rò rỉ, mô hình Random Forest đạt AUC 0,771.

Khoản vay có LTV trên 100% vỡ nợ 65,1%, khoản có DTI trên 50% vỡ nợ 42,7%. Khoản vay trả gộp cuối kỳ vỡ nợ 77,7% và khoản trả gốc âm vỡ nợ 44,6%.

Điểm tín dụng gần như không phân biệt được rủi ro, tỷ lệ vỡ nợ ở mọi nhóm điểm chỉ dao động từ 24,3% đến 25,2%.
