<!-- Converted from Word (.docx) to Markdown.
This file intentionally keeps some HTML tags/styles inside Markdown to preserve Word-like formatting: font size, colors, indentation, numbering, bullets, bold/underline, and image dimensions. -->

<style type="text/css">
		@page { size: 8.27in 11.69in; margin: 1in }
		p { direction: ltr; margin-bottom: 0.1in; widows: 2; orphans: 2; text-align: left; line-height: 115%; background: transparent }
		a:link { color: #467886; text-decoration: underline }
		a:visited { color: #96607d; text-decoration: underline }
	</style>

<p align="center" style="line-height: 116%; margin-bottom: 0.11in">
<font color="#153d63"><font size="4" style="font-size: 16pt"><b>QUY
TRÌNH CA TẬP TRUNG</b></font></font></p>


<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>QUY
	TRÌNH VẬN HÀNH HỆ THỐNG CA TẬP TRUNG</b></font></p>
<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Quy
		trình quản lý máy chủ Esxi</b></font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Quy
		trình dựng máy chủ Esxi</b></font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Quy
		trình quản lý và backup máy ảo Esxi</b></font></p></li>
</ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>QUY
	TRÌNH THỰC HIỆN DỰ ÁN CA TẬP TRUNG</b></font></p></li>
</li></ol>


<p style="text-indent: 0.25in; line-height: 116%; margin-bottom: 0.11in">
Đối với dự án CA áp dụng phương pháp CA tập trung sẽ
bao gồm các bước sau:</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Khởi tạo
	tài liệu, công cụ cho dự án (1)</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Thu thập
	log cho dự án (2)</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Tiền xử
	lý log (3)</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Tiến hành
	hunting tập trung (4)</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Đánh giá
	lại hiệu năng và cải tiến (5)</p></li>
</ul>


<p style="line-height: 116%; margin-bottom: 0.11in"><br/>
<br/>
</p>


<p align="center" style="line-height: 116%; margin-bottom: 0.11in"><img align="bottom" border="0" height="499" name="Picture 1" src="images/image01.png" width="394"/>
</p>


<p style="line-height: 116%; margin-bottom: 0.11in"><br/>
<br/>
</p>


<ol>
<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Khởi
		tạo tài liệu cho dự án</b></font></p></li>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in">Hiện tại các
dự án CA đang sử dụng các file Excel (.xlsx) để quản lý
thông tin. Hiện tại tài liệu này sẽ áp dụng quy trình
với các file Excel</p>


<p style="line-height: 116%; margin-bottom: 0.11in">VSEC đang phát
triển hệ thống DFIR Platform hỗ trợ quản lý note cho
hunting tập trung và áp dụng trong thời gian sớm nhất
(khoảng tháng 04/2026). Sau khi app dụng DFIR Platform sẽ cập
nhật thêm quy trình sử dụng hệ thống này. 
</p>


<ol>
<ol>
<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63">Tạo
			Centrailzed Hunting Note</font></p></li>
</ol>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in">Tạo các File
exel từ template như hình sau: 
</p>


<p style="line-height: 116%; margin-bottom: 0.11in"><img align="bottom" border="0" height="129" name="Image2" src="images/image02.png" width="537"/>
</p>


<p style="line-height: 116%; margin-bottom: 0.11in">Template có
trong sharepoint DFIR với đường dẫn: 
</p>


<p style="line-height: 116%; margin-bottom: 0.11in"><span lang="en-US"><u>Documents
&gt; DFIR &gt; Documents &gt; Centralized Hunting &amp; Optimization
&gt; Template</u></span></p>


<p style="line-height: 116%; margin-bottom: 0.11in">Link: <font color="#467886"><u><a href="https://vsecvn.sharepoint.com/sites/HuntingDFIR/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2FHuntingDFIR%2FShared%20Documents%2FDFIR%2FDocuments%2FCentralized%20Hunting%20%26%20Optimization%2FTemplate&amp;viewid=7595e775%2De694%2D4192%2Db623%2Dcb73bfbc7c26&amp;ct=1739255796584&amp;or=Teams%2DHL&amp;ga=1&amp;LOF=1">Link</a></u></font></p>


<p style="line-height: 116%; margin-bottom: 0.11in">Copy vào thư
mục của dự án tương ứng. Ví dụ: 
</p>


<p style="line-height: 116%; margin-bottom: 0.11in"><img align="bottom" border="0" height="231" name="Image3" src="images/image03.png" width="589"/>
</p>


<p style="line-height: 116%; margin-bottom: 0.11in"><span lang="en-US">Các
file này sẽ được sử dụng </span>
</p>


<p lang="en-US" style="line-height: 116%; margin-bottom: 0.11in"><br/>
<br/>
</p>


<ol>
<ol>
<ol start="2">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#ee0000">Tạo
			dự án trên DFIR Platform (To be determined)</font></p></li>
</ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Thu
		thập log và thông tin thiết bị cho dự án</b></font></p>
<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Thu
			thập log từ endpoint</b></font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Copy
			log vào máy chủ Hunting tập trung</b></font></p></li>
</ol>
</li></ol>
</ol>


<ol type="a">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Truy
	cập vào máy chủ hunting tập trung</font></p></li>
</ol>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">IP
	Address: 10.15.4.241 (có thể thay đổi trong tương lai, xem
	mới nhất trong teams)</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Username:
	theo tên thành viên, ví dụ toannq, phongpt,…</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Password:
	&lt;được cấp riêng&gt;</font></p></li>
</ul>


<ol start="2" type="a">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Tạo
	thư mục log</font></p></li>
</ol>


<p style="line-height: 116%; margin-left: 0.44in; margin-bottom: 0.11in">
<font size="2" style="font-size: 11pt">Cần tạo 2 thư mục tương
ứng cho Raw Logs (chưa giải nén) và thư mục chứa log đã
giải nén và đã tiền xử lý</font></p>


<p style="line-height: 116%; margin-left: 0.44in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="216" name="Image4" src="images/image04.png" width="433"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Truy
	cập vào D:\ThreatHunting\hunting_directory\Raw_logs</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Tạo
	thư mục mới cho dự án, clone từ thư mục
	samples_structure_index</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#ee0000"><font size="2" style="font-size: 11pt">Lưu
	ý: tên thư mục cho dự án theo format: &lt;tên
	KH&gt;_&lt;month&gt;_&lt;year&gt;_index (1)</font></font></p></li>
</ul>


<p style="line-height: 116%; margin-bottom: 0.11in; margin-left: 0.5in">
<img align="bottom" border="0" height="94" name="Image5" src="images/image05.png" width="512"/>
</p>


<p style="line-height: 116%; margin-left: 0.5in; margin-bottom: 0.11in">
<font size="2" style="font-size: 11pt"><u>Lưu ý:</u></font><font size="2" style="font-size: 11pt">
cần copy chính xác loại log của Windows và Linux vào thư
mục tương ứng</font></p>


<p style="line-height: 116%; margin-left: 0.5in; margin-bottom: 0.11in">
<br/>
<br/>
</p>


<ol start="3" type="a">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Tạo
	thư mục chứa log giải nén và tiền xử lý</font></p></li>
</ol>


<p style="line-height: 116%; margin-left: 0.44in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="170" name="Image6" src="images/image06.png" width="505"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Truy
	cập vào D:\ThreatHunting\hunting_directory\DFIR_Logs</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Tạo
	thư mục mới cho dự án, clone từ thư mục
	samples_structures</font></p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<font color="#ee0000"><font size="2" style="font-size: 11pt">Lưu ý:
tên thư mục cho dự án theo format: &lt;tên
KH&gt;_&lt;month&gt;_&lt;year&gt;_index Tên phải giống (1)</font></font></p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="142" name="Image7" src="images/image07.png" width="410"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Cấu
	trúc thư mục dự án trong DFIR_Logs:</font></p>
<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">baseline_compare_ouput:
		chứa log đã so sánh với baseline</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">baseline_samples:
		chứa các sample log của host baseline</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">converted_data:
		chứa log đã tiền xử lý, được đẩy lên Splunk</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">hunting_data:
		chứa dữ liệu tiền xử lý riêng cho Linux hunting trên
		Portal</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">samples:
		chứa các thư mục log được giải nén từ Raw_Logs tương
		ứng</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">scan_output:
		chứa các kết quả scan (thông tin máy, trạng thái
		webshell, kết quả scan thor,…)</font></p></li>
</ul>
</li></ul>


<ol>
<ol>
<ol start="3">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Kiểm
			tra log</b></font></p></li>
</ol>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in">Trước khi hoàn
thành quá trình thu thập log, cần kiểm tra kỹ lưỡng các
log đã thu thập.</p>


<p style="line-height: 116%; margin-bottom: 0.11in">Để phát hiện
các trường hợp lỗi như:</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Tool thu
	thập log chưa chạy xong</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Tool đã
	chạy xong tuy nhiên thiếu log</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Tool thu
	thập webshell đã chạy xong nhưng không phát hiện được
	webroot</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Tool bị
	dừng sớm do hết thời gian timeout</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">vv…</p></li>
</ul>


<p style="line-height: 116%; margin-bottom: 0.11in">Có 2 cách để
kiểm tra log</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Sử dụng
	Jenkins job: Windows – Audit Missing Sample Log 
	</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Sử dụng
	công cụ .exe tự phát triển (áp dụng cho 1 log bất kỳ,
	không ưu tiên sử dụng cho hunting tập trung – yêu cầu
	tính nhất quán cao)</p></li>
</ul>


<p style="line-height: 116%; margin-bottom: 0.11in">Hướng dẫn sử
dụng Jenkins job:</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Truy cập
	job tại đường dẫn:</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"></p></li>
</ul>


<ol>
<ol>
<ol start="4">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Thu
			thập thông tin thiết bị cho dự án</b></font></p></li>
</ol>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in">Sau khi thu thập
log cần 
</p>


<ol type="I">
<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Tiền
		xử lý log và upload Splunk</b></font></p></li>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in">Dữ liệu đã
được chuẩn bị chính xác cho dự án ở bước 2.2.2</p>


<p style="line-height: 116%; margin-bottom: 0.11in">Tiếp theo sẽ
sử dụng <b>Jenkins</b> để chạy các công cụ tiền xử
lý thông qua các Job được cài đặt sẵn</p>


<ol>
<ol>
<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Tiền
			xử lý log cho Windows</b></font></p></li>
</ol>
</ol>
</ol>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Truy cập
	vào Jenkins tại địa chỉ: <font color="#467886"><u><a href="http://10.15.4.241/jenkins">http://10.15.4.241/jenkins</a></u></font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Truy cập
	job <b>Windows - Process and Upload to Splunk: </b><font color="#467886"><u><a href="http://10.15.4.241/jenkins/job/Windows%20Centralized%20Hunting/job/Windows%20-%20Process%20and%20Upload%20to%20Splunk/"><b>link</b></a></u></font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Chọn Build
	with Parameters</p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<br/>
<br/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="203" name="Image8" src="images/image08.png" width="451"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Nhập/chọn
	các parameters</font></p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="367" name="Image9" src="images/image09.png" width="291"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<font size="2" style="font-size: 11pt">Các parameters:</font></p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">index:
	tên index của dự án, trùng với (1) và (2)</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">splunkIndex:
	index của dự án trên Splunk (3)</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">unzip:
	có giải nén log từ Raw_Logs qua DFIR_Logs hay không</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">unzipOnly:
	true nếu chỉ muốn unzip chứ không tiền xử lý</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">unzipReplace:
	có giải nén lại những sample đã giải nén không</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">convertAll:
	có tiền xử lý ghi đè lại tất cả sample đã tiền xử
	lý, true khi có update về log</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">compareBaseline:
	có compare với baseline hay không</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">uploadToSplunk:
	true nếu muốn upload lên Splunk, false nếu chỉ tiền xử
	lý</font></p></li>
</ul>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Chọn
	Build để bắt đầu chạy tool tiền xử lý</font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Xem
	kết quả Build</font></p></li>
</ul>


<p style="line-height: 116%; margin-bottom: 0.11in; margin-left: 0.94in">
<img align="bottom" border="0" height="231" name="Image10" src="images/image10.png" width="395"/>
</p>


<p style="line-height: 116%; margin-bottom: 0.11in; margin-left: 0.94in">
<img align="bottom" border="0" height="219" name="Image11" src="images/image11.png" width="526"/>
</p>


<ol>
<ol>
<ol start="2">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Tiền
			xử lý log cho Linux</b></font></p></li>
</ol>
</ol>
</ol>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Truy cập
	vào Jenkins tại địa chỉ: <font color="#467886"><u><a href="http://10.15.4.241/jenkins">http://10.15.4.241/jenkins</a></u></font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Truy cập
	thư mục job <span lang="en-US"><b> Linux Centralized Hunting
	</b></span>
</p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="254" name="Image12" src="images/image12.png" width="445"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font size="2" style="font-size: 11pt">Chạy
	các job bên trong theo thứ tự sau:</font></p>
<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#467886"><u><a href="http://10.15.4.241/jenkins/job/Linux%20Centralized%20Hunting/job/Linux%20-%20Convert%20Samples%20To%20Hashes/"><font size="2" style="font-size: 11pt">Linux
		- Convert Samples To Hashes</font></a></u></font><font size="2" style="font-size: 11pt">:
		Convert sample thành hash</font></p></li>
</ul>
</li></ul>


<p style="line-height: 116%; margin-left: 1.75in; margin-bottom: 0.11in">
<br/>
<br/>
</p>


<p style="line-height: 116%; margin-left: 1.25in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="230" name="Image13" src="images/image13.png" width="317"/>
</p>


<ul>
<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#467886"><u><a href="http://10.15.4.241/jenkins/job/Linux%20Centralized%20Hunting/job/Linux%20-%20Generate%20Baseline%20Hashes/"><font size="2" style="font-size: 11pt">Linux
		- Generate Baseline Hashes</font></a></u></font><font size="2" style="font-size: 11pt">:
		convert các baseline thành hash</font></p></li>
</ul>
</ul>


<p style="line-height: 116%; margin-left: 1.25in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="240" name="Image14" src="images/image14.png" width="311"/>
</p>


<ul>
<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#467886"><u><a href="http://10.15.4.241/jenkins/job/Linux%20Centralized%20Hunting/job/Linux%20-%20Scan%20All%20Samples/"><font size="2" style="font-size: 11pt">Linux
		- Scan All Samples</font></a></u></font><font size="2" style="font-size: 11pt">:
		scan tất cả các sample với baseline</font></p></li>
</ul>
</ul>


<p style="line-height: 116%; margin-left: 1.25in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="282" name="Image15" src="images/image15.png" width="284"/>
</p>


<ol>
<ol>
<ol start="3">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Kiểm
			tra log upload Splunk</b></font></p></li>
</ol>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in">Sau khi tiền xử
lý và upload log lên Splunk, cần kiểm tra kỹ lưỡng log đã
được đẩy thành công, chính xác lên Splunk chưa. Nếu
thiếu log sẽ dẫn đến việc rà soát thiếu.</p>


<p style="line-height: 116%; margin-bottom: 0.11in">Sử dụng query
Splunk để kiểm tra số lượng event được đẩy lên
Splunk và số lượng event từ raw log có tương đồng hay
không.</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Kiểm tra
	log Windows sử dụng query tại: <font color="#467886"><u><a href="https://gitlab.vsec.com.vn/dfir/hunting-group/dfir-platform/centralized-threat-hunting-usecases/-/blob/master/Windows/0.%20Check%20event%20count/queries.md?ref_type=heads">Queries</a></u></font></p></li>
</ul>


<p style="line-height: 116%; margin-bottom: 0.11in"><img align="bottom" border="0" height="246" name="Image16" src="images/image16.png" width="582"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Kiểm tra
	log Linux sử dụng query tại: <font color="#467886"><u><a href="https://gitlab.vsec.com.vn/dfir/hunting-group/dfir-platform/centralized-threat-hunting-usecases/-/blob/master/Linux/0.%20Check%20event%20count/queries.md?ref_type=heads">Queries</a></u></font></p></li>
</ul>


<p style="line-height: 116%; margin-bottom: 0.11in"><img align="bottom" border="0" height="248" name="Picture 2" src="images/image17.png" width="575"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<br/>
<br/>
</p>


<ol>
<ol start="4">
<li><p style="line-height: 116%; margin-bottom: 0.06in"><font color="#153d63"><b>Tiến
		hành hunting tập trung</b></font></p></li>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in">Sau khi dữ liệu
và log được xử lý thành công, tiến hành hunting tập
trung</p>


<p style="line-height: 116%; margin-bottom: 0.11in">Hunting tập
trung sẽ chia ra Hunting tập trung cho Windows và Linux</p>


<p style="line-height: 116%; margin-bottom: 0.11in">Trong đó:</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0in">Windows:
	hunting dựa trên query trên <b>Splunk</b></p></li>
<li><p style="line-height: 116%; margin-bottom: 0in">Linux: hunting
	kết hợp <b>Splunk</b> và công cụ <b>Hunting Portal</b></p></li>
</ul>


<p style="line-height: 116%; margin-bottom: 0.11in">Các công cụ
sử dụng:</p>


<ul>
<li><p align="justify" style="line-height: 116%; margin-bottom: 0.11in">
<font color="#467886"><u><a href="https://app.clickup.com/90181015141/v/o/s/90183617331">DFIR
	Hunting Checklist Clickup</a></u></font>: hỗ trợ tracking tiến
	độ, assign công việc và tính hiệu quả công việc của
	<b>hunting trên Splunk</b></p></li>
<li><p align="justify" style="line-height: 116%; margin-bottom: 0.11in">
<font color="#467886"><u><a href="http://10.15.4.241/hunting/hunting-logsource">DFIR
	Hunting Portal</a></u></font>: hỗ trợ hunting các checklist
	manual của Linux và hunting compare Linux, hunting cho webshell,
	note envidence,….</p></li>
<li><p align="justify" style="line-height: 116%; margin-bottom: 0.11in">
<font color="#467886"><u><a href="http://10.15.4.241:8000/en-GB/app/search/search">Splunk
	Web</a></u></font>: thực hiện các truy vấn hunting tập
	trung theo usecase/log type</p></li>
<li><p align="justify" style="line-height: 116%; margin-bottom: 0.11in">
<font color="#467886"><u><a href="https://github.com/ToanElNino/Centralize-Threat-Hunting-Usecases">Hunting
	usecases</a></u></font>: chứa các câu query hunting tập trung
	cho Linux và Wndows</p></li>
</ul>


<p align="justify" style="line-height: 116%; margin-left: 0.5in; margin-bottom: 0.11in">
<br/>
<br/>
</p>


<ol>
<ol>
<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Hunting
			tập trung cho Windows</b></font></p></li>
</ol>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in">Hunting tập
trung cho Windows sẽ dựa trên việc hunting theo từng usecase
cho các loại sourcetype</p>


<p style="line-height: 116%; margin-bottom: 0.11in">Ví dụ 1 số
loại sourcetype: 
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">autoruns: từ
	log_autoruns.csv</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">dll_scan: từ
	dll.csv</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">prefetch_windows:
	tiền xử lý từ danh sách các file .pf</p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in">check_iis_module:
	tiền xử lý từ danh sách các file web.config của IIS
	webroot</p></li>
</ul>


<ol type="a">
<li><p style="line-height: 116%; margin-bottom: 0.11in">Quản lý
	tiến độ hunting theo checklist</p></li>
</ol>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Tạo
	Clickup folder cho dự án tương ứng</p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="130" name="Image17" src="images/image18.png" width="440"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="270" name="Image18" src="images/image19.png" width="297"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Tạo
	Checklist hunting windows cho dự án trong thư mục vừa tạo</p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="157" name="Image19" src="images/image20.png" width="415"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="196" name="Image20" src="images/image21.png" width="421"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="254" name="Image21" src="images/image22.png" width="390"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
Checklist sẽ được tạo trong folder như hình dưới:</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="172" name="Image22" src="images/image23.png" width="522"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Assign task
	cho member</p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="100" name="Image23" src="images/image24.png" width="395"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="86" name="Image24" src="images/image25.png" width="453"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Bắt đầu
	cho từng checklist</p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
Khi bắt đầu hunting từng checklist cần chuyển status sang
<b>IN PROGRESS </b>và <b>bấm thời gian</b> cho task (sẽ là dữ
liệu quan trọng để đánh giá hiệu năng và cải tiến)</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="54" name="Image25" src="images/image26.png" width="455"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<font color="#ee0000">Note: chỉ cần bấm time cho sub-task, task
lớn sẽ tự tính tổng thời gian</font></p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Query
	hunting cho checklis trên <b>Splunk</b></p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
Ví dụ: <b>1.1 Unsignged Image</b>, query sẽ có trong
<font color="#467886"><u><a href="https://github.com/ToanElNino/Centralize-Threat-Hunting-Usecases/blob/master/Windows/1.%20Autoruns/1.1%20Unsigned%20Image/queries.md">Centralize-Threat-Hunting-Usecases/Windows/1.
Autoruns/1.1 Unsigned Image/queries.md</a></u></font></p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<br/>
<br/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="240" name="Image26" src="images/image27.png" width="547"/>
</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
Sử dụng Query để search trên Splunk</p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<font color="#ee0000">Note: Đổi index chính xác theo splunk
index (3) tiền xử lý ở bước 2.3.1. Tiền xử lý log cho
Windows</font></p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="268" name="Image27" src="images/image28.png" width="543"/>
</p>


<ul>
<li><p style="line-height: 116%; margin-bottom: 0.11in">Hoàn thành
	một checklist</p></li>
</ul>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
Chuyển status sang <b>DONE</b> và <b>stop timer</b></p>


<p style="line-height: 116%; margin-left: 0.75in; margin-bottom: 0.11in">
<img align="bottom" border="0" height="48" name="Image28" src="images/image29.png" width="548"/>
</p>


<p style="line-height: 116%; margin-left: 0.44in; margin-bottom: 0.11in">
<br/>
<br/>
</p>


<ol>
<ol>
<ol start="2">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Hunting
			tập trung cho Linux</b></font></p></li>
</ol>
</ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in"><br/>
<br/>
</p>


<p style="margin-bottom: 0.11in; margin-left: 0.45in; line-height: 116%">
<br/>
<br/>
</p>


<ol>
<ol start="5">
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Đánh
		giá hiệu năng và cải tiến</b></font></p>
<ol>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Thu
			thập và đánh giá hiệu năng</b></font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Hướng
			dẫn contribute vào Usecase hunting</b></font></p></li>
<li><p style="line-height: 116%; margin-bottom: 0.11in"><font color="#153d63"><b>Hướng
			dẫn contribute vào DFIR Platform</b></font></p></li>
</ol>
</li></ol>
</ol>


<p style="line-height: 116%; margin-bottom: 0.11in"><br/>
<br/>
</p>


