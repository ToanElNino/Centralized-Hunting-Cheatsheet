# QUY TRÌNH THỰC HIỆN DỰ ÁN CA TẬP TRUNG

Đối với dự án CA áp dụng phương pháp CA tập trung sẽ
bao gồm các bước sau:

- Khởi tạo
  tài liệu, công cụ cho dự án (1)

- Thu thập
  log cho dự án (2)

- Tiền xử
  lý log (3)

- Tiến hành
  hunting tập trung (4)

- Đánh giá
  lại hiệu năng và cải tiến (5)

  <img src="images/image01.png" width="394">

# 1. Khởi tạo tài liệu cho dự án

Hiện tại các dự án CA đang sử dụng các file Excel (.xlsx) để quản lý thông tin. Hiện tại tài liệu này sẽ áp dụng quy trình với các file Excel

VSEC đang phát triển hệ thống DFIR Platform hỗ trợ quản lý note cho hunting tập trung và áp dụng trong thời gian sớm nhất. Sau khi app dụng DFIR Platform sẽ cập nhật thêm quy trình sử dụng hệ thống này.

## 1.1. Tạo Centrailzed Hunting Note

Tạo các File
exel từ template như hình sau:

  <img src="images/image02.png" width="700">

Template có
trong sharepoint DFIR với đường dẫn:

Documents
&gt; DFIR &gt; Documents &gt; Centralized Hunting &amp; Optimization
&gt; Template

