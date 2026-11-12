# MyMemory (nhớ ngày sinh, ngày giỗ, ngày lễ) – Hướng dẫn cài đặt và sử dụng

## 0. Các file trong thư mục `D:\claude\file\MyMemory\`

| File | Vai trò |
|---|---|
| `index.html` | Toàn bộ giao diện và chức năng |
| `sw.js` | Service Worker: lưu web vào iPhone để dùng khi không có mạng |
| `manifest.webmanifest` | Thông tin app (tên **MyMemory**, icon) khi thêm vào màn hình chính |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | Icon của app (tờ lịch + trái tim + trăng khuyết) |
| `HUONG_DAN.md` | File hướng dẫn này (không cần upload) |

Cần upload **6 file** (tất cả trừ `HUONG_DAN.md`).

> **Dữ liệu người thân không nằm trong các file này.** Dữ liệu được lưu trong iPhone,
> đã mã hóa bằng mã PIN. Dữ liệu không bao giờ được đưa lên GitHub. Trên GitHub chỉ có code của app.

---

## Phần A. Đưa web lên GitHub Pages (làm trên máy tính, khoảng 5 phút)

> Dùng chung tài khoản GitHub với tuvung-web và Picards.
> MyMemory dùng **repository riêng** (`mymemory`), không upload chung với các app khác.

### A-1. Tạo repository
1. Đăng nhập **https://github.com**, bấm dấu **＋** ở góc trên bên phải → **New repository**.
2. Điền như sau:
   - **Repository name**: `mymemory` (chữ thường)
   - Chọn **Public**. Code là công khai, nhưng dữ liệu của anh không nằm ở đây.
   - **Add README**: để **Off**
3. Bấm nút xanh **Create repository**.

### A-2. Upload file
1. Trên trang **Quick setup**, bấm chữ **uploading an existing file**.
2. Mở thư mục `D:\claude\file\MyMemory\` bằng **Explorer（エクスプローラー）**.
3. Chọn 6 file (giữ **Ctrl** và bấm từng file):
   `index.html`, `sw.js`, `manifest.webmanifest`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`
   (**không** chọn `HUONG_DAN.md`).
4. Kéo thả vào khung **Drag files here**, đợi 6 tên file hiện ra.
5. Bấm nút xanh **Commit changes**.

### A-3. Bật GitHub Pages
1. Trong repository `mymemory`, bấm tab **⚙ Settings** → menu trái **Pages**.
2. **Build and deployment**:
   - **Source**: `Deploy from a branch`
   - **Branch**: chọn `main`, ô bên cạnh `/ (root)` → bấm **Save**.
3. Đợi 1–2 phút (tab **Actions**: dòng **pages build and deployment** có dấu ✓ xanh là xong).
4. Địa chỉ của app: **https://thaixaleme.github.io/mymemory/**

---

## Phần B. Cài vào iPhone

1. Mở **Safari** (bắt buộc dùng Safari), vào **https://thaixaleme.github.io/mymemory/**
2. Bấm nút **Share（共有）** (hình vuông có mũi tên lên) → **Add to Home Screen（ホーム画面に追加）** → **Add（追加）**.
3. Từ nay **luôn mở app bằng icon MyMemory** trên màn hình chính.

> ⚠️ Dữ liệu trong Safari và dữ liệu trong app (mở từ icon) là **2 nơi riêng**.
> Hãy tạo mã PIN và nhập dữ liệu **sau khi đã mở từ icon**.

---

## Phần C. Lần đầu mở app

1. **Tạo mã PIN 6 số** và nhập lại một lần để xác nhận.
   - ⚠️ **Quên mã PIN là mất dữ liệu.** Không có cách lấy lại, vì dữ liệu đã được mã hóa bằng mã PIN.
2. App hỏi **"Bật mở khóa bằng Face ID?"** → bấm **OK**, iPhone sẽ hỏi lưu passkey bằng Face ID → đồng ý.
   - Cần **iOS 18 trở lên**. iOS cũ hơn sẽ báo không hỗ trợ; khi đó anh vẫn dùng mã PIN bình thường.
   - Passkey tên **MyMemory** sẽ hiện trong app **Passwords（パスワード）**. Đừng xóa nó, nếu xóa thì Face ID không mở được (vẫn mở được bằng mã PIN).
   - Nếu để sau: vào **Cài đặt** → bật **Mở khóa bằng Face ID**.

