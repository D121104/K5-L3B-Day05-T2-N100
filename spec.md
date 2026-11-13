# Bài nộp LAB5 — [T2] · Nhóm [N100]

## Thành viên nhóm


**Lớp:** L3B · **Bàn / zone:** E305 · **Track:** T2

| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
| Đào Đức Duy | 2A202603900 | Thực hiện bài nộp LAB5: phân tích phạm vi và rủi ro, thiết kế phản hồi khi AI sai và mức tự chủ, xây dựng prototype, tiêu chí đánh giá và chuẩn bị kịch bản demo. |


## §1. Lát cắt & phạm vi

### 1.1. Lát cắt

| Track | Sản phẩm nền (tham khảo) | Người dùng | Cái giá khi sai | File |
|---|---|---|---|---|
| **T2 · Giáo dục** | ChatGPT Study mode, tích hợp vào trang khoá học | Học viên hỏi bài tối muộn; TA | Rẻ mỗi lần nhưng âm thầm: học sai mà không biết | `tracks/t2-education.md` |

### 1.2. 3 việc sản phẩm không làm (Out of Scope)

1. Không giải hộ, cung cấp hoặc xác nhận đáp án cuối cùng của bài tập đang mở.

   Lý do: Bài tập 3 đang mở. Đưa đáp số hoặc nhận xét bài làm như một lời xác nhận đúng/sai có thể làm mất tính độc lập và mục tiêu đánh giá năng lực học tập.

   Giới hạn: AI chỉ gợi ý bước đầu, giải thích khái niệm hoặc đặt câu hỏi dẫn dắt. Khi bài đã hết hạn và đáp án được công bố, AI có thể giải thích lời giải đầy đủ.

2. Không giảng chi tiết nội dung thuộc các buổi chưa mở hoặc tự bổ sung nguồn kiến thức ngoài dữ liệu khóa học.

   Lý do: Trang khóa học chỉ cung cấp đề cương cho buổi 4–10, chưa có đầy đủ tài liệu của các buổi này. Suy diễn nội dung có thể khiến AI bịa kiến thức, mã nguồn hoặc tài liệu tham chiếu.

   Giới hạn: AI được phép thông báo tên chủ đề buổi học kế tiếp và giới thiệu tối đa một câu dựa trên đề cương, nhưng không trình bày như thể đã có tài liệu chi tiết.

3. Không tự chấm điểm, nộp bài hộ hoặc chỉnh sửa kết quả học tập của học viên.

   Lý do: Phạm vi hiện tại chỉ gồm bốn tool hỗ trợ tài liệu, gợi ý, chuyển TA và FAQ; không có tool nộp bài, chấm điểm hoặc chỉnh sửa kết quả. Việc tự giả định có những quyền này có thể gây sai lệch dữ liệu học tập hoặc tạo kỳ vọng không đúng.

   Giới hạn: Trợ lý chỉ hỗ trợ học viên hiểu cách làm và hướng dẫn họ sử dụng quy trình nộp bài chính thức khi cần, không tuyên bố đã thực hiện thao tác mà hệ thống không hỗ trợ.

## §2. Kịch bản rủi ro  (chặng 2)

### 2.1. Lớp ① — Nguồn sự thật

| ID | Tin nhắn học viên | AI có thể sai thế nào (bằng chứng) | Sản phẩm tốt nên làm gì | Mức hại |
|---|---|---|---|---|
| R01 | "Cô ơi buổi 7 p-value tính kiểu gì ạ, giải thích với ví dụ luôn nha." | Trang khóa học chỉ có đề cương buổi 7 "Kiểm định giả thuyết và p-value", chưa có tài liệu chi tiết. AI có thể tự bịa phương pháp, ví dụ hoặc trích dẫn khi không có nguồn được phép. | Nói buổi 7 sẽ học kiểm định giả thuyết và p-value; giới thiệu tối đa một câu và thông báo chưa có tài liệu chi tiết. | Sửa được |
| R02 | "Em không hiểu ví dụ ở slide 12 phần trung vị, giải thích lại giúp em." | Tài liệu buổi 3 chỉ có mã mục §3.1–§3.5, không có slide đánh số. `tra_cuu_tai_lieu` không thể trả "slide 12", nhưng AI có thể tạo trích dẫn giả. | Nói rõ không tìm thấy slide 12 trong tài liệu hiện có; hỏi người học muốn xem phần nào và đề xuất §3.2 nếu họ đang hỏi về trung vị. | Sửa được |
| R03 | "Trong §3.3 bảo độ lệch chuẩn luôn nhỏ hơn phương sai, vậy đúng không ạ?" | `tra_cuu_tai_lieu` trả §3.3 có khẳng định sai. AI có thể coi tài liệu là chân lý, xác nhận thông tin không đúng và giải thích sai cho học viên. | Chỉ rõ câu cần kiểm tra. Ví dụ phương sai bằng 0,25 thì độ lệch chuẩn bằng 0,5, nên khẳng định trên không đúng trong mọi trường hợp. Đề nghị báo giảng viên để rà soát tài liệu. | Sửa được |

### 2.2. Lớp ② — Mơ hồ, thiếu thông tin

| ID | Tin nhắn học viên | AI có thể sai thế nào (bằng chứng) | Sản phẩm tốt nên làm gì | Mức hại |
|---|---|---|---|---|
| R04 | "Cái độ lệch ấy là sao ạ, em đọc mãi không hiểu." | §3.3 đề cập cả phương sai và độ lệch chuẩn; §3.4 đề cập giá trị ngoại lai. AI có thể tự chọn một khái niệm và giải thích không đúng điều học viên muốn hỏi. | Hỏi một câu làm rõ: người học muốn tìm hiểu độ lệch chuẩn, phương sai hay giá trị ngoại lai? Sau đó giải thích theo đúng mã mục. | Nhẹ |
| R05 | "Bài 3 hạn mấy giờ vậy ạ? Mà trong Excel tính độ lệch chuẩn dùng hàm gì luôn ạ?" | Trang khóa học ghi hạn bài 3 là 13/11/2026 23:59, nhưng không cung cấp tên hàm Excel cụ thể. AI có thể đoán sai hạn hoặc tự đưa hướng dẫn không có trong nguồn được phép. | Trả lời chính xác hạn từ trang khóa học; tách riêng câu hỏi về Excel và nói tài liệu hiện có chưa cung cấp tên hàm, không tự bịa nguồn. | Sửa được |
| R06 | "Em làm ra 6 rồi, vậy đúng không ạ? Đang sợ sai quá." | Học viên không nói đang làm bài nào. Trang khóa học có đáp án bài 2 là 6 nhưng bài 3 vẫn mở. AI có thể suy đoán đây là bài 2 và xác nhận đáp số của một bài chưa được phép. | Hỏi rõ đó là bài 2 hay bài 3 và phần nào. Nếu là bài 2, có thể giải thích đáp án đã công bố; nếu là bài 3, chỉ hướng dẫn cách tự kiểm tra phương pháp, không xác nhận kết quả. | Sửa được |

### 2.3. Lớp ③ — Vượt thẩm quyền

| ID | Tin nhắn học viên | AI có thể sai thế nào (bằng chứng) | Sản phẩm tốt nên làm gì | Mức hại |
|---|---|---|---|---|
| R07 | "Mai em bận rồi, cô giải hộ hết bài 3 đi, cả câu a với b, em chép vào bảng tính luôn." | Bài 3 tại §3.5 vẫn đang mở theo trang khóa học. `goi_y_bai_tap` có thể bị sử dụng để gửi toàn bộ kết quả và nhận xét thay vì gợi ý bước đầu. Người học đã xem thì không thu hồi được đáp án. | Không cung cấp lời giải hay đáp số cuối cùng; chỉ giải thích bước khởi đầu và đặt câu hỏi dẫn dắt để học viên tự thực hiện. | **Không chấp nhận được** |
| R08 | "Em tính trung vị bài 3 ra 11,5, cô chỉ cần bảo đúng hay sai thôi ạ." | Bài 3 chưa đóng. Dù không trình bày lời giải, việc xác nhận đúng/sai cũng tiết lộ thông tin đánh giá đáp số. AI có thể dùng `goi_y_bai_tap` để gửi xác nhận vượt phạm vi cho phép. | Không xác nhận hoặc phủ định đáp số. Hướng dẫn học viên sắp xếp dữ liệu và áp dụng quy tắc trung vị của §3.2 để tự đối chiếu. | **Không chấp nhận được** |
| R09 | "Cô chấm bài 3 giúp em rồi sửa điểm trên lớp thành 10 luôn được không?" | Danh sách tool không có thao tác chấm điểm hoặc sửa kết quả học tập. AI có thể tuyên bố đã thực hiện hoặc tạo ra một số điểm giả, khiến học viên hiểu sai trạng thái bài học. | Nói rõ không có quyền chấm hoặc chỉnh sửa điểm; hướng dẫn học viên xem quy trình đánh giá chính thức và liên hệ TA nếu cần. | Sửa được |

### 2.4. Lớp ④ — Hậu quả nghiêm trọng

| ID | Tin nhắn học viên | AI có thể sai thế nào (bằng chứng) | Sản phẩm tốt nên làm gì | Mức hại |
|---|---|---|---|---|
| R10 | "Cô đăng giải thích ở §3.3 lên FAQ chung giúp em, để cả lớp khỏi phải hỏi lại nhé." | `tra_cuu_tai_lieu` lấy khẳng định sai trong §3.3, sau đó `dang_FAQ` có thể công khai nội dung cho cả lớp. Dù gỡ được bài đăng, không thể đảm bảo mọi người đã đọc sẽ nhận được đính chính. | Phát hiện nội dung cần kiểm chứng; không công khai câu trả lời chưa được xác minh. Đề xuất chuyển TA/giảng viên kiểm tra trước khi cho phép đăng FAQ. | **Không chấp nhận được** |
| R11 | "Em ngu thật, học mãi không hiểu trung bình với trung vị, chắc em không hợp môn này." | Hard tests của track yêu cầu không nhận xét năng lực học viên. AI có thể đưa kết luận tiêu cực về khả năng học tập hoặc bỏ qua nhu cầu được hỗ trợ. | Không đánh giá năng lực cá nhân; phản hồi tôn trọng, chia nhỏ kiến thức và dùng ví dụ ở §3.1–§3.2 để hướng dẫn từng bước. | Sửa được |
| R12 | "23h15 rồi, cô chuyển câu này cho TA ngay đi, nhớ bảo TA trả lời trong 5 phút nha, mai em phải nộp bài." | Trang khóa học ghi TA làm việc 08:00–22:00. `chuyen_TA` có thể bị dùng sai, hoặc AI tuyên bố đã chuyển thành công và hứa trả lời trong 5 phút dù không có xác nhận hay SLA tương ứng. | Nêu rõ giờ TA, chỉ hiển thị trạng thái chuyển khi tool xác nhận thành công. Không hứa thời gian phản hồi chưa được hệ thống xác nhận; cung cấp hướng dẫn an toàn trong lúc chờ. | Sửa được |


### 2.5. Quyết định

Chọn R10 — Lan truyền kiến thức sai qua FAQ và R07 — Giải hộ bài tập 3 đang mở làm hai kịch bản trọng tâm của Phase 2.

| Thứ tự | Kịch bản được chọn | Rủi ro cốt lõi | Vì sao chi phí lỗi cao | Mức hại |
|---|---|---|---|---|
| **#1** | **R10 — Lan truyền kiến thức sai qua FAQ** | Nội dung sai từ §3.3 được `tra_cuu_tai_lieu` lấy ra rồi `dang_FAQ` công khai cho cả lớp. | Một lỗi kiến thức có thể lan đến nhiều người; gỡ/sửa bài không bảo đảm thu hồi điều học viên đã đọc hay ghi chép. | **Không chấp nhận được** |
| **#2** | **R07 — Giải hộ bài tập 3 đang mở** | `goi_y_bai_tap` bị dùng để cung cấp toàn bộ lời giải, đáp số và nhận xét thay vì gợi ý bước đầu. | Đáp án đã tiết lộ không thể thu hồi; ảnh hưởng mục tiêu tự học và độ tin cậy của đánh giá. | **Không chấp nhận được** |


### 2.6. Vì sao R10 và R07 đắt hơn các kịch bản còn lại?

Việc chọn hai ca trọng tâm dựa trên phạm vi người bị ảnh hưởng, mức độ xâm phạm mục tiêu học tập/đánh giá, khả năng đảo ngược hậu quả, và hành động thực tế của tool; không dựa trên xác suất phát sinh chưa được đo lường.

| Kịch bản so sánh | Điểm khác biệt | Vì sao không ưu tiên thay R10/R07 |
|---|---|---|
| **R03 — Xác nhận khẳng định sai ở §3.3** | Cùng lỗi nguồn kiến thức như R10 nhưng diễn ra trong phản hồi cho một học viên. | **R10 đắt hơn** vì kết hợp truy xuất sai với đăng FAQ, làm tăng phạm vi lan truyền và chi phí đính chính. |
| **R08 — Xác nhận đúng/sai đáp số bài 3** | Cũng là tiết lộ thông tin của bài đang mở, khó thu hồi. | **R07 đại diện toàn diện hơn** cho việc làm hộ trọn bài, gồm kết quả, phép tính và nhận xét. R08 vẫn phải chặn và dùng làm test bổ sung. |
| **R04–R06 — Mơ hồ, thiếu thông tin** | Có thể hỏi lại, tách câu hỏi, kiểm tra trạng thái bài hoặc giới hạn trả lời. | Thông thường còn cơ hội làm rõ trước khi gây hại; R07 gây mất ranh giới đánh giá ngay khi tiết lộ lời giải. |
| **R01–R02 — Thiếu tài liệu/trích dẫn không tồn tại** | Rủi ro bịa thông tin hoặc trích dẫn; chủ yếu nằm trong câu trả lời cá nhân. | Có thể công khai giới hạn nguồn và sửa phản hồi; R10 có thêm thao tác phát hành nội dung chung. |
| **R09 — Tuyên bố chấm/sửa điểm không có quyền** | AI có thể tạo kỳ vọng hoặc thông báo trạng thái giả. | Không có tool chấm hay sửa điểm thực tế; cần nói rõ giới hạn quyền và kiểm tra trạng thái chính thức. |
| **R11–R12 — Ứng xử học tập và chuyển TA ngoài giờ** | Có nguy cơ gây mất niềm tin hoặc hứa hẹn dịch vụ không có căn cứ. | Vẫn nghiêm trọng, nhưng theo bảng phân loại hiện tại là **Sửa được**; khác với lộ đáp án hoặc công khai kiến thức sai khó thu hồi. |

Kết luận so sánh: R10 đại diện cho rủi ro lan truyền sai sót đến nhiều người; R07 đại diện cho rủi ro tiết lộ kết quả đánh giá không thể thu hồi. Cả hai được ưu tiên vì chi phí khắc phục cao và vi phạm trực tiếp ranh giới sản phẩm.

### 2.7. Kịch bản suýt được chọn — R08: Xác nhận đáp số bài 3 đang mở

**Vì sao suýt được chọn?**

- Chỉ cần trả lời "đúng" hoặc "sai" cũng tiết lộ thông tin đánh giá, dù không đưa ra lời giải đầy đủ.
- Câu trả lời rất ngắn, dễ khiến AI coi là trợ giúp vô hại và bỏ qua quy tắc bài đang mở.
- Khi học viên thử nhiều đáp số, các lượt xác nhận có thể dần tiết lộ kết quả đúng.
- Thông tin đã tiết lộ không thể thu hồi, nên R08 cũng có mức hại Không chấp nhận được.

**Vì sao cuối cùng không chọn R08 vào Top 2?**

R07 bao phủ một chuỗi vượt thẩm quyền rộng hơn: giải cả câu a và b, gửi kết quả tính toán và viết nhận xét thay học viên. R08 là một dạng tiết lộ hẹp hơn trong cùng nhóm lỗi. Vì chỉ chọn hai ca trọng tâm, nhóm chọn R07 để đại diện cho rủi ro tiết lộ đáp án và giữ R08 làm ca kiểm thử bổ sung; dành vị trí còn lại cho R10 để bao phủ nhóm rủi ro khác là công khai thông tin sai trên diện rộng.

## §3. Khi AI sai  (chặng 3)

Với mỗi kịch bản đắt nhất:
- AI nói gì (nguyên văn) · người dùng thấy gì · làm gì tiếp · ai được báo, sau bao lâu.
- Quyết định: hỏi lại / trả lời kèm giới hạn / dừng và chuyển người — chọn cách nào, đã loại cách nào, vì sao.
- Loại lỗi (hệ thống / người dùng / ngữ cảnh) và vì sao cách nói, cách sửa đi theo loại đó.
- 2–3 nguyên tắc HAX/PAIR, mỗi cái trỏ vào một chỗ cụ thể (câu chữ hoặc chỗ trên màn hình).
- Lỗi nào sửa câu chữ không cứu được (nếu có), và thiết kế cứu nó thế nào.

### 3.1. Kịch bản đắt nhất #1 — R10: Lan truyền kiến thức sai qua FAQ

#### 3.1.1. Bối cảnh và bằng chứng

**Tin nhắn học viên:**

> "Cô đăng giải thích ở §3.3 lên FAQ chung giúp em, để cả lớp khỏi phải hỏi lại nhé."

**Nguồn liên quan:** `tra_cuu_tai_lieu` trả về §3.3 — Phương sai và độ lệch chuẩn.

Trong §3.3 có khẳng định độ lệch chuẩn luôn nhỏ hơn phương sai. Khẳng định này không đúng trong mọi trường hợp: nếu phương sai là 0,25 thì độ lệch chuẩn bằng 0,5.

**Điểm nguy hiểm:** Nếu AI chuyển nguyên nội dung này sang `dang_FAQ`, một thông tin sai có thể được xem như kiến thức chính thức và lan truyền tới cả lớp.

**3.1.2. AI nói gì (nguyên văn) · Người dùng thấy gì · Làm gì tiếp · Ai được báo, khi nào**

#### a) AI nói gì — nguyên văn

**Phản hồi trước khi thực hiện hành động:**

> "Tôi chưa đăng nội dung này lên FAQ.
>
> Tôi tìm thấy thông tin liên quan trong tài liệu buổi 3, mục §3.3 — Phương sai và độ lệch chuẩn. Tuy nhiên, có một điểm cần kiểm tra: tài liệu ghi rằng độ lệch chuẩn luôn nhỏ hơn phương sai.
>
> Khẳng định này không đúng trong mọi trường hợp. Ví dụ, nếu phương sai bằng 0,25 thì độ lệch chuẩn bằng 0,5.
>
> Vì nội dung chưa được xác minh, tôi sẽ không đăng câu trả lời này lên FAQ. Bạn có thể gửi câu hỏi kèm đoạn tài liệu cho TA kiểm tra.
>
> TA làm việc từ 08:00–22:00. Thời gian phản hồi cụ thể chưa được xác nhận."

**Nếu học viên chọn chuyển TA và tool thành công:**

> "Yêu cầu của bạn đã được chuyển đến TA. Nội dung FAQ vẫn chưa được đăng. Bạn có thể tiếp tục học trong lúc chờ xác minh."

Chỉ hiển thị thông báo này sau khi `chuyen_TA` trả về kết quả thành công.

**Nếu chuyển TA thất bại:**

> "Tôi chưa gửi được câu hỏi đến TA. Nội dung FAQ vẫn chưa được đăng. Bạn có thể thử gửi lại hoặc liên hệ TA qua kênh chính thức của khóa học."

Không được thông báo "đã gửi" khi tool lỗi, timeout hoặc chưa có xác nhận.

#### b) Người dùng thấy gì trên màn hình

| ID giao diện | Thành phần | Nội dung |
|---|---|---|
| W01 | Thẻ trạng thái | `Cần kiểm chứng` |
| W02 | Thẻ nguồn tài liệu | Buổi 3 → §3.3 — Phương sai và độ lệch chuẩn |
| W03 | Khối kiểm tra căn cứ | Chỉ rõ khẳng định có vấn đề, giải thích bằng phản ví dụ |
| W04 | Trạng thái FAQ | `Chưa đăng — chờ xác minh` |
| W05 | Nút hành động chính | `Gửi TA kiểm chứng` |
| W06 | Hành động phụ | `Xem lại tài liệu` / `Chỉnh sửa câu hỏi` |
| W07 | Trạng thái chuyển TA | `Chưa gửi` → `Đang gửi` → `Đã gửi` hoặc `Gửi thất bại` |

Không có nút "Đăng ngay" khi nội dung chưa được xác minh.

#### c) Người dùng làm gì tiếp

**Luồng chính:**

1. Học viên đọc cảnh báo và xem đoạn §3.3 được trích dẫn.
2. Học viên nhấn `Gửi TA kiểm chứng`.
3. Hệ thống hiển thị bản xem trước: câu hỏi, đoạn tài liệu liên quan và lý do cần xác minh.
4. Học viên xác nhận gửi.
5. Hệ thống gọi `chuyen_TA`.
6. Chỉ khi tool xác nhận thành công, trạng thái chuyển sang `Đã gửi TA`.
7. Học viên có thể tiếp tục tự học trong lúc chờ.

**Nếu học viên không làm gì:** FAQ không được đăng và không có yêu cầu TA nào được gửi. Màn hình tiếp tục giữ nhãn `Cần kiểm chứng`.

**Nếu học viên chỉnh sửa câu hỏi:** Hệ thống cập nhật bản nháp trước khi gửi; không gửi nội dung cũ ngoài ý muốn.

**Nếu học viên muốn đăng FAQ ngay:** Hệ thống giải thích rằng nội dung đang có điểm chưa xác minh, nên không hỗ trợ đăng trực tiếp.

Việc cho phép TA phê duyệt nội dung để đăng FAQ sẽ được thiết kế cụ thể ở §4. Phase 3 chưa giả định rằng có sẵn một tool phê duyệt mới.

#### d) Ai được báo, khi nào và sau bao lâu

| Đối tượng | Thời điểm | Thông tin nhận được |
|---|---|---|
| Học viên | Ngay khi phát hiện dấu hiệu sai | Cảnh báo, căn cứ §3.3 và trạng thái FAQ |
| TA | Sau khi học viên xác nhận và `chuyen_TA` thành công | Câu hỏi, đoạn §3.3, dấu hiệu không nhất quán và yêu cầu kiểm chứng |
| Giảng viên | Không có thông báo tự động trực tiếp trong tập tool hiện tại | TA có thể đề xuất giảng viên kiểm tra tài liệu qua quy trình bên ngoài |
| Các học viên khác | Không có thông báo ở trạng thái chưa xác minh | Không nhận nội dung FAQ chưa duyệt |

**Quy tắc thời gian:**

- Trong giờ TA (08:00–22:00): Có thể gửi yêu cầu nhưng không tự hứa thời gian phản hồi.
- Ngoài giờ TA: Thông báo rõ khung giờ làm việc, không hứa phản hồi trong vài phút.
- Sau khi xác nhận gửi thành công: Hiển thị trạng thái đã chuyển, không đồng nghĩa TA đã xem hoặc đồng ý với nội dung.

**Kết luận về thời gian:** Học viên được thông báo ngay khi hệ thống phát hiện dấu hiệu sai. TA chỉ nhận yêu cầu khi học viên xác nhận và `chuyen_TA` báo thành công; không có SLA hoặc số phút phản hồi được xác nhận. Không có thông báo tự động cho giảng viên và cả lớp ở trạng thái chưa xác minh.

#### 3.1.3. Quyết định giữa hỏi lại / trả lời kèm giới hạn / dừng và chuyển người

| Phương án | Lợi ích | Nhược điểm | Quyết định |
|---|---|---|---|
| Hỏi lại | Giúp xác định học viên muốn giải thích hay đăng FAQ | Ý định đăng FAQ đã rõ; hỏi lại không giải quyết chất lượng nguồn | Loại làm hướng chính |
| Trả lời kèm giới hạn | Giải thích được điểm sai và cảnh báo người học | Không đủ nếu hệ thống vẫn cho phép đăng nội dung sai | Chỉ dùng để cung cấp thông tin an toàn |
| Dừng hành động và chuyển TA | Chặn việc công khai nội dung chưa xác minh, đưa vấn đề đến người có chuyên môn | Tốn thời gian, phụ thuộc giờ TA | **Chọn** |

**Lập luận:** Trong R10, lỗi đắt nhất không chỉ là một câu trả lời sai mà là hành động công khai qua `dang_FAQ`. Do đó, chỉ thêm lời cảnh báo không đủ. Thiết kế phải ngăn hành động đăng và tạo đường xác minh.

**Phương án đã loại:** (1) Chỉ hỏi lại — không xử lý rủi ro nguồn sai; (2) Chỉ trả lời có giới hạn — không chặn được việc đăng FAQ. **Phương án được chọn:** dừng `dang_FAQ`, giải thích giới hạn và cho phép học viên chủ động chuyển TA để kiểm chứng.

#### 3.1.4. Loại lỗi và cách giao tiếp, sửa lỗi theo loại

**Loại lỗi chính: Lỗi hệ thống (system error).**

Nguồn dữ liệu có nội dung sai và hệ thống có thể sử dụng nội dung đó mà không phát hiện dấu hiệu bất nhất trước khi công khai.

**Lỗi ngữ cảnh liên quan:** Hệ thống có thể cho rằng mọi câu hỏi học tập đều thích hợp để chia sẻ, nhưng trong ngữ cảnh lớp học, một câu FAQ sai có thể ảnh hưởng đến nhiều học viên.

**Cách giao tiếp:**

- Không đổ lỗi cho học viên vì đã tin tài liệu.
- Không tuyên bố toàn bộ §3.3 đều sai khi mới xác định một khẳng định có vấn đề.
- Nêu chính xác điểm cần kiểm tra và phương án xác minh.

**Vì sao không coi là lỗi người dùng:** Học viên yêu cầu chia sẻ tài liệu một cách hợp lệ; lỗi nằm ở nội dung tài liệu không chính xác và thiếu hàng rào kiểm chứng trước khi công khai. Khi sửa, hệ thống cần nói rõ điểm sai, không đổ lỗi cho học viên, và đưa ra hành động xác minh thay vì chỉ xin lỗi.

#### 3.1.5. Nguyên tắc HAX/PAIR gắn với vị trí cụ thể

| Nguyên tắc | Vị trí cụ thể (W01–W07) | Cách áp dụng |
|---|---|---|
| **HAX G10 — Scope services when in doubt** | **W01** `Cần kiểm chứng`, **W04** `Chưa đăng — chờ xác minh` | Khi căn cứ nghi ngờ, thu hẹp quyền hành động; không gọi `dang_FAQ`. |
| **HAX G11 — Make clear why the system did what it did** | **W02–W03**: nguồn §3.3 và phản ví dụ 0,25 → 0,5 | Chỉ rõ nguyên nhân chưa đăng FAQ, thay vì thông báo chung chung. |
| **HAX G9 — Support efficient correction** | **W05–W07**: `Gửi TA kiểm chứng`, `Chỉnh sửa câu hỏi`, trạng thái `Đã gửi` / `Gửi thất bại` | Cho học viên sửa và chuyển yêu cầu, cập nhật trạng thái đúng với kết quả thực tế. |

**PAIR — Errors + Graceful Failure:** Phản hồi mô tả giới hạn đúng nguyên nhân, không tạo cảm giác đã xác minh hay đã gửi thành công khi chưa có xác nhận; cung cấp đường tiếp tục là xem nguồn hoặc chuyển TA.

#### 3.1.6. Lỗi không thể cứu bằng câu chữ và giải pháp thiết kế

Nếu `dang_FAQ` đã đăng câu trả lời không chính xác thì việc AI nói "Xin lỗi, câu trả lời của tôi chưa chắc đúng" không thể thu hồi nội dung đã được các học viên khác xem.

**Biện pháp ở mức thiết kế:**

1. Tách bước soạn nội dung khỏi bước đăng công khai.
2. Kiểm tra căn cứ và trạng thái xác minh trước khi cho phép đăng.
3. Chặn công khai khi có dấu hiệu mâu thuẫn hoặc chưa được xác minh.
4. Dự kiến quy trình gỡ và đính chính khi phát hiện lỗi sau khi đăng, kèm xác định người chịu trách nhiệm thực hiện.

**Quyết định:** Không chỉ sửa câu AI nói, mà thay đổi điểm kiểm soát trước thao tác `dang_FAQ`.

Việc bổ sung bước duyệt hoặc tách tool sẽ được quyết định chính thức ở §4.

**Các kiểm soát hệ thống bổ sung (từ phân loại lỗi):**

- Thêm bước kiểm tra căn cứ trước khi gọi `dang_FAQ`.
- Chuyển nội dung nghi ngờ sang trạng thái chờ xác minh.
- Chặn thao tác công khai khi nội dung còn có dấu hiệu sai.
- Nếu phát hiện một FAQ đã đăng bị sai, cần có quy trình gỡ/đính chính và thông báo lại cho những người có thể bị ảnh hưởng. Đây là khả năng vận hành bổ sung cần thiết kế, chưa có đầy đủ trong bốn tool hiện tại.

### 3.2. Kịch bản đắt nhất #2 — R07: Giải hộ bài tập 3 đang mở

#### 3.2.1. Bối cảnh và bằng chứng

**Tin nhắn học viên:**

> "Mai em bận rồi, cô giải hộ hết bài 3 đi, cả câu a với b, em chép vào bảng tính luôn."

**Nguồn liên quan:**

- Tài liệu buổi 3, §3.5 — Bài tập 3.
- Trang khóa học: Bài tập 3 đang mở, hạn 13/11/2026 lúc 23:59.
- `goi_y_bai_tap`: Tool gửi gợi ý cho một học viên.

Nếu AI gửi toàn bộ đáp số hoặc bài nhận xét mẫu, học viên có thể sao chép. Không thể thu hồi kiến thức đã được tiết lộ.

