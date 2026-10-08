# ✈ Sky Team

Game **Sky Team** (Luc Rémond, Le Scorpion Masqué, Spiel des Jahres 2024) cho 2 người, chơi ngay trên trình duyệt:
Phi công và Cơ phó cùng hạ cánh máy bay xuống sân bay YUL Montréal-Trudeau bằng xúc xắc, không được nói về xúc xắc.

Chơi online: https://tranviethoang99.github.io/sky-team/

## Chế độ chơi
- **Bay cùng máy**: nhập tên, chọn ghế (Phi công / Cơ phó), bấm *Bay cùng máy*.
  Máy chỉ nhìn thấy xúc xắc của nó và bảng điều khiển chung, không nhìn trộm xúc xắc của bạn.
- **Online 2 người**: bấm *Tạo phòng*, gửi mã hoặc link cho đồng đội; đồng đội nhập mã và bấm *Vào phòng*
  (người vào nhận ghế còn lại). Người tạo phòng phải **giữ tab mở**, vì máy chủ phòng giữ trạng thái chuyến bay.
  Đầu mỗi vòng có ô chat để bàn chiến thuật; khi đã tung xúc xắc thì chat bị khoá.

## Luật tóm tắt (bản cơ bản, YUL Montréal)
- 7 vòng, mỗi vòng hạ 1000 ft (6000 → 0). Vòng 7 là vòng hạ cánh.
- Mỗi vòng: bàn chiến thuật, tung 4 xúc xắc (giấu kín), rồi thay phiên đặt từng viên. Mỗi người bắt buộc đặt 1 viên vào **Trục** và 1 viên vào **Động cơ**.
- **Trục** nghiêng về phía người đặt số lớn hơn, bằng hiệu hai số; lệch 3 là rơi máy bay.
- **Động cơ**: tổng ≤ vạch xanh thì đứng yên, tới vạch cam thì tiến 1 ô, quá vạch cam thì tiến 2 ô.
  Tiến lên khi ô hiện tại còn máy bay là va chạm; đang ở sân bay mà còn tiến là bay quá sân bay.
- **Radio** dẹp máy bay trên đường tiếp cận; **Càng đáp** đẩy vạch xanh, **Cánh tà** đẩy vạch cam; **Phanh** 2 → 4 → 6;
  **Tập trung** cho cà phê để chỉnh xúc xắc ±1; 2 lượt **tung lại** ở 6000 ft và 2000 ft.
- Thắng khi cuối vòng 7: không còn máy bay trên đường tiếp cận, đủ 3 càng đáp và 4 cánh tà, trục thăng bằng, tốc độ ≤ lực phanh.

## Cách bấm
- Bấm một xúc xắc của bạn (hoặc phím 1–4): các ô đặt được sáng xanh, ô viền đỏ là nước đi làm thua ngay (sẽ hỏi lại trước khi đặt).
- Rê chuột vào ô để xem trước kết quả; trên điện thoại chạm một lần để xem, chạm lần nữa để đặt.
- Nút **− / +** cạnh xúc xắc đang chọn tiêu cà phê để đổi giá trị.

## Kỹ thuật
Một file `index.html` duy nhất. Kết nối P2P bằng [PeerJS](https://peerjs.com/), cùng khung với Quoridor, Azul và Splendor Duel.
Luật lấy từ rulebook chính thức; số máy bay trên đường tiếp cận YUL (0, 0, 1, 2, 1, 3, 2) đối chiếu với bản Board Game Arena.
Máy chấm điểm từng nước đặt bằng heuristic, có tính kỳ vọng theo xúc xắc chưa biết của đồng đội và mô phỏng khi quyết định tung lại;
hai máy bay cùng nhau hạ cánh thành công khoảng 2/3 số chuyến.
Chạy thử: `npx http-server sky-team -p 5189`.