---

## Phần D. Sử dụng

### D-1. Tab 📅 Sắp tới (màn hình chính)
- Trên cùng: hôm nay (thứ, ngày dương, ngày âm lịch).
- Banner: **🔔 Hôm nay có … ngày cần nhớ** / **⏰ Sắp đến: … ngày**.
- Màu thẻ:
  - 🔴 **Đỏ**: hôm nay
  - 🟠 **Cam**: còn 1–3 ngày
  - 🟡 **Vàng**: còn trong thời gian báo trước (mặc định 7 ngày)
  - Trắng: còn lâu
- Thẻ đỏ / cam / vàng hiện **câu nhắc** (ví dụ "Còn 3 ngày là đến sinh nhật vợ Lan").
- Số đỏ trên tab "Sắp tới" là số ngày đang "sắp đến".
- Bấm vào thẻ để sửa.

### D-2. Tab 👪 Người thân
- **＋ Thêm người**: tên, mối quan hệ (chọn gợi ý hoặc tự gõ), ngày sinh, ghi chú.
- **Ngày sinh / ngày mất**: chọn **Dương lịch** hoặc **Âm lịch**.
  - Năm có thể để trống. Có năm thì app tính được tuổi (sinh nhật) hoặc giỗ năm thứ mấy.
  - Âm lịch có ô **Tháng nhuận**. Ngày giỗ hằng năm luôn tính theo **tháng thường**. Tháng âm năm đó chỉ có 29 ngày thì ngày 30 tính là ngày 29.
  - Bên dưới ô nhập hiện ngày quy đổi (ví dụ "= Âm lịch 29/9 năm Canh Ngọ") để kiểm tra.
- Bật **🕯️ Đã mất** để nhập ngày mất. App sẽ nhắc ngày giỗ, và mặc định tắt nhắc sinh nhật (bật lại được).

### D-3. Tab 🎉 Ngày lễ
- Có sẵn các ngày lễ: 8/3, 20/10, 14/2, Tết, Vu Lan, Trung thu, Ngày của Mẹ, Ngày của Cha…
- Bật hoặc tắt nhắc bằng công tắc bên phải.
- **＋ Thêm ngày lễ / kỷ niệm**: ví dụ ngày cưới. Nhập **năm bắt đầu** thì `{nam}` = kỷ niệm năm thứ mấy.
- Kiểu **Theo thứ**: ví dụ "Chủ nhật thứ 2 của tháng 5" (Ngày của Mẹ).

### D-4. Câu nhắc tự đặt
Mỗi ngày (sinh nhật, ngày giỗ, ngày lễ) có phần **🔔 Nhắc nhở**:
- **Báo "sắp đến" trước bao nhiêu ngày**: để trống = theo cài đặt chung (7 ngày).
- **Câu nhắc khi sắp đến** và **Câu nhắc đúng ngày**: để trống = dùng câu mặc định (chữ mờ trong ô).
- Các chỗ trống app tự điền (bấm nút để chèn):

| Chỗ trống | Ý nghĩa | Ví dụ |
|---|---|---|
| `{n}` | số ngày còn lại | 3 |
| `{ten}` | tên | Lan |
| `{qh}` | mối quan hệ | vợ |
| `{tuoi}` | tuổi tròn (cần năm sinh) | 36 |
| `{nam}` | giỗ năm thứ / kỷ niệm năm thứ | 11 |
| `{ngay}` | ngày dương | 15/11 |
| `{am}` | ngày âm | 29/9 |

Ví dụ: `Còn {n} ngày là đến sinh nhật {qh} {ten} – tròn {tuoi} tuổi, nhớ mua quà!`
→ "Còn 3 ngày là đến sinh nhật vợ Lan – tròn 36 tuổi, nhớ mua quà!"
Bên dưới có phần **Xem trước** để kiểm tra.

### D-5. Tab ⚙️ Cài đặt
- **Báo "sắp đến" trước bao nhiêu ngày** (mặc định 7).
- **Hiện số trên icon app**: cần cho phép thông báo. Số chỉ cập nhật khi mở app.
- **Tự khóa app**: ngay khi rời app / sau 1 / 5 / 15 phút.
- **Mở khóa bằng Face ID**, **Đổi mã PIN**, **Khóa ngay** (hoặc bấm 🔒 trên thanh trên cùng).
- Nhập sai mã PIN 5 lần thì phải chờ 30 giây. Mỗi lần sai tiếp theo, thời gian chờ tăng gấp đôi.