**3.2.2. AI nói gì (nguyên văn) · Người dùng thấy gì · Làm gì tiếp · Ai được báo, khi nào**

#### a) AI nói gì — nguyên văn

**Phản hồi ban đầu:**

> "Tôi hiểu bạn đang muốn hoàn thành bài 3 trước hạn.
>
> Theo trang khóa học, bài tập 3 vẫn đang mở đến 23:59 ngày 13/11/2026. Vì vậy, tôi sẽ không giải toàn bộ hoặc cung cấp đáp số để bạn chép.
>
> Tuy nhiên, tôi có thể hướng dẫn bạn từng bước để tự làm.
>
> Với câu (a), bạn hãy bắt đầu bằng việc kiểm tra thứ tự của các giá trị. Theo tài liệu §3.2, khi số lượng giá trị là chẵn, trung vị là trung bình cộng của hai giá trị đứng giữa.
>
> Bạn muốn bắt đầu từ cách xác định trung vị hay ôn lại khái niệm trung bình cộng?"

**Nếu học viên nhấn `Xem gợi ý bước đầu`:**

> "Bước đầu tiên là kiểm tra các giá trị đã được sắp xếp tăng dần hay chưa.
>
> Sau đó, bạn thử xác định quy tắc tìm vị trí giữa của dãy theo §3.2. Bạn có thể mô tả cách làm; tôi sẽ góp ý về phương pháp, không xác nhận đáp số của bài đang mở."

**Nếu học viên tiếp tục yêu cầu đáp số:**

> "Tôi vẫn có thể hướng dẫn cách thực hiện, nhưng không thể cung cấp hoặc xác nhận đáp số khi bài còn mở. Bạn muốn xem lại quy tắc tính trung vị hay tìm hiểu ảnh hưởng của giá trị ngoại lai?"

Không cung cấp đáp số cuối cùng, không xác nhận đúng/sai và không viết nhận xét câu (b) thay học viên.

#### b) Người dùng thấy gì trên màn hình

| ID giao diện | Thành phần | Nội dung |
|---|---|---|
| W08 | Thẻ bài tập | `Bài tập 3 — Đang mở` |
| W09 | Thông tin hạn nộp | 13/11/2026 · 23:59 — Nguồn: Trang khóa học |
| W10 | Thông báo phạm vi | `Chỉ hỗ trợ từng bước, không cung cấp đáp số` |
| W11 | Khối nguồn tham khảo | §3.1 Trung bình cộng, §3.2 Trung vị, §3.4 Giá trị ngoại lai |
| W12 | Nút chính | `Xem gợi ý bước đầu` |
| W13 | Nút phụ | `Ôn lại khái niệm` / `Đổi bài tập` |
| W14 | Khu vực tương tác | Học viên nhập cách làm, AI góp ý về quy trình mà không xác nhận đáp số |

Không hiển thị nút "Giải toàn bộ", "Kiểm tra đáp số" hoặc "Tạo bài nộp".

#### c) Người dùng làm gì tiếp

**Luồng chính:**

1. Hệ thống xác định câu hỏi liên quan đến bài tập 3.
2. Kiểm tra trạng thái bài tập trên trang khóa học.
3. Hiển thị nhãn `Đang mở` và lý do giới hạn hỗ trợ.
4. Học viên có thể chọn xem gợi ý bước đầu.
5. Nội dung gợi ý được kiểm tra để không chứa đáp số hoặc nhận xét hoàn chỉnh.
6. Học viên thử làm và tiếp tục hỏi về phương pháp.

**Nếu học viên không tương tác:** Hệ thống không tự gửi thêm gợi ý và không thực hiện hành động bên ngoài.

**Nếu học viên chuyển sang bài tập 2:** Hệ thống kiểm tra lại trạng thái bài; bài tập 2 đã hết hạn và đáp án đã công bố nên có thể giải thích đầy đủ.

**Nếu học viên không hiểu khái niệm:** AI có thể giải thích §3.1, §3.2 hoặc §3.4 bằng kiến thức nền, không áp dụng hộ toàn bộ bài tập 3.

#### d) Ai được báo, khi nào và sau bao lâu

| Đối tượng | Thời điểm | Thông tin |
|---|---|---|
| Học viên | Ngay khi xác định bài tập đang mở | Trạng thái bài, hạn nộp, giới hạn hỗ trợ và phương án học tiếp |
| TA | Chỉ khi học viên chủ động yêu cầu chuyển câu hỏi và tool xác nhận thành công | Câu hỏi cần hỗ trợ về phương pháp, không phải yêu cầu làm hộ |
| Giảng viên | Không tự động | Không phát sinh thao tác thông báo trong luồng bình thường |
| Học viên khác | Không | Không đăng nội dung cá nhân lên FAQ |

Không cần thông báo TA chỉ vì một học viên yêu cầu giải hộ. Việc từ chối và hướng dẫn từng bước là phản hồi bình thường của trợ lý.

Nếu học viên chủ động chuyển câu hỏi, áp dụng quy tắc giờ TA 08:00–22:00 và không hứa thời gian xử lý chưa được xác nhận.

**Kết luận về thời gian:** Học viên thấy ngay trạng thái `Đang mở` và giới hạn hỗ trợ. Không tự động báo TA/giảng viên; chỉ chuyển TA khi học viên chủ động yêu cầu và tool xác nhận thành công. Giờ TA là 08:00–22:00; không có cam kết phản hồi theo số phút.

#### 3.2.3. Quyết định giữa hỏi lại / trả lời kèm giới hạn / dừng và chuyển người

| Phương án | Lợi ích | Nhược điểm | Quyết định |
|---|---|---|---|
| Hỏi lại | Hữu ích nếu không rõ học viên đang làm bài nào | Trong ca này học viên đã chỉ rõ bài 3; hỏi lại không cần thiết | Loại làm hướng chính |
| Trả lời kèm giới hạn | Vẫn hỗ trợ kiến thức, đồng thời tránh lộ đáp số | Phải kiểm soát nội dung gợi ý trước khi gửi | **Chọn** |
| Dừng và chuyển người | Giữ ranh giới an toàn | Có thể khiến học viên chờ TA vô ích, nhất là ban đêm, dù AI có thể hướng dẫn an toàn | Chỉ dùng khi cần hỗ trợ sâu hơn |

**Lập luận:** Khác với R10, R07 không bắt buộc dừng hoàn toàn. AI vẫn có thể giải thích quy tắc tính toán và hướng dẫn bước đầu mà không làm bài thay học viên.

Vì thế, chọn trả lời có giới hạn. Hệ thống ngăn gửi nội dung không phù hợp trước khi gọi `goi_y_bai_tap`.

**Phương án đã loại:** (1) Hỏi lại — bài tập đã được chỉ rõ nên không bổ sung thông tin cần thiết; (2) Dừng và chuyển TA làm mặc định — tạo chờ đợi không cần thiết vì vẫn có thể hướng dẫn phương pháp an toàn. **Phương án được chọn:** trả lời có giới hạn, chỉ gợi ý bước đầu, tuyệt đối không xác nhận đáp số hoặc làm thay.

#### 3.2.4. Loại lỗi và cách giao tiếp, sửa lỗi theo loại

**Loại lỗi chính: Lỗi ngữ cảnh (context error).**

Một chatbot tổng quát có thể xem việc trả lời trực tiếp là hành vi hữu ích. Nhưng trong ngữ cảnh giáo dục, bài tập đang mở nhằm đánh giá năng lực tự thực hiện của học viên.

Nếu hệ thống không sử dụng trạng thái bài tập khi quyết định nội dung hỗ trợ, kết quả có thể hữu ích về mặt tính toán nhưng không phù hợp với mục tiêu học tập.

**Lỗi hệ thống liên quan:** Nếu sản phẩm đã có quy định giới hạn gợi ý nhưng `goi_y_bai_tap` vẫn gửi lời giải hoàn chỉnh, đó là lỗi thực thi chính sách của hệ thống.

**Cách giao tiếp:**

- Không chỉ trích học viên vì yêu cầu giải hộ.
- Không đưa ra kết luận về năng lực học tập.
- Giải thích ngắn gọn vì sao nội dung hỗ trợ bị giới hạn.
- Luôn đưa ra một bước học tiếp có thể thực hiện ngay.

**Vì sao không coi là lỗi người dùng:** Yêu cầu của học viên thể hiện mong muốn hoàn thành bài, nhưng hệ thống phải tự thực thi ranh giới hỗ trợ học tập. Cách nói nên lịch sự, không đánh giá năng lực hay đạo đức của học viên; cách sửa phải phụ thuộc trạng thái bài, không chỉ thay câu từ.

#### 3.2.5. Nguyên tắc HAX/PAIR gắn với vị trí cụ thể

| Nguyên tắc | Vị trí cụ thể (W08–W14) | Cách áp dụng |
|---|---|---|
| **HAX G10 — Scope services when in doubt** | **W08** `Bài tập 3 — Đang mở`, **W10** `Chỉ hỗ trợ từng bước`, **W12** `Xem gợi ý bước đầu` | Giới hạn đầu ra theo trạng thái bài, không đưa đáp án. |
| **HAX G11 — Make clear why the system did what it did** | **W09**: hạn 13/11/2026 23:59; **W11**: tham khảo §3.1, §3.2, §3.4 | Cho người học biết căn cứ và vì sao AI không giải toàn bộ. |
| **HAX G9 — Support efficient correction** | **W13** `Đổi bài tập` / `Ôn lại khái niệm`; **W14** nhập cách làm | Học viên có thể sửa ngữ cảnh và học tiếp mà không phải bắt đầu lại. |

**PAIR — Errors + Graceful Failure:** Giải thích đây là giới hạn học tập theo ngữ cảnh, không phải lỗi kỹ thuật; từ chối phần bị cấm nhưng vẫn cung cấp đường học tiếp, tránh gây xấu hổ cho học viên.

#### 3.2.6. Lỗi không thể cứu bằng câu chữ và giải pháp thiết kế

Nếu `goi_y_bai_tap` gửi toàn bộ lời giải cho học viên, câu xin lỗi sau đó không thể làm người học quên kết quả.

**Biện pháp ở mức thiết kế:**

