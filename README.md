# Cờ Tướng (Xiangqi)

Game cờ tướng chạy trên trình duyệt, gói gọn trong một file `index.html` (HTML + CSS + JavaScript thuần, không thư viện ngoài).

## Tính năng

- Bàn cờ 9x10 vẽ bằng SVG, có sông và cung tướng, quân cờ chữ Hán.
- Luật đi đầy đủ: Tướng/Sĩ trong cung, Tượng không qua sông và bị cản mắt, Mã bị cản chân, Pháo ăn qua đúng một ngòi, Tốt qua sông mới được đi ngang, hai tướng không được đối mặt, không được tự đưa tướng vào thế bị chiếu.
- Phát hiện chiếu tướng, chiếu bí, hết nước đi và thông báo người thắng.
- Chơi với máy (người cầm Đỏ) hoặc hai người trên cùng máy.
- AI minimax + alpha-beta + tìm kiếm tĩnh, 3 mức độ khó (độ sâu 1 / 2 / 4).
- Highlight nước đi hợp lệ, đánh dấu nước vừa đi, undo, ván mới, đổi chế độ.
- Responsive, chơi được trên điện thoại và máy tính.

## Chạy

Mở `index.html` bằng trình duyệt, hoặc bật GitHub Pages cho repo này (Settings → Pages → Deploy from branch `main`, folder `/`).

## Cấu trúc mã

`index.html` gồm ba khối `<script>` độc lập:

| Khối | Nội dung |
| --- | --- |
| `rules` | Biểu diễn bàn cờ, sinh nước đi, kiểm tra chiếu, nước hợp lệ, trạng thái ván |
| `ai` | Lượng giá (bảng điểm vị trí), negamax alpha-beta, quiescence, chọn nước |
| `ui` | Vẽ SVG, xử lý click, điều khiển ván cờ, undo, chế độ chơi |

Bộ sinh nước đi đã được kiểm tra bằng perft từ thế ban đầu: 44 / 1920 / 79666 / 3290240 (độ sâu 1–4), khớp với số liệu chuẩn của cờ tướng.
