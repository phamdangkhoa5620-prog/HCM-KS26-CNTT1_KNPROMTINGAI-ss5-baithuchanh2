
# XÂY DỰNG CHUỖI PROMPT VIẾT BÀI PR SẢN PHẨM CÔNG NGHỆ BẰNG PROMPT CHAINING

## 1. Mục tiêu

- Thành thạo kỹ thuật Prompt Chaining để giải quyết các tác vụ phức tạp qua nhiều công đoạn.
- Biết cách thiết lập và truyền ngữ cảnh (Context) giữa các prompt thành phần.
- Xây dựng quy trình viết bài PR chuyên nghiệp, có chiều sâu và hạn chế lặp ý.
- Nắm vững kỹ thuật xử lý khi AI bị ngắt giữa chừng do giới hạn Token.
- Đảm bảo tính nhất quán về nội dung, cấu trúc và giọng điệu trong toàn bộ bài viết.

## 2. Bối cảnh bài toán

Phòng Marketing cần xây dựng một bài PR chuyên sâu khoảng 1.000–1.500 từ để giới thiệu giải pháp AI Chatbot mới dành cho doanh nghiệp.

Nếu sử dụng một prompt duy nhất để yêu cầu AI viết toàn bộ bài, kết quả có thể gặp các vấn đề:

- Nội dung hời hợt, thiếu chiều sâu.
- Các đoạn văn bị lặp ý.
- Không xác định đúng nhu cầu khách hàng mục tiêu.
- Dàn ý thiếu logic và không có sự liên kết.
- Từ khóa SEO được sử dụng chưa hợp lý.
- Bài viết có thể bị ngắt quãng khi vượt quá giới hạn Token.

**Giải pháp:** Sử dụng kỹ thuật Prompt Chaining gồm 3 bước, trong đó đầu ra của bước trước là đầu vào bắt buộc của bước tiếp theo.

## 3. Thiết kế quy trình Prompt Chaining

### Bước 1: Nghiên cứu khách hàng mục tiêu và Pain Points

**Mục tiêu:** Xác định đối tượng khách hàng tiềm năng, nhu cầu và những vấn đề mà AI Chatbot có thể giải quyết.

**Prompt 1:**

# ROLE
Bạn là chuyên gia nghiên cứu thị trường và phân tích khách hàng trong lĩnh vực công nghệ.

# TASK
Hãy nghiên cứu đối tượng khách hàng mục tiêu cho sản phẩm AI Chatbot dành cho doanh nghiệp.

# PRODUCT INFORMATION
- Sản phẩm: AI Chatbot doanh nghiệp.
- Chức năng: Tự động trả lời khách hàng, tư vấn sản phẩm, hỗ trợ chăm sóc khách hàng 24/7, phân tích dữ liệu và tích hợp với hệ thống quản lý doanh nghiệp.
- Đối tượng: Doanh nghiệp vừa và nhỏ, doanh nghiệp thương mại điện tử và bộ phận chăm sóc khách hàng.

# PROCESS
1. Xác định nhóm khách hàng mục tiêu.
2. Phân tích đặc điểm và hành vi của từng nhóm.
3. Xác định ít nhất 5 Pain Points (nỗi đau khách hàng).
4. Phân tích nguyên nhân và hậu quả của từng vấn đề.
5. Đề xuất tính năng AI Chatbot có thể giải quyết từng Pain Point.
6. Xác định lợi ích nổi bật mà khách hàng nhận được.

# OUTPUT FORMAT

CUSTOMER_PROFILE:
- Nhóm khách hàng:
- Đặc điểm:
- Nhu cầu:

PAIN_POINTS:
1. Vấn đề:
   - Nguyên nhân:
   - Hậu quả:
   - Giải pháp từ AI Chatbot:

2. Vấn đề:
   - Nguyên nhân:
   - Hậu quả:
   - Giải pháp từ AI Chatbot:

VALUE_PROPOSITION:
- Giá trị nổi bật:
- Lợi ích kinh doanh:
- Điểm khác biệt:

# CONSTRAINTS
- Phân tích thực tế, rõ ràng và có logic.
- Không tự tạo số liệu thống kê hoặc dẫn chứng chưa được xác minh.
- Tập trung vào nhu cầu doanh nghiệp.
- Sử dụng giọng văn chuyên nghiệp, tin cậy.
- Kết quả phải có cấu trúc rõ ràng để sử dụng làm đầu vào cho Prompt 2.