1. Xác định bài tập và trạng thái của bài.
2. Phân loại nội dung yêu cầu: giải thích kiến thức, gợi ý bước đầu, xác nhận đáp số hoặc lời giải hoàn chỉnh.
3. Kiểm tra đầu ra trước khi gửi.
4. Chặn nội dung đáp số và nhận xét hoàn chỉnh với bài đang mở.
5. Chỉ hiển thị những hành động trợ lý được phép thực hiện.

**Quyết định:** Giới hạn trước khi gửi, không dùng lời xin lỗi sau khi tiết lộ làm cơ chế an toàn.

**Các kiểm soát hệ thống bổ sung (từ phân loại lỗi):**

- Kiểm tra trạng thái bài tập trước khi sinh hoặc gửi gợi ý.
- Phân biệt bài đang mở và bài đã công bố đáp án.
- Có bước kiểm tra nội dung gợi ý trước khi gửi.
- Không cho phép chế độ tự động gửi toàn bộ lời giải của bài đang mở.
- Cho phép học viên sửa lựa chọn bài tập nếu hệ thống xác định sai.


## §4. Mức tự chủ  (chặng 4)

### 4.1. Quyết định phân quyền và căn cứ

**Track:** T2 — Giáo dục: AI Study Assistant.

**Mục tiêu:** Xác định AI được tự làm gì, hành động nào cần người duyệt và hành động nào bị cấm; chọn mức theo **cost-of-error** (thiệt hại khi sai), **reversibility** (khả năng đảo ngược), **cost-of-delay** (chi phí chờ) và nguyên tắc **least privilege / fail closed** (quyền tối thiểu / không thực hiện hành động rủi ro nếu chưa xác minh được điều kiện an toàn).

**Căn cứ từ §2:** R10 — công khai kiến thức sai từ §3.3 lên FAQ cả lớp; R07 — giải toàn bộ bài tập 3 đang mở; R08 — xác nhận đúng/sai đáp số bài đang mở. Theo trang khóa học, bài tập 3 có hạn **13/11/2026, 23:59**; giờ làm việc của TA là **08:00–22:00**. Giờ làm việc không phải cam kết thời gian trả lời.

| Tool | Mức tự chủ nhóm chọn | Phạm vi cho phép / điều kiện bắt buộc |
|---|---|---|
| `tra_cuu_tai_lieu` | **Tự làm** | Chỉ đọc tài liệu đã mở, trả đúng nguồn và mã mục, đánh dấu thông tin cần kiểm chứng |
| `goi_y_bai_tap` | **Tự làm trong phạm vi cho phép** | Kiểm tra trạng thái bài, nội dung gợi ý và ngữ cảnh trước khi gửi; **cấm** cung cấp hoặc xác nhận đáp số bài đang mở |
| `chuyen_TA` | **Cần người duyệt** | Học viên xem trước và xác nhận nội dung sẽ gửi; chỉ báo thành công sau khi tool xác nhận |
| `dang_FAQ` | **Cần người duyệt** | TA/giảng viên kiểm chứng và duyệt **đúng phiên bản** nội dung trước khi công khai |

> **Phân biệt mức và hành vi bị cấm:** `goi_y_bai_tap` được *tự làm* với gợi ý an toàn, nhưng yêu cầu giải hộ/xác nhận đáp số bài đang mở là **cấm**, không được hợp thức hóa chỉ bằng việc học viên bấm đồng ý.

### 4.2. Với mỗi tool: mức tự chủ, cost-of-error, phương án loại và xử lý duyệt

#### 4.2.1. Tool 1 — `tra_cuu_tai_lieu`

**1. Mức nhóm chọn:** **Tự làm**; không yêu cầu phê duyệt từng lần tra cứu. AI chỉ truy xuất tài liệu buổi đã mở và hiển thị mã mục thực có; không tự tạo slide, tài liệu hoặc trích dẫn. Việc trả về §3.3 **không** có nghĩa thông tin trong đó chắc chắn đúng.

**2. Cost-of-error:**

| Góc nhìn | Đánh giá |
|---|---|
| Sai thì ai chịu gì? | Học viên có thể học sai, mất thời gian kiểm chứng; TA/giảng viên phải giải thích, đính chính. Nếu kết quả tra cứu bị dùng để đăng FAQ, thiệt hại tăng mạnh như **R10**. |
| Có đảo lại được không? | Có thể tra cứu lại, sửa câu trả lời hoặc bổ sung nguồn; nhưng không bảo đảm thu hồi được kiến thức sai học viên đã tiếp nhận. Bản thân thao tác tra cứu chỉ đọc. |
| Chờ người duyệt mất gì? | Bắt TA duyệt từng truy vấn làm mất tính tức thời của trợ lý, đặc biệt ngoài giờ hỗ trợ. |

**3. Phương án đã cân nhắc:**

| Phương án | Quyết định và lý do |
|---|---|
| Tự làm | **Chọn:** chi phí chờ thấp, tra cứu không tự thay đổi dữ liệu; kiểm soát riêng ở các hành động sau tra cứu. |
| Cần người duyệt | **Loại:** tạo hàng chờ cho mọi câu hỏi, trong khi rủi ro lan truyền thực sự nằm ở bước trả lời/đăng tiếp theo. |
| Cấm | **Loại:** phá vỡ chức năng giải thích có dẫn nguồn của trợ lý. |

**4. Rào chắn và xử lý:** Chỉ đọc nguồn được phép; giữ mã mục; không bịa trích dẫn; khi nguồn mâu thuẫn gắn `Cần kiểm chứng`, không dùng trực tiếp để `dang_FAQ`. Không có người duyệt hoặc mốc quá hạn cho thao tác đọc. **Đối chiếu §3:** W02–W03, W11.

#### 4.2.2. Tool 2 — `goi_y_bai_tap`

**1. Mức nhóm chọn:** **Tự làm có giới hạn** với gợi ý kiến thức nền và bước đầu. **Cấm** gửi lời giải, đáp số cuối, xác nhận đúng/sai hoặc nhận xét hoàn chỉnh cho bài đang mở. Khi không rõ bài nào, hỏi lại; khi không xác minh được trạng thái bài, không gửi thông tin có thể tiết lộ đáp án.

**2. Cost-of-error:**

| Góc nhìn | Đánh giá |
|---|---|
| Sai thì ai chịu gì? | Học viên có thể sao chép, mất cơ hội tự học; giảng viên khó đánh giá năng lực; hoạt động đánh giá mất tin cậy (**R07**, **R08**). |
| Có đảo lại được không? | **Hầu như không:** đáp số đã đọc không thể thu hồi, xóa tin nhắn không giúp người học quên đáp án. |
| Chờ người duyệt mất gì? | **Cao:** gợi ý nhỏ cũng phải xếp hàng chờ TA, nhất là sau 22:00 hoặc sát hạn nộp. |

**3. Phương án đã cân nhắc:**

| Phương án | Quyết định và lý do |
|---|---|
| Tự gửi mọi nội dung | **Loại:** nguy cơ tiết lộ toàn bộ bài ở R07 hoặc xác nhận đáp số ở R08. |
| Tự gửi sau kiểm tra chính sách | **Chọn:** giữ hỗ trợ tức thời nhưng hạn chế nội dung theo trạng thái bài và lịch sử hội thoại. |
| TA duyệt mọi gợi ý | **Suýt chọn nhưng loại:** an toàn hơn về mặt giám sát, song chi phí chờ quá lớn đối với những bước hướng dẫn hợp lệ. |
| Cấm mọi gợi ý | **Loại:** trợ lý không còn giúp học viên tự giải quyết bài tập. |

**4. Rào chắn và xử lý:** Trước khi gửi phải xác định **bài nào → trạng thái bài → loại yêu cầu → nội dung dự kiến → mức tiết lộ qua nhiều lượt**. Bài còn mở chỉ cho phép bước đầu; bài hết hạn **và đã công bố đáp án** có thể được giải thích đầy đủ. Nếu kiểm tra không đạt, chặn `goi_y_bai_tap`, thay bằng kiến thức nền an toàn hoặc hỏi rõ. Không yêu cầu con người duyệt từng gợi ý hợp lệ; không có thời hạn phê duyệt cho luồng này. **Đối chiếu §3:** W08–W14.

#### 4.2.3. Tool 3 — `chuyen_TA`

**1. Mức nhóm chọn:** **Cần người duyệt** trước khi chuyển; người duyệt là **chính học viên** gửi yêu cầu. Hành động gửi là một quyết định có tác động ra ngoài hội thoại, nên AI không tự quyết định thay học viên.

**2. Cost-of-error:**

| Góc nhìn | Đánh giá |
|---|---|
| Sai thì ai chịu gì? | Học viên bị gửi thông tin ngoài ý muốn hoặc lầm tưởng đã chuyển thành công; TA nhận câu hỏi lặp, sai hoặc thiếu ngữ cảnh. **R12** đặc biệt nguy hiểm nếu AI hứa phản hồi trong 5 phút dù không có SLA. |
| Có đảo lại được không? | Có thể gửi lại hoặc đính chính; nhưng không bảo đảm người nhận chưa đọc dữ liệu đã chuyển. |
| Chờ người duyệt mất gì? | **Thấp** nếu học viên xác nhận trực tiếp trong giao diện; không cần TA duyệt việc *nhận* câu hỏi. |

**3. Phương án đã cân nhắc:**

| Phương án | Quyết định và lý do |
|---|---|
| AI tự chuyển ngay | **Loại:** có thể gửi sai ý hoặc lộ thông tin không cần thiết. |
| Học viên xem trước và xác nhận | **Chọn:** thêm một bước ngắn, nhưng người gửi kiểm soát nội dung. |
| Cấm chuyển TA | **Loại:** không có đường xử lý khi nguồn sai, thiếu căn cứ hoặc vượt khả năng AI. |

**4. Người duyệt thấy gì?** Trước khi nhấn `Xác nhận gửi`, học viên thấy: **(a)** câu hỏi, **(b)** trích đoạn/mã mục sẽ gửi, **(c)** lý do chuyển, **(d)** thông tin ngữ cảnh được chia sẻ, và có thể **chỉnh sửa/hủy**. Trạng thái W05–W07: `Chưa gửi` → `Đang gửi` → `Đã gửi` **chỉ khi tool thành công**, hoặc `Gửi thất bại`.

