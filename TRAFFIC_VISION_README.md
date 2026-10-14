# MapVision Traffic Research Lab 2.0

**Thiết kế module: Long Ngo · MIT © 2026**

Website dự kiến: https://xulytiengviet.github.io/mapvision/

## Phạm vi đã triển khai
- HTML/CSS/JavaScript thuần, không CDN, tile hay API từ xa, chạy tĩnh trên GitHub Pages.
- Mô phỏng vi mô từng xe, bước thời gian cố định 0.1s, random seed xác định.
- IDM giản lược: gia tốc dựa trên tốc độ mong muốn và khoảng cách an toàn với xe trước.
- Hai trục đường minh họa (4 hướng di chuyển), nút giao có đèn 2 pha, pha vàng toàn đỏ.
- Cấu hình phương tiện, lưu lượng sinh, chu kỳ và tỷ lệ xanh, tốc độ mô phỏng.
- Kịch bản bình thường, giờ cao điểm và ngập giả định.
- Xuất ảnh PNG, GeoJSON đường giả định, CSV trạng thái xe, JSON kịch bản, TXT báo cáo.
- Dashboard tốc độ, hàng chờ, lượt qua nút, tổng giây chờ và biểu đồ lịch sử.

## Hệ tọa độ
Mốc địa lý minh họa `lat=10.252, lon=105.972` và hệ phẳng cục bộ theo mét:
`lon = lon0 + (x - 600)/(111320 cos(lat0))`;
`lat = lat0 + (400 - y)/111320`.
Các tuyến đường là **hình học giả định**, không phải GeoJSON đường thực đã khảo sát. Các đơn vị vận tốc xuất từ mô hình theo mét/giây và đổi ra km/giờ, không phải vận tốc quan trắc.

## Lưu ý khoa học
Đây là một công cụ giáo dục và thử nghiệm, **không phải** bộ mô phỏng giao thông được hiệu chuẩn/kiểm chứng hoặc camera AI. Mô hình chưa có lane-changing, xe rẽ, tương tác tại vùng xung đột, người đi bộ, giao thông hỗn hợp, hiệu chuẩn OSM hay phép đo GPS thực. Số lượng xe đang hoạt động phụ thuộc giới hạn tải và khả năng xe được sinh; không cam kết luôn bằng thanh cài đặt. Những tình huống trái quy tắc có thể xảy ra tại nút giao giản lược.

## Tối ưu băng thông
Trang chỉ tải một tệp `index.html` và chạy cục bộ sau khi tải. Không cần tile; giao diện sử dụng Canvas 2D. Dữ liệu chỉ xuất xuống thiết bị khi người dùng nhấn tải. Có thể xây dựng chế độ GIS thực từ vector GeoJSON/PMTiles riêng nhưng cần cấu hình cache, attribution, bản quyền và CORS.

## Sử dụng
1. Bật GitHub Pages: Settings → Pages → Deploy from branch → `main` / `(root)`.
2. Truy cập URL, thay đổi lưu lượng, chu kỳ đèn, tỷ lệ xanh, chạy kịch bản.
3. Quan sát thống kê và xuất file để phân tích.

## Giấy phép
Module dashboard mô phỏng độc lập trong `index.html` và tài liệu này: MIT © 2026 Long Ngo, theo `TRAFFIC_VISION_LICENSE.md`. Các module nghiên cứu computer vision vốn có tại các thư mục khác vẫn giữ giấy phép Apache-2.0 theo `LICENSE` gốc.