**Đầu ra Prompt 1:**

- Khách hàng mục tiêu: Doanh nghiệp vừa và nhỏ, doanh nghiệp thương mại điện tử.
- Nhu cầu: Tăng tốc độ phản hồi, giảm chi phí vận hành và nâng cao trải nghiệm khách hàng.
- Các Pain Points:
  1. Nhân viên chăm sóc khách hàng quá tải.
  2. Khách hàng phải chờ lâu để được phản hồi.
  3. Chi phí thuê nhân viên chăm sóc khách hàng cao.
  4. Khó quản lý và phân tích dữ liệu khách hàng.
  5. Bỏ lỡ khách hàng tiềm năng ngoài giờ làm việc.
- Giải pháp: Tự động hóa tư vấn, hỗ trợ 24/7, quản lý dữ liệu và phân tích tương tác khách hàng.
- Giá trị nổi bật: Tiết kiệm chi phí, tăng hiệu suất và cải thiện trải nghiệm khách hàng.

### Bước 2: Xây dựng dàn ý bài viết PR (Outline)

**Mục tiêu:** Sử dụng kết quả nghiên cứu từ Prompt 1 để xây dựng dàn ý bài PR có cấu trúc logic, hấp dẫn và chuẩn SEO.

**Prompt 2:**

# ROLE
Bạn là chuyên gia Content Marketing và SEO trong lĩnh vực công nghệ.

# TASK
Dựa trên toàn bộ kết quả nghiên cứu khách hàng từ Prompt 1, hãy xây dựng dàn ý chi tiết cho bài PR giới thiệu sản phẩm AI Chatbot dành cho doanh nghiệp.

# INPUT
[ DÁN TOÀN BỘ OUTPUT CỦA PROMPT 1 VÀO ĐÂY ]

# PROCESS
1. Phân tích lại Customer Profile và Pain Points.
2. Xác định thông điệp truyền thông chính.
3. Xây dựng tiêu đề bài viết hấp dẫn.
4. Viết đoạn mở đầu (Lead) tập trung vào vấn đề khách hàng.
5. Xây dựng hệ thống tiêu đề H2 và H3.
6. Sắp xếp nội dung theo trình tự:
   - Thực trạng và khó khăn của doanh nghiệp.
   - Giới thiệu giải pháp AI Chatbot.
   - Các tính năng nổi bật.
   - Lợi ích đối với doanh nghiệp.
   - Khả năng ứng dụng thực tế.
   - Lời kêu gọi hành động (CTA).
7. Đề xuất từ khóa SEO chính và từ khóa phụ.

# OUTPUT FORMAT

CONTENT_STRATEGY:
- Đối tượng độc giả:
- Thông điệp chính:
- Giọng văn: Chuyên nghiệp, tin cậy.
- Mục tiêu bài viết:

SEO_KEYWORDS:
- Từ khóa chính:
- Từ khóa phụ:
- Từ khóa liên quan:

ARTICLE_OUTLINE:
- Headline:
- Lead:
- H2:
  - H3:
  - H3:
- H2:
  - H3:
  - H3:
- H2:
  - H3:
  - H3:
- CTA:

# CONSTRAINTS
- Dàn ý phải có tính liên kết và logic.
- Mỗi tiêu đề phải phục vụ một mục tiêu nội dung cụ thể.
- Không lặp lại các ý giữa các phần.
- Bám sát Pain Points từ Prompt 1.
- Đảm bảo phù hợp với bài viết dài 1.000–1.500 từ.
- Giữ giọng văn chuyên nghiệp, tin cậy.
- Kết quả phải được sử dụng trực tiếp làm đầu vào cho Prompt 3.

**Đầu ra Prompt 2:**

- Tiêu đề: AI Chatbot doanh nghiệp – Giải pháp tự động hóa chăm sóc khách hàng trong thời đại số.
- Lead: Giới thiệu những khó khăn trong việc chăm sóc khách hàng và nhu cầu tự động hóa.
- H2. Những thách thức trong hoạt động chăm sóc khách hàng hiện nay.
  - H3. Nhân viên quá tải và chi phí vận hành tăng cao.
  - H3. Khách hàng phải chờ đợi phản hồi.
- H2. AI Chatbot – Giải pháp tự động hóa chăm sóc khách hàng.
  - H3. Tự động trả lời và tư vấn khách hàng.
  - H3. Hỗ trợ khách hàng 24/7.
- H2. Những lợi ích nổi bật của AI Chatbot.
  - H3. Tiết kiệm chi phí và nhân lực.
  - H3. Nâng cao trải nghiệm khách hàng.
  - H3. Hỗ trợ phân tích dữ liệu kinh doanh.
- H2. Ứng dụng AI Chatbot trong doanh nghiệp.
  - H3. Thương mại điện tử.
  - H3. Dịch vụ và chăm sóc khách hàng.
- CTA: Đăng ký tư vấn và trải nghiệm giải pháp AI Chatbot.

### Bước 3: Triển khai bài viết PR và tối ưu SEO

**Mục tiêu:** Dựa trên dàn ý của Prompt 2 để triển khai thành bài PR hoàn chỉnh, đảm bảo độ dài, tính chuyên nghiệp và tối ưu SEO.

**Prompt 3:**

# ROLE
Bạn là chuyên gia Content Marketing và SEO với kinh nghiệm viết bài PR sản phẩm công nghệ.

# TASK
Dựa trên kết quả nghiên cứu từ Prompt 1 và dàn ý chi tiết từ Prompt 2, hãy viết một bài PR chuyên sâu giới thiệu sản phẩm AI Chatbot dành cho doanh nghiệp.

# INPUT
1. Kết quả nghiên cứu khách hàng:
[ DÁN OUTPUT PROMPT 1 ]

2. Dàn ý bài viết:
[ DÁN OUTPUT PROMPT 2 ]

# REQUIREMENTS
1. Độ dài bài viết từ 1.000–1.500 từ.
2. Có tiêu đề chính (Headline) hấp dẫn.
3. Có đoạn mở đầu (Lead) thu hút, tập trung giải quyết Pain Points.
4. Triển khai đầy đủ các tiêu đề H2 và H3 theo dàn ý.
5. Phân tích rõ tính năng và lợi ích của AI Chatbot.
6. Sử dụng từ khóa SEO chính và từ khóa phụ tự nhiên.
7. Có lời kêu gọi hành động (CTA) rõ ràng ở cuối bài.
8. Nội dung chuyên sâu, có ví dụ minh họa phù hợp.

# SEO OPTIMIZATION
- Từ khóa chính xuất hiện tự nhiên trong tiêu đề, đoạn mở đầu và nội dung.
- Sử dụng từ khóa phụ trong các tiêu đề H2, H3 khi phù hợp.
- Không nhồi nhét từ khóa.
- Viết Meta Description hấp dẫn, dài khoảng 150–160 ký tự.
- Đảm bảo nội dung dễ đọc, có đoạn văn rõ ràng.

# CONTEXT CONSISTENCY
- Giữ nguyên đối tượng khách hàng mục tiêu từ Prompt 1.
- Giữ nguyên thông điệp truyền thông và cấu trúc từ Prompt 2.
- Không tự ý thay đổi thứ tự các tiêu đề.
- Không thêm thông tin hoặc số liệu chưa được cung cấp.
- Duy trì giọng văn chuyên nghiệp, tin cậy trong toàn bộ bài viết.

# OUTPUT FORMAT
1. SEO Title
2. Meta Description
3. Headline
4. Lead
5. Nội dung bài viết với đầy đủ H2 và H3
6. CTA

# CONSTRAINTS
- Không bỏ sót bất kỳ phần nào trong dàn ý.
- Không lặp ý giữa các đoạn.
- Không viết nội dung chung chung, thiếu chiều sâu.
- Nếu chưa đủ dữ liệu về sản phẩm, hãy ghi rõ thông tin cần bổ sung.
- Nếu bài viết vượt giới hạn Token, phải dừng tại cuối một đoạn hoàn chỉnh và thông báo vị trí đang dừng.

## 4. Quy trình truyền dữ liệu giữa các Prompt

Quy trình Prompt Chaining được thực hiện theo thứ tự:

**Prompt 1 → Prompt 2 → Prompt 3**

- Prompt 1 nhận thông tin sản phẩm và phân tích khách hàng mục tiêu, Pain Points.
- Prompt 2 nhận toàn bộ kết quả Prompt 1 để xây dựng dàn ý bài PR.
- Prompt 3 nhận kết quả Prompt 1 và Prompt 2 để triển khai bài viết hoàn chỉnh.

**Nguyên tắc truyền Context:**

- Không bỏ qua đầu ra của Prompt trước.
- Không tự ý thay đổi thông tin khách hàng mục tiêu.
- Giữ nguyên thông điệp truyền thông xuyên suốt.
- Duy trì cấu trúc nội dung và giọng văn thống nhất.
- Nếu phát hiện thông tin mâu thuẫn, phải yêu cầu xác nhận trước khi tiếp tục.

## 5. Xử lý lỗi đứt gãy ngữ cảnh khi AI đạt giới hạn Token

Trong quá trình viết bài dài 1.000–1.500 từ, AI có thể bị ngắt giữa chừng do giới hạn Token.

Để khắc phục, sử dụng kỹ thuật Continue Prompting.

**Prompt tiếp tục viết:**

Hãy tiếp tục viết bài PR từ chính xác vị trí đã dừng ở phản hồi trước.

YÊU CẦU:
1. Giữ nguyên chủ đề và mục tiêu bài viết.
2. Giữ nguyên giọng văn chuyên nghiệp, tin cậy.
3. Tuân thủ dàn ý H2 và H3 đã thống nhất.
4. Không viết lại những nội dung đã hoàn thành.
5. Không lặp lại tiêu đề hoặc đoạn văn trước đó.
6. Tiếp tục đúng ý của câu và đoạn đang triển khai.
7. Duy trì từ khóa SEO một cách tự nhiên.
8. Đảm bảo tổng độ dài bài viết đạt 1.000–1.500 từ.

THÔNG TIN NGỮ CẢNH:
- Phần đã hoàn thành: [Ghi rõ phần đã viết].
- Tiêu đề cuối cùng đã hoàn thành: [Ghi tiêu đề].
- Vị trí cần tiếp tục: [Ghi tiêu đề hoặc đoạn tiếp theo].
- Nội dung cuối cùng đã viết: [Dán đoạn cuối của phản hồi trước].

Hãy tiếp tục ngay từ phần còn thiếu, không mở đầu lại bài viết.

**Nguyên tắc xử lý:**

- Lưu lại nội dung đã hoàn thành trước khi tiếp tục.
- Cung cấp lại dàn ý và các thông tin quan trọng nếu phiên chat bị mất ngữ cảnh.
- Xác định chính xác tiêu đề và đoạn văn cuối cùng.
- Không yêu cầu AI viết lại những phần đã hoàn thành.
- Kiểm tra sự liên kết giữa phần cũ và phần mới.

## 6. Kiểm tra và đánh giá kết quả

Sau khi hoàn thành Prompt 3, sử dụng các tiêu chí sau để đánh giá:

| Tiêu chí | Yêu cầu |
|---|---|
| Độ dài | 1.000–1.500 từ |
| Tiêu đề | Thu hút, đúng chủ đề |
| Nội dung | Đầy đủ, chuyên sâu |
| Cấu trúc | Có H1, H2, H3 rõ ràng |
| SEO | Có từ khóa chính và phụ |
| Giọng văn | Chuyên nghiệp, tin cậy |
| Tính nhất quán | Không thay đổi thông điệp |
| CTA | Rõ ràng, có tính thuyết phục |
| Context | Không bị mất hoặc sai lệch ngữ cảnh |

## 7. Kết luận

Kỹ thuật Prompt Chaining giúp chia một nhiệm vụ phức tạp thành nhiều công đoạn nhỏ, có sự liên kết và kế thừa dữ liệu giữa các bước.

Trong bài tập này, quy trình gồm 3 Prompt:

- **Prompt 1:** Nghiên cứu khách hàng mục tiêu và xác định Pain Points.
- **Prompt 2:** Xây dựng dàn ý bài viết PR dựa trên kết quả nghiên cứu.
- **Prompt 3:** Triển khai bài viết hoàn chỉnh và tối ưu SEO.

Bên cạnh đó, kỹ thuật Continue Prompting giúp xử lý tình trạng AI bị ngắt giữa chừng, duy trì tính nhất quán và đảm bảo nội dung không bị lặp lại.

**Kết quả:** Tạo ra quy trình viết bài PR sản phẩm công nghệ chuyên nghiệp, có cấu trúc rõ ràng, nội dung chuyên sâu, chuẩn SEO và hạn chế lỗi đứt gãy ngữ cảnh.