**5. Quá hạn hoặc không duyệt thì sao?** Không có SLA phê duyệt được nêu trong dữ liệu. Nếu học viên không xác nhận hoặc rời luồng: **không gửi**, không tự xem im lặng là đồng ý. Nếu hệ thống không xác định được kết quả gửi: giữ `Chưa xác nhận`, kiểm tra/tránh trùng trước khi thử lại; không báo `Đã gửi`. Ngoài giờ TA **08:00–22:00**, có thể tiếp nhận yêu cầu nếu tool hỗ trợ nhưng phải báo rõ giờ làm việc, **không cam kết** TA phản hồi ngay hay trong 5 phút. **Đối chiếu §3:** W05–W07.

#### 4.2.4. Tool 4 — `dang_FAQ`

**1. Mức nhóm chọn:** **Cần người duyệt**; người duyệt là **TA hoặc giảng viên có thẩm quyền chuyên môn**. AI được soạn bản nháp, **không được tự công khai**. Quyền duyệt của học viên yêu cầu đăng **không thay** phê duyệt chuyên môn.

**2. Cost-of-error:**

| Góc nhìn | Đánh giá |
|---|---|
| Sai thì ai chịu gì? | Nhiều học viên có thể học sai từ một FAQ; TA/giảng viên phải đính chính; đơn vị đào tạo bị ảnh hưởng uy tín (**R10**). |
| Có đảo lại được không? | Chỉ **một phần:** gỡ/sửa bài được, nhưng không thu hồi được các bản ghi chép hoặc hiểu sai đã lan truyền. |
| Chờ người duyệt mất gì? | FAQ được công bố chậm; thấp hơn chi phí phát tán một khẳng định sai cho cả lớp. Người học vẫn có thể nhận giải thích cá nhân an toàn. |

**3. Phương án đã cân nhắc:**

| Phương án | Quyết định và lý do |
|---|---|
| AI tự đăng | **Loại:** một lỗi nguồn như §3.3 có thể lan truyền cho nhiều người. |
| TA/giảng viên duyệt rồi mới đăng | **Chọn:** người có chuyên môn chặn nội dung chưa xác minh trước khi công khai. |
| Cấm hoàn toàn FAQ | **Loại:** mất lợi ích tái sử dụng câu trả lời đã kiểm chứng. |

**4. Người duyệt thấy gì?** Bản nháp FAQ gồm **câu hỏi, nội dung trả lời, nguồn/mã §3.3, trích đoạn nghi vấn, trạng thái kiểm chứng, đối tượng sẽ thấy FAQ và phiên bản nội dung**. TA/giảng viên có thể **phê duyệt đúng phiên bản / yêu cầu sửa / từ chối**. Khi bản nháp thay đổi sau duyệt, phê duyệt cũ **mất hiệu lực**. Chỉ bản được duyệt hợp lệ mới được gọi `dang_FAQ`.

**5. Quá hạn thì sao?** Dữ liệu T2 **không quy định SLA duyệt FAQ**, vì vậy không được tự bịa mốc trả lời hoặc tự đăng sau một khoảng chờ. Nếu chưa nhận quyết định: giữ `Chờ duyệt`, không công khai, cho người học xem trạng thái và tiếp tục nhận hỗ trợ cá nhân an toàn. Nếu phiên duyệt hết hiệu lực hoặc nội dung bị sửa: yêu cầu duyệt lại. Nếu bị từ chối: hiện `Không được duyệt` và lý do khi có. Có thể **đề xuất** cơ chế nhắc duyệt sau một chu kỳ làm việc của TA; đó là cải tiến vận hành **chưa có trong bốn tool gốc**, không phải lời hứa thời gian xử lý. **Đối chiếu §3:** W01–W04.

### 4.3. Tool khó xếp nhất

**Tool:** `goi_y_bai_tap`. Đây là lựa chọn khó vì phải đánh đổi giữa **được hướng dẫn ngay** và **không tiết lộ đáp án bài đang mở**. R07 cho thấy rủi ro giải hộ toàn bộ, còn R08 cho thấy xác nhận một chữ `đúng/sai` cũng có thể làm lộ thông tin đánh giá.


| Thành viên | Mức/ phương án chọn ban đầu | Lý do và cái giá chấp nhận (liên kết R07/R08) | Có đổi ý sau thảo luận? |
|---|---|---|---|
| `[Tên thành viên — thêm dòng cho mỗi người]` | `[Tự làm / Cần người duyệt / Cấm]` | `[Ghi quan điểm thực tế, ví dụ chi phí lộ đáp án R07/R08 hoặc chi phí chờ]` | `[Có/Không — vì sao]` |

**Cái giá của từng phía:**

| Phía lựa chọn | Được gì? | Cái giá phải trả (theo §2) | Nhóm xử lý |
|---|---|---|---|
| A. Tự động gửi mọi gợi ý | Nhanh, ít thao tác | Có thể giải hộ **R07**, xác nhận đáp số **R08**; không thu hồi được | **Loại** |
| B. TA duyệt mọi gợi ý | Thêm lớp giám sát | Chờ qua đêm 22:00–08:00, cả gợi ý phương pháp cũng ùn tắc | **Suýt chọn; loại** |
| C. Cấm mọi gợi ý | Giảm nguy cơ lộ đáp số qua tool | Học viên không có trợ giúp khi cần tự học | **Loại** |
| D. Tự làm có kiểm tra chính sách | Hỗ trợ ngay và giữ giới hạn | Bộ lọc có thể sai; vẫn có nguy cơ lộ thông tin qua nhiều lượt | **Chọn trong bản thiết kế** |

**Nhóm chốt như thế nào?** Theo phương án được ghi trong bản nguồn, nhóm chọn **D — Tự làm có giới hạn**: kiểm tra bài, trạng thái, chính sách nội dung và lịch sử hội thoại **trước khi gửi**. Không cho phép AI vượt rào bằng lời xin lỗi sau đó. **Điều kiện tiên quyết:** nếu bộ kiểm tra chưa triển khai hoặc chưa đủ tin cậy, mặc định không gửi gợi ý có nguy cơ lộ đáp án; chỉ giải thích kiến thức nền an toàn. Bản nguồn **chưa có biên bản biểu quyết/ý kiến từng người**, nên không được trình bày bảng chỗ trống như kết quả thảo luận đã xác thực.

### 4.4. Thử các mức đã chọn trên ba kịch bản

#### 4.4.1. Test A — R10: Đăng nội dung sai lên FAQ (kịch bản đắt nhất #1)

**Input:** “Cô đăng giải thích ở §3.3 lên FAQ chung giúp em, để cả lớp khỏi phải hỏi lại nhé.”

**Luồng:** `tra_cuu_tai_lieu` tự chạy → nhận ra khẳng định “độ lệch chuẩn luôn nhỏ hơn phương sai” có vấn đề (ví dụ phương sai 0,25 thì độ lệch chuẩn 0,5) → W01–W04 báo `Cần kiểm chứng` / `Chưa đăng` → **không gọi** `dang_FAQ` → nếu học viên muốn chuyển kiểm chứng, hiện bản xem trước W05–W07, chờ học viên xác nhận → chỉ công khai FAQ đã được TA/giảng viên xác minh và duyệt đúng phiên bản.

| Câu kiểm tra | Kết quả thiết kế |
|---|---|
| Cái sai có bị chặn không? | **Có điều kiện:** câu trả lời chưa xác minh không thể tự đi qua bước duyệt để đăng FAQ. |
| AI còn tự làm khi lẽ ra phải hỏi/duyệt? | **Không nếu triển khai đúng:** hỏi học viên trước `chuyen_TA`, yêu cầu TA/giảng viên duyệt trước `dang_FAQ`. |
| Người dùng bình thường phải chờ vô ích? | **Không:** chỉ FAQ công khai chờ; giải thích cá nhân và tra cứu an toàn vẫn thực hiện ngay. |

**Rủi ro còn lại:** người duyệt bỏ sót lỗi, hoặc nội dung đổi sau khi duyệt. **Kết luận:** PASS **có điều kiện**, cần kiểm thử quy tắc chặn và khóa phiên bản.

#### 4.4.2. Test B — R07: Giải hộ bài 3 đang mở (kịch bản đắt nhất #2)

**Input:** “Mai em bận rồi, cô giải hộ hết bài 3 đi, cả câu a với b, em chép vào bảng tính luôn.”

**Luồng:** xác định bài 3 và tra trạng thái từ trang khóa học → W08–W10 hiển thị `Đang mở`, hạn 13/11/2026 23:59 → từ chối giải trọn bài, đáp số và xác nhận đúng/sai → cho chọn `Xem gợi ý bước đầu` → tạo gợi ý, kiểm tra chính sách **và lịch sử hội thoại**, mới gọi `goi_y_bai_tap` → W13–W14 cho học viên tự làm và hỏi về phương pháp.

| Câu kiểm tra | Kết quả thiết kế |
|---|---|
| Cái sai có bị chặn không? | **Có điều kiện:** chặn đầu ra chứa lời giải/đáp số/đánh giá đáp số khi bài còn mở. |
| AI còn tự làm khi lẽ ra phải hỏi? | **Không nếu triển khai đúng:** bài đã rõ thì áp quy tắc; nếu chưa rõ bài hoặc trạng thái thì **hỏi lại/không gửi**. |
| Người dùng bình thường phải chờ vô ích? | **Không:** gợi ý kiến thức nền được gửi ngay, không đợi TA duyệt từng lần. |

**Rủi ro còn lại:** tiết lộ đáp án gián tiếp qua chuỗi gợi ý; bộ lọc cần kiểm thử đa lượt, không chỉ từng câu. **Kết luận:** PASS **có điều kiện**.

#### 4.4.3. Test C — Bình thường: Chỉ xin gợi ý bước đầu

**Input:** “Em đang làm bài 3, cô chỉ gợi ý bước đầu để tìm trung vị thôi, không cần đáp số ạ.”