Link: [Link](https://vsecvn.sharepoint.com/sites/HuntingDFIR/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2FHuntingDFIR%2FShared%20Documents%2FDFIR%2FDocuments%2FCentralized%20Hunting%20%26%20Optimization%2FTemplate&viewid=7595e775%2De694%2D4192%2Db623%2Dcb73bfbc7c26&ct=1739255796584&or=Teams%2DHL&LOF=1)

Copy vào thư mục của dự án tương ứng. Ví dụ:

  <img src="images/image03.png" width="700">

Các file này sẽ được sử dụng...

## 1.2.  Tạo dự án trên DFIR Platform (To be determined)
---

# 2. Thu thập log và thông tin thiết bị cho dự án

## 2.1. Thu thập log từ endpoint

## 2.2. Copy log vào máy chủ Hunting tập trung

a. Truy
  cập vào máy chủ hunting tập trung

- IP
  Address: 10.15.4.241 (có thể thay đổi trong tương lai, xem
  mới nhất trong teams)

- Username:
  theo tên thành viên, ví dụ toannq, phongpt,…

- Password:
  &lt;được cấp riêng&gt;

b. Tạo
  thư mục log

- Cần tạo 2 thư mục tương
ứng cho Raw Logs (chưa giải nén) và thư mục chứa log đã
giải nén và đã tiền xử lý

  <img src="images/image04.png" width="700">

- Truy
  cập vào D:\ThreatHunting\hunting_directory\Raw_logs

- Tạo
  thư mục mới cho dự án, clone từ thư mục
  samples_structure_index 

  - Lưu
  ý: Cần copy chính xác loại log của Windows và Linux vào thư
mục tương ứng và tạo tên thư mục cho dự án theo format: &lt;tên
  KH&gt;_&lt;month&gt;_&lt;year&gt;\_index (1) 

  <img src="images/image05.png" width="700">


- Tạo
  thư mục chứa log giải nén và tiền xử lý

  <img src="images/image06.png" width="700">

- Truy
  cập vào D:\ThreatHunting\hunting_directory\DFIR_Logs

- Tạo
  thư mục mới cho dự án, clone từ thư mục
  samples_structures

  - Lưu ý:
tên thư mục cho dự án theo format: &lt;tên
KH&gt;_&lt;month&gt;_&lt;year&gt;\_index Tên phải giống (1)

  <img src="images/image07.png" width="410">

  - Cấu
  trúc thư mục dự án trong DFIR_Logs:

  - baseline_compare_ouput:
  chứa log đã so sánh với baseline

  - baseline_samples:
  chứa các sample log của host baseline

  - converted_data:
  chứa log đã tiền xử lý, được đẩy lên Splunk

  - hunting_data:
  chứa dữ liệu tiền xử lý riêng cho Linux hunting trên
  Portal

  - samples:
  chứa các thư mục log được giải nén từ Raw_Logs tương
  ứng

  - scan_output:
  chứa các kết quả scan (thông tin máy, trạng thái
  webshell, kết quả scan thor,…)

## 2.3. Kiểm tra log

Trước khi hoàn
thành quá trình thu thập log, cần kiểm tra kỹ lưỡng các
log đã thu thập.

Để phát hiện
các trường hợp lỗi như:

- Tool thu
  thập log chưa chạy xong

- Tool đã
  chạy xong tuy nhiên thiếu log

- Tool thu
  thập webshell đã chạy xong nhưng không phát hiện được
  webroot

- Tool bị
  dừng sớm do hết thời gian timeout

- vv…

**Có 2 cách để kiểm tra log**

- Sử dụng
  Jenkins job: Windows – Audit Missing Sample Log

- Sử dụng script .py để kiểm tra: (TDB)

Hướng dẫn sử
dụng Jenkins job:

- Truy cập
  job tại đường dẫn:

-

## 2.4. Thu thập thông tin thiết bị cho dự án

Sau khi thu thập log cần lên danh sách các hostname, IP, OS, webshell status,...cho các máy chủ đã thu thập log.
**TDB**

# 3. Tiền xử lý log và upload Splunk

Dữ liệu đã được chuẩn bị chính xác cho dự án ở bước 2.2.2

Tiếp theo sẽ sử dụng **Jenkins** để chạy các công cụ tiền xử lý thông qua các Job được cài đặt sẵn

## 3.1. Tiền xử lý log cho Windows

- Truy cập
  vào Jenkins tại địa chỉ: http://10.15.4.241/jenkins

- Truy cập
  job: [Windows - Process and Upload to Splunk](http://10.15.4.241/jenkins/job/Windows%20Centralized%20Hunting/job/Windows%20-%20Process%20and%20Upload%20to%20Splunk/)

- Chọn Build
  with Parameters

  <img src="images/image08.png" width="451">

- Nhập/chọn
  các parameters

  <img src="images/image09.png" width="291">

- Các parameters:

	- index:
	tên index của dự án, trùng với (1) và (2)

	- splunkIndex:
	index của dự án trên Splunk (3)

	- unzip:
	có giải nén log từ Raw_Logs qua DFIR_Logs hay không

	- unzipOnly:
	true nếu chỉ muốn unzip chứ không tiền xử lý

	- unzipReplace:
	có giải nén lại những sample đã giải nén không

	- convertAll:
	có tiền xử lý ghi đè lại tất cả sample đã tiền xử
	lý, true khi có update về log

	- compareBaseline:
	có compare với baseline hay không

	- uploadToSplunk:
	true nếu muốn upload lên Splunk, false nếu chỉ tiền xử
	lý

- Chọn
  Build để bắt đầu chạy tool tiền xử lý

- Xem
  kết quả Build

  <img src="images/image10.png" width="395">

  <img src="images/image11.png" width="526">

## 3.2. Tiền xử lý log cho Linux

- Truy cập
  vào Jenkins tại địa chỉ: [Jenkins](http://10.15.4.241/jenkins)

- Truy cập
  thư mục job **Linux Centralized Hunting**

  <img src="images/image12.png" width="445">

- Chạy các job bên trong theo thứ tự sau:

	- Linux - Convert Samples To Hashes:
	Convert sample thành hash

	<img src="images/image13.png" width="400" style="margin-left: 40px">

	- Linux - Generate Baseline Hashes:
	convert các baseline thành hash

	<img src="images/image14.png" width="400" style="margin-left: 40px">

	- Linux - Scan All Samples:
	scan tất cả các sample với baseline

	<img src="images/image15.png" width="400" style="margin-left: 40px">

## 3.3. Kiểm tra log upload Splunk

Sau khi tiền xử lý và upload log lên Splunk, cần kiểm tra kỹ lưỡng log đã được đẩy thành công, chính xác lên Splunk chưa. Nếu thiếu log sẽ dẫn đến việc rà soát thiếu.

Sử dụng query Splunk để kiểm tra số lượng event được đẩy lên Splunk và số lượng event từ raw log có tương đồng hay không.

- Kiểm tra
  log Windows sử dụng query tại: [Queries](https://gitlab.vsec.com.vn/dfir/hunting-group/dfir-platform/centralized-threat-hunting-usecases/-/blob/master/Windows/0.%20Check%20event%20count/queries.md?ref_type=heads)

  <img src="images/image16.png" width="700">

- Kiểm tra
  log Linux sử dụng query tại: [Queries](https://gitlab.vsec.com.vn/dfir/hunting-group/dfir-platform/centralized-threat-hunting-usecases/-/blob/master/Linux/0.%20Check%20event%20count/queries.md?ref_type=heads)

  <img src="images/image17.png" width="700">

# 4. Tiến hành hunting tập trung

Sau khi dữ liệu và log được xử lý thành công, tiến hành hunting tập trung
Hunting tập trung sẽ chia ra Hunting tập trung cho Windows và Linux

Trong đó:

- Windows:
  hunting dựa trên query trên **Splunk**

- Linux: hunting
  kết hợp **Splunk** và công cụ **Hunting Portal**

**Các công cụ sử dụng:**

- [DFIR Hunting Checklist Clickup](https://app.clickup.com/90181015141/v/o/s/90183617331): hỗ trợ tracking tiến
  độ, assign công việc và tính hiệu quả công việc của
  **hunting trên Splunk**

- [DFIR Hunting Portal](http://10.15.4.241/hunting/hunting-logsource): hỗ trợ hunting các checklist
  manual của Linux và hunting compare Linux, hunting cho webshell,
  note envidence,….

- [Splunk Web](http://10.15.4.241:8000/en-GB/app/search/search): thực hiện các truy vấn hunting tập
  trung theo usecase/log type

- [Hunting usecases](https://gitlab.vsec.com.vn/dfir/hunting-group/dfir-platform/centralized-threat-hunting-usecases): chứa các câu query hunting tập trung
  cho Linux và Wndows

## 4.1. Hunting tập trung cho Windows

Hunting tập trung cho Windows sẽ dựa trên việc hunting theo từng usecase cho các loại sourcetype

Ví dụ 1 số loại sourcetype:

- **autoruns**: từ log_autoruns.csv

- **dll_scan**: từ dll.csv

- **prefetch_windows**: tiền xử lý từ danh sách các file .pf

- **check_iis_module**:
  tiền xử lý từ danh sách các file web.config của IIS
  webroot

a. Quản lý tiến độ hunting theo checklist

- Tạo
  Clickup folder cho dự án tương ứng

  <img src="images/image18.png" width="500">

  <img src="images/image19.png" width="500">

- Tạo
  Checklist hunting windows cho dự án trong thư mục vừa tạo

  <img src="images/image20.png" width="500">

  <img src="images/image21.png" width="500">

  <img src="images/image22.png" width="500">

  Checklist sẽ được tạo trong folder như hình dưới:

  <img src="images/image23.png" width="500">

- Assign task
  cho member

  <img src="images/image24.png" width="500">

  <img src="images/image25.png" width="500">

- Bắt đầu cho từng checklist

	Khi bắt đầu hunting từng checklist cần chuyển status sang **IN PROGRESS** và bấm thời gian cho task (sẽ là dữ
	liệu quan trọng để đánh giá hiệu năng và cải tiến)

  <img src="images/image26.png" width="455">

	***Note: chỉ cần bấm time cho sub-task, task
	lớn sẽ tự tính tổng thời gian***

- Query hunting cho checklis trên **Splunk**

	Ví dụ: **1.1 Unsignged Image**, query sẽ có trong
	***Centralize-Threat-Hunting-Usecases/Windows/1.
	Autoruns/1.1 Unsigned Image/queries.md***

  <img src="images/image27.png" width="700">

   Sử dụng Query để search trên Splunk

	***Note: Đổi index chính xác theo splunk
	index (3) tiền xử lý ở bước 2.3.1. Tiền xử lý log cho
	Windows***

  <img src="images/image28.png" width="543">

- Hoàn thành một checklist

	Chuyển status sang **DONE** và **stop timer**

  <img src="images/image29.png" width="700">

## 4.2. Hunting tập trung cho Linux

# 5. Viết báo cáo và kết thúc dự án
## 5.1. Viết báo cáo CA
## 5.2. 