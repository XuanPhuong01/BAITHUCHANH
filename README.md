# BAITHUCHANH
Họ và tên: Nguyễn Thị Xuân Phương
MSSV:K225480106054
Lớp:K58KTP
## Dự Án: So Sánh Hiệu Năng và Kiến Trúc Pandas vs. PySpark Trên Cụm Phân Tán
**🔗 Links dự án:

GitHub Repository: https://github.com/XuanPhuong01/BAITHUCHANH.git

Video Demo / Thuyết trình: https://drive.google.com/file/d/18Jeyvf9VljJFqhNFdTkntJvRK9ydsTmv/view?usp=drive_link

### 1. Bối Cảnh & Mục Tiêu: 
    Dự án này được xây dựng nhằm mục đích tính toán "Doanh thu trung bình và thời gian di chuyển theo từng khung giờ trong ngày" từ bộ dữ liệu chuyến đi của Taxi. Thông qua dự án, chúng ta sẽ thực nghiệm và so sánh cách xử lý dữ liệu dạng bảng bằng Pandas (xử lý trên bộ nhớ đơn máy) so với PySpark DataFrame (xử lý phân tán).
   Mục tiêu học tập đạt được:
     -Phân biệt kiến trúc: Hiểu rõ giới hạn In-memory (bộ nhớ trong) của Pandas so với cơ chế Disk/RAM Distributed (phân tán) của Spark.
     - Khác biệt cơ chế thực thi: Trải nghiệm sự khác biệt giữa Eager Execution (Thực thi ngay lập tức - Pandas) và Lazy Evaluation (Thực thi lười biếng - PySpark).
     - Kỹ năng DevOps cơ bản: Tự thiết lập một cụm máy chủ ảo (Virtual Machine) kết nối mạng LAN để chạy Spark ở chế độ Standalone Cluster.

### 2.  Nguồn Dữ Liệu
    Sử dụng bộ dữ liệu mở NYC TLC Yellow Taxi Trip Records (định dạng Parquet).  
       - Quy mô Pandas: Xử lý 1 tháng dữ liệu (khoảng 3-4 triệu dòng, ~50MB file Parquet, bung ra RAM ~500MB).  
       - Quy mô PySpark: Xử lý 1-2 năm dữ liệu (khoảng 40-80 triệu dòng, ~1GB file Parquet, bung ra RAM > 5GB).

### 3.  Kiến Trúc Hệ Thống (Distributed Cluster Setup)
    Hệ thống mô phỏng một cụm máy tính xử lý phân tán sử dụng Ubuntu Linux, được cấu hình mạng Bridged Adapter để ping và SSH lẫn nhau:
   - Máy chủ (Master Node): 1 máy ảo (RAM 2GB, 2 CPU) - IP: 192.168.1.100.
   - Máy trạm (Worker Nodes): 2 máy ảo (RAM 2GB, 2 CPU) - IP: 192.168.1.101 và 192.168.1.102.

      