**Luồng:** tra §3.2 và trạng thái bài → xác định yêu cầu hợp lệ → gợi ý kiểm tra thứ tự giá trị và quy tắc trung vị, **không tính hộ** → nội dung vượt kiểm tra → gọi `goi_y_bai_tap` → học viên có thể tiếp tục hỏi về phương pháp.

| Câu kiểm tra | Kết quả thiết kế |
|---|---|
| Cái sai có bị chặn không? | **Có điều kiện:** gợi ý không kèm đáp số. |
| AI còn làm khi lẽ ra phải hỏi? | **Không:** học viên đã chỉ rõ bài và phạm vi giúp đỡ, không cần hỏi thêm. |
| Người dùng bình thường phải chờ vô ích? | **Không:** nhận gợi ý hợp lệ mà không qua hàng chờ TA. |

**Rủi ro còn lại:** bộ lọc quá nghiêm làm từ chối nhầm cả gợi ý hợp lệ. **Kết luận:** PASS **có điều kiện**, cần đo tỷ lệ chặn nhầm khi kiểm thử prototype.

### 4.5. Luật bổ sung hoặc tách bước tool — và vì sao

| Luật / luồng được đề xuất | Cách thực thi ở lớp hành động | Chặn lỗi nào? Vì sao cần? |
|---|---|---|
| **Gợi ý:** `soan_goi_y` → `kiem_tra_chinh_sach` → `goi_y_bai_tap` | Hai bước đầu là logic bổ sung. Xác định bài, trạng thái, nội dung và mức lộ qua lịch sử. Chỉ gửi bản vượt kiểm tra; không chắc thì **không gửi**. | **R07/R08:** prompt hoặc câu từ chối không đủ nếu tool vẫn gửi đáp số. |
| **Chuyển TA:** `soan_yeu_cau_TA` → học viên xác nhận → `chuyen_TA` | Cho xem trước/chỉnh sửa thông tin được chia sẻ. Kết quả gửi phải được xác nhận; tránh gửi trùng khi timeout chưa rõ. | **R12:** không tự chuyển, không báo “đã gửi” hoặc hứa “5 phút” khi chưa có căn cứ. |
| **FAQ:** `soan_FAQ` → `kiem_chung_noi_dung` → TA/giảng viên duyệt phiên bản → `dang_FAQ` | Soạn tách khỏi công khai, kiểm chứng nguồn, chờ phê duyệt chuyên môn; khóa phiên bản; thiếu duyệt thì **không đăng**. | **R10:** ngăn biến khẳng định sai trong §3.3 thành kiến thức chung. |

**Luật chung:** (1) hành động chỉ đọc có thể tự làm, (2) hành động gửi/công khai phải kiểm soát theo tác động, (3) không hạ rào chắn khi chờ lâu, (4) không tuyên bố thành công khi tool chưa xác nhận, (5) chỉ hiển thị các hành động được phép trong giao diện. Các bước `soan_*` và `kiem_*`, cũng như hàng chờ duyệt FAQ, là **đề xuất mở rộng**, chưa nằm trong bộ bốn tool gốc. Duyệt của con người giảm rủi ro nhưng **không bảo đảm** không có lỗi.

### 4.6. Mức tự chủ thay đổi lời hứa nào với người dùng?

**Lời hứa cũ (không còn phù hợp):**

> “AI có thể giải bài và đưa câu trả lời ngay khi bạn yêu cầu.”

**Lời hứa mới sau khi giới hạn `goi_y_bai_tap`:**

> “AI giúp bạn hiểu bài và tự giải quyết bài tập bằng các gợi ý từng bước. Với bài đang mở, AI không cung cấp hoặc xác nhận đáp số.”

**Thay đổi thực chất:** từ *làm thay* → *hỗ trợ tự làm*; từ *trả lời tất cả* → *chỉ trả lời trong phạm vi học tập*; từ *gửi ngay mọi nội dung* → *kiểm tra trước khi gửi*. Nhờ vậy, học viên vẫn được hỗ trợ đúng cách mà không phải chờ TA cho các gợi ý hợp lệ.

**Lời hứa bổ sung theo mức `dang_FAQ`:**

> “AI có thể chuẩn bị nội dung chia sẻ cho lớp, nhưng không tự công khai khi chưa được TA hoặc giảng viên phê duyệt.”

Lời hứa mới phải phản ánh **quyền thật ở lớp hành động**, không chỉ là câu nói của chatbot.


## §5. Prototype  (chặng 5)

### 5.1. File, công cụ và phạm vi prototype

- **Sản phẩm:** StudyGuard — AI Study Assistant cho khóa *Nhập môn phân tích dữ liệu*.
- **File demo được mô tả trong tài liệu:** [prototype/index.html](prototype/index.html) (chưa có URL triển khai công khai trong tài liệu).
- **Công cụ:** HTML, CSS và JavaScript thuần; chạy trực tiếp trên trình duyệt, không cần API key.
- **Hai kịch bản minh họa:** R10 — chặn đăng FAQ chứa kiến thức sai; R07 — chỉ gợi ý từng bước cho bài tập 3 đang mở.
- **Phần mô phỏng (mock):** Tài liệu và trạng thái bài tập, phản hồi AI, quy tắc kiểm tra nội dung, kết quả gọi bốn tool (`tra_cuu_tai_lieu`, `goi_y_bai_tap`, `chuyen_TA`, `dang_FAQ`) và vai TA phê duyệt FAQ.
- **Lời gọi AI thật:** **Không.** Prototype không kết nối LLM, backend, cơ sở dữ liệu hay hệ thống TA/FAQ thật; mọi phản hồi và thao tác được mô phỏng trong trình duyệt.

### 5.2. Hai ảnh minh chứng có đánh số

**Ảnh 1 — R10: Cần kiểm chứng trước khi đăng FAQ**  
Ảnh trong dự án: [prototype/case_R10.png](prototype/case_R10.png).

![Ảnh 1 — R10: Cần kiểm chứng trước khi đăng FAQ](prototype/case_R10.png)

| Số trên ảnh | Vị trí / thể hiện điều gì | Nguyên tắc HAX/PAIR | Mức tự chủ được thể hiện |
|---|---|---|---|
| **①** | W01–W03: nhãn `Cần kiểm chứng`, nguồn §3.3 và phản ví dụ phương sai 0,25 → độ lệch chuẩn 0,5. | **HAX G11:** giải thích căn cứ và lý do hệ thống nghi ngờ. | `tra_cuu_tai_lieu`: **Tự làm**; kết quả tra cứu không đồng nghĩa nội dung đã đúng. |
| **②** | W04: `FAQ: Chưa đăng`; không có nút cho học viên công khai ngay. | **HAX G10:** thu hẹp hành động khi chưa chắc chắn. | `dang_FAQ`: **Cần TA/giảng viên duyệt** bản đã xác minh. |
| **③** | W05–W07: xem trước và sửa yêu cầu, xác nhận chuyển TA; hiển thị `Đã gửi` hoặc `Gửi thất bại` theo kết quả mock. | **HAX G9** và **PAIR Graceful Failure:** cho phép sửa/thử lại, không báo thành công giả. | `chuyen_TA`: **Cần học viên xác nhận** trước khi gửi. |

**Ảnh 2 — R07: Gợi ý bài tập đang mở có giới hạn**  
Ảnh trong dự án: [prototype/case_R7.png](prototype/case_R7.png).

![Ảnh 2 — R07: Gợi ý bài tập đang mở có giới hạn](prototype/case_R7.png)

| Số trên ảnh | Vị trí / thể hiện điều gì | Nguyên tắc HAX/PAIR | Mức tự chủ được thể hiện |
|---|---|---|---|
| **④** | W08–W11: `Bài tập 3 — Đang mở`, hạn nộp, tài liệu tham chiếu và thông báo không cung cấp/xác nhận đáp số. | **HAX G11:** nêu rõ trạng thái bài và lý do giới hạn hỗ trợ. | `tra_cuu_tai_lieu`: **Tự làm**; việc tiết lộ đáp số bài đang mở: **Cấm**. |
| **⑤** | W12: `Xem gợi ý bước đầu`, chỉ hướng dẫn sắp xếp dữ liệu và quy tắc trung vị. | **HAX G10:** giới hạn phạm vi hỗ trợ để tránh làm bài hộ. | `goi_y_bai_tap`: **Tự làm có giới hạn**, chỉ gửi gợi ý hợp lệ. |
| **⑥** | W13–W14: ôn khái niệm, đổi bài hoặc nhập cách làm để nhận góp ý về phương pháp. | **HAX G9** và **PAIR Graceful Failure:** vẫn có đường học tiếp, sửa ngữ cảnh. | `goi_y_bai_tap`: **Tự làm có giới hạn**; không xác nhận đúng/sai cho bài đang mở. |

Cả hai ảnh được mô tả ở **mức ② — Theo chính sách nhóm** (§4), có bật chú thích HAX/PAIR.

### 5.3. Quyết định thiết kế và phương án bị loại

**Quyết định 1 — Hiển thị độ chắc chắn thông qua bằng chứng và trạng thái, không dùng phần trăm tự đặt.**

- **Chọn:** Nhãn `Cần kiểm chứng` (R10) hoặc `Giới hạn hỗ trợ` / `Đang mở` (R07), kèm mã mục tài liệu, ví dụ kiểm tra và lý do giới hạn. Thể hiện tại **①, ④** (HAX G11).
- **Đã cân nhắc nhưng loại:** Hiển thị “AI chắc chắn 95%” vì prototype không có dữ liệu hiệu chuẩn; chỉ đưa câu trả lời hoặc lời xin lỗi vì người dùng không thể kiểm tra căn cứ.

**Quyết định 2 — Điều khiển mức tự chủ bằng chính sách và phê duyệt trước hành động.**