---

## Phần E. Thêm vào Lịch iPhone (để được báo cả khi không mở app)

MyMemory chỉ hiện nhắc nhở **khi anh mở app**. Muốn iPhone tự báo trên màn hình khóa, hãy đưa các ngày vào app **Lịch（カレンダー）**:

1. **Cài đặt** → **📅 Thêm vào Lịch iPhone**: chọn số năm (mặc định 10) và giờ báo (mặc định 7:00).
2. Bấm **📤 Tạo file lịch** → **OK** → bảng chia sẻ hiện ra → chọn **Save to Files（"ファイル"に保存）** → lưu.
3. Mở app **Files（ファイル）**, bấm vào file `MyMemory.ics` → bấm **Add All（すべてを追加）**.
   - Nên tạo trước một lịch riêng tên **MyMemory** trong app Lịch (Lịch → **Calendars（カレンダー）** → **Add Calendar（カレンダーを追加）**) rồi chọn lịch đó khi thêm.
     Khi cần làm lại, chỉ cần xóa lịch MyMemory là xóa hết các sự kiện cũ.
4. Mỗi ngày có 2 lần báo: **trước N ngày** (số ngày báo trước) và **đúng ngày**, vào giờ đã chọn.

- Ngày âm lịch được đổi sẵn sang ngày dương cho từng năm.
- **Thêm / sửa người thì phải tạo lại file.** Xóa lịch MyMemory cũ trước, rồi thêm file mới, để không bị trùng.
- ⚠️ App Lịch **không có mã PIN**: ai mở được iPhone thì xem được các sự kiện này. Ô "Không ghi phần ghi chú vào Lịch" mặc định bật.

---

## Phần F. Sao lưu và khôi phục

- **Cài đặt** → **📤 Sao lưu ra file** → **Save to Files（"ファイル"に保存）** → nên lưu vào **iCloud Drive**.
- File sao lưu được **mã hóa bằng mã PIN lúc sao lưu**. Người khác mở file cũng không đọc được.
- **📥 Khôi phục từ file** → chọn file → nhập **mã PIN lúc tạo bản sao lưu** → xác nhận thay dữ liệu.
- Nên sao lưu sau mỗi lần thêm hoặc sửa nhiều. Nếu iPhone hỏng, bị đổi máy hay lỡ xóa app, chỉ có file sao lưu cứu được dữ liệu.

---

## Phần G. Cập nhật app (khi có bản mới)

1. GitHub → repository `mymemory` → **Add file** → **Upload files** → kéo thả file đã sửa → **Commit changes**.
2. Mở app trên iPhone **2 lần** (lần 1 tải bản mới ở nền, lần 2 mới thấy thay đổi).
   Dữ liệu không mất khi cập nhật.

---

## Phần H. Lưu ý về bảo mật

- Dữ liệu được mã hóa **AES-256**. Khóa được tạo từ mã PIN, còn khi dùng Face ID thì từ passkey.
- Mã PIN chỉ có 6 số. Chặn đoán mã trong app (chờ khi nhập sai) giúp chống người xem trộm. Tuy nhiên người rành kỹ thuật, nếu lấy được file dữ liệu ra khỏi iPhone, về lý thuyết vẫn có thể thử hết 1 triệu mã trên máy tính. Vì vậy hãy khóa iPhone bằng mật mã như bình thường.
- **Xóa app khỏi màn hình chính = xóa luôn dữ liệu.** Hãy sao lưu trước.
- Không xóa dữ liệu website trong **Settings（設定）** → **Safari**. Việc đó có thể xóa dữ liệu của app.

---

## Những điểm chưa thử trên iPhone thật

Đã chạy thử trên máy tính (Chrome): âm lịch, mã PIN, mã hóa, thêm/sửa, xuất file lịch, sao lưu/khôi phục. **Chưa thử trên iPhone thật** các mục sau:
- Face ID (passkey + PRF, cần iOS 18+)
- Số trên icon app
- Bảng chia sẻ khi lưu file sao lưu / file lịch, và mở file `.ics` trong app Tệp
