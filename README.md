# TinyOS-Project3
Truyền dữ liệu trên mạng các mote CM-5000 sử dụng TinyOS.
Mạng được chia thành 3 tầng: tầng thu thập dữ liệu, tầng trung gian, tầng gốc.
1. Tầng thu thập dữ liệu tiến hành thu thập thông tin từ môi trường dựa trên các cảm biến có trên mote, bao gồm các thông tin: nhiệt độ, độ ẩm, ánh sáng. Các dữ liệu này được đóng gói và gửi đến tầng trung gian dưới dạng một raw-code.
2. Tầng trung gian, tầng trung gian thu thập dữ liệu từ môi trường đồng thời nhận dữ liệu được gửi đến từ tầng thu thập dữ liệu và tiến hành đóng gói dữ liệu sau khi được tái cấu trúc gói tin theo định nghĩa: cứ mỗi 4 gói tin* sẽ được đóng gói thành 1 gói tin, các gói tin* được lấy từ hàng đợi của mote đó. Gói tin sau khi đóng gói sẽ được gửi đến tầng gốc(sử dụng id) và được xếp vào hàng đợi đọc của mote gốc này
3. Tầng gốc: nhận gói tin được gửi từ tầng trung gian và phân rã gói tin để lấy dữ liệu cảm biến cần thiết( sử dụng hàm Listen.java để decode dữ liệu). Cuối cùng dữ liệu này chỉ bao gồm các thông tin về: id thiết bị gửi, dữ liệu về nhiệt độ, độ ẩm, ánh sáng được in trực tiếp từ console screen.
# Language: nesC
Một số chú ý khi nạp code lên các thiết bị (mote CM 5000):
- cài đặt module cần thiết trên hđh debian Linux
- cài đặt môi trường trên máy và trên chip MSP430F1611