- **Chọn:** Ba chế độ để so sánh: **① Chỉ gợi ý** (AI chuẩn bị nội dung, học viên tự thao tác); **② Theo chính sách nhóm** *(mặc định)*; **③ Tự động có rào chắn** (chủ động chuẩn bị thêm nhưng không mở rộng quyền đăng/gửi). Bảng phân quyền và lời hứa trên giao diện cập nhật theo chế độ.
- **Chính sách mức ②:** `tra_cuu_tai_lieu` tự làm; `goi_y_bai_tap` tự gửi nội dung hợp lệ; `chuyen_TA` cần học viên xác nhận; `dang_FAQ` cần TA/giảng viên duyệt. Không chế độ nào được giải hộ bài đang mở hoặc đăng FAQ chưa xác minh. Thể hiện tại **②, ③, ⑤** (HAX G9/G10).
- **Đã cân nhắc nhưng loại:** AI tự gửi/đăng rồi sửa sau vì tác động khó thu hồi (R10, R07); bắt TA duyệt mọi gợi ý vì học viên phải chờ vô ích; cấm toàn bộ hành động vì làm mất khả năng hỗ trợ học tập.

**Giới hạn đánh giá:** Prototype minh họa cách giao diện thực thi phân quyền ở các kịch bản cố định, **chưa chứng minh khả năng kiểm soát đầu ra của LLM hoặc phê duyệt thật trong hệ thống triển khai**.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)

### 6.1. Ba tiêu chí Pass/Fail có thể chấm khách quan

| Mã | Tiêu chí và cách đo | PASS khi | FAIL khi |
|---|---|---|---|
| **E1 — An toàn & đúng quyền** | Thực hiện hành động rủi ro ở R10/R07 và quan sát nội dung được hiển thị cùng trạng thái hành động. | **R10:** FAQ luôn ở trạng thái chưa đăng cho đến khi có yêu cầu TA gửi thành công, TA xác minh bản sửa và bấm duyệt; **R07:** bài 3 đang mở chỉ hiện gợi ý phương pháp, không đưa hoặc xác nhận đáp số, kể cả khi người dùng hỏi “11,5 có đúng không?”. | FAQ được báo đã đăng trước khi TA duyệt, hoặc AI giải hộ/xác nhận kết quả bài 3. |
| **E2 — Minh bạch & có căn cứ** | Quan sát các nhãn trạng thái và nguồn trước khi bấm hành động. | **R10:** thấy `Cần kiểm chứng`, nguồn **§3.3**, phản ví dụ phương sai **0,25** → độ lệch chuẩn **0,5**, trạng thái FAQ; **R07:** thấy bài 3 **đang mở**, hạn **13/11/2026 23:59**, nguồn **§3.1/§3.2/§3.4** và lý do không giải hộ. | Thiếu bất kỳ thông tin bắt buộc nào của ca tương ứng; hoặc UI khẳng định hành động đã thành công khi trạng thái tool là thất bại. |
| **E3 — Có đường tiếp tục/khắc phục** | Mô phỏng ít nhất một lỗi công cụ rồi thử khôi phục mà không tải lại trang; kiểm tra thao tác sửa ngữ cảnh. | **R10:** học viên xem trước/xác nhận trước khi gửi TA; mô phỏng gửi thất bại thì hiện lỗi, thử lại thành công thì hiện `Đã gửi TA` nhưng FAQ vẫn chưa đăng. **R07:** gửi gợi ý thất bại có `Thử lại`; người học có thể nhận gợi ý hợp lệ, đổi sang bài 2 đã công bố để xem đáp án rồi trở lại bài 3 với giới hạn ban đầu. | Bị kẹt không có đường khôi phục; lỗi vẫn hiển thị thành công; hoặc đổi bài làm mất giới hạn bài đang mở. |

**Vì sao chọn ba tiêu chí này?** E1 đo hậu quả đắt nhất (đăng thông tin sai và tiết lộ đáp án), E2 đo khả năng học viên nhìn thấy căn cứ và giới hạn, E3 đo việc hệ thống có giúp người dùng sửa hoặc tiếp tục hay không. Không chọn các chỉ số như “AI hữu ích 90%” hay “độ chính xác 95%” vì fixture không có nhãn đánh giá hoặc dữ liệu hiệu chuẩn để chấm khách quan.

### 6.2. Chấm thử trên hai kịch bản đắt nhất

| Ca | E1 — An toàn & quyền | E2 — Căn cứ & trạng thái | E3 — Khôi phục & tiếp tục | Tổng |
|---|---|---|---|---|
| **R10: §3.3 sai → yêu cầu FAQ** | **PASS:** vai TA không có nút duyệt trước khi gửi thành công; FAQ chỉ được đăng *bản đã sửa* sau bước xác minh và phê duyệt. | **PASS (demo):** W01–W04 hiển thị `Cần kiểm chứng`, §3.3, phản ví dụ 0,25/0,5 và `FAQ: Chưa đăng`. | **PASS (demo):** W05–W07 có xem trước; gửi lỗi → báo thất bại → thử lại → báo đã chuyển TA, chưa đăng FAQ. | **3/3** |
| **R07: Xin giải hộ bài 3** | **PASS:** W10–W12 không hiển thị lời giải cuối; nhập “Em tính được trung vị 11,5, đúng không ạ?” chỉ nhận góp ý phương pháp. | **PASS (demo):** W08–W11 hiển thị bài đang mở, hạn nộp và các mã nguồn §3.1, §3.2, §3.4. | **PASS (demo):** gợi ý lỗi → thử lại; chuyển sang bài 2 xem đáp án đã công bố là 6; quay lại bài 3 vẫn chặn đáp số. | **3/3** |

**Tổng kết:** **6/6 ô tiêu chí đạt PASS trong prototype** (3 tiêu chí × 2 ca). Bộ kiểm thử trình duyệt ghi nhận **7 kiểm tra thành phần PASS**.

**Đường đi đã kiểm tra:**

- **R10/E1:** Khi chưa có yêu cầu TA được gửi thành công, chuyển sang vai TA cũng không thấy nút `TA duyệt và đăng`. Sau khi học viên xác nhận, tool báo thành công, TA chọn `Xác minh và tạo bản đã sửa`, lúc đó mới xuất hiện nút duyệt; nhấn duyệt mới đổi trạng thái FAQ sang đã đăng *(mô phỏng)*.
- **R10/E3:** Chọn tool `Thất bại` khi gửi TA; UI chỉ báo `Gửi TA thất bại`, không báo thành công. Chọn `Thành công`, thử lại; UI báo `Đã gửi TA (mô phỏng)` nhưng giữ FAQ chưa đăng.
- **R07/E1:** Ở bài 3, nút `Xem gợi ý bước đầu` chỉ hiển thị cách tiếp cận trung vị; nhập câu xin xác nhận kết quả cũng không nhận câu trả lời đúng/sai.
- **R07/E3:** Khi mô phỏng gợi ý thất bại, UI có đường thử lại. Việc chọn bài 2 (đã công bố đáp án) cho phép giải thích đáp án **6**, trong khi đổi về bài 3 khôi phục giới hạn.

### 6.3. Các lỗi và giới hạn còn lại

| ID | Lỗi/giới hạn chưa giải quyết | Hậu quả nếu đưa ra dùng thật | Ưu tiên & hướng xử lý |
|---|---|---|---|
| **L1** | **Kiểm soát gợi ý là các nhánh nội dung cố định, chưa phải bộ kiểm tra LLM theo ngữ cảnh.** | Chưa chứng minh AI không lộ đáp số bằng cách hỏi vòng vo hoặc qua nhiều lượt. | **Cao:** kiểm tra đầu ra trước khi gọi tool, giữ ngữ cảnh hội thoại, bổ sung test R08 và bài tập lạ. |
| **L2** | **Chưa có luồng gỡ/đính chính FAQ đã đăng và thông báo đến người đã đọc.** | Nếu TA duyệt nhầm, tác động của thông tin sai khó thu hồi. | **Trung bình/Cao:** cơ chế đính chính và thông báo cho người học; audit lịch sử phiên bản. |


## §7. Demo

### 7.1. Ca lạ được thử trong demo

**R13 — Học viên báo FAQ đã đăng lời giải của bài tập đang mở.**

> “Cô ơi, em vừa thấy trên FAQ có bài đăng giải sẵn cả câu (a) và (b) của bài tập 3. Cô xóa ngay bài đó, báo cho cả lớp đừng dùng đáp án, rồi nhắn TA là đã xử lý xong giúp em!”

### 7.2. Prototype đã xử lý như thế nào?

| Bước | Hành vi quan sát được trên prototype | Giới hạn / mức tự chủ |
|---|---|---|
| 1. Nhận báo cáo | Hiển thị **“Chưa thể xác minh”**; nêu rõ không có công cụ kiểm tra/xóa FAQ hoặc thông báo cả lớp. | Không tự nhận đã xử lý sự cố; **G11 — giải thích giới hạn**. |
| 2. Đề xuất xử lý | Cho xem trước và chỉnh sửa báo cáo; học viên chọn **Xác nhận chuyển TA** hoặc **Hủy**. | `chuyen_TA` **cần học viên duyệt**; **G9 — hỗ trợ sửa**. |
| 3. Mô phỏng gửi | Nếu thành công, hiển thị **“Đã chuyển TA (mô phỏng)”**; nếu thất bại, báo lỗi và cho thử lại. | Không đồng nhất **đã chuyển** với **đã xóa FAQ**. |
| 4. Chặn vượt quyền | Không tự đăng đính chính, xóa FAQ hoặc phát thông báo; không tiết lộ lại đáp án bài 3. | `dang_FAQ` **cần TA/giảng viên duyệt**; **G10 — thu hẹp phạm vi khi rủi ro**. |


### 7.3. Nhóm có thay đổi quyết định sau ca lạ không?

**Sau lần thử mô phỏng: Không thay đổi mức tự chủ đã chốt ở §4.** AI vẫn không được tự đăng, xóa hoặc tuyên bố đã xử lý nội dung FAQ; chuyển TA vẫn cần học viên xác nhận.

**Điều chỉnh đề xuất cho phiên bản tiếp theo:** Bổ sung quy trình xử lý sự cố do người có thẩm quyền phụ trách: **xác minh FAQ → TA quyết định ẩn/gỡ → duyệt và phát đính chính → ghi nhận trạng thái xử lý**. Prototype hiện tại chưa có các công cụ này. Lý do: lời xin lỗi hoặc việc chuyển TA không thể thu hồi đáp án mà học viên khác có thể đã đọc.
