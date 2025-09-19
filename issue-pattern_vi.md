# Issue Patterns for Software Development & AMS

## 1. Bug Issues

### 1.1 Logic Errors

- **Pattern**: Code không hoạt động theo đúng business logic
- **Business Definition**: Phần mềm tính toán hoặc xử lý dữ liệu sai so với yêu cầu kinh doanh thực tế
- **Keywords Explained**:
  - **Business Logic**: Quy tắc kinh doanh được lập trình vào hệ thống (ví dụ: cách tính lương, quy trình phê duyệt)
  - **Code**: Mã nguồn phần mềm
- **Examples**:
  - Calculation errors in financial modules (Lỗi tính toán trong module tài chính)
  - Incorrect condition checks in workflows (Kiểm tra điều kiện sai trong quy trình làm việc)
  - Wrong data validation rules (Quy tắc kiểm tra dữ liệu sai)
- **Issue Sample**:
  - *Tình huống*: Hệ thống tính lương tính thuế thu nhập cá nhân sai công thức
  - *Biểu hiện*: Nhân viên nhận lương ít hơn hoặc nhiều hơn quy định
  - *Tác động kinh doanh*: Công ty có thể bị kiểm tra thuế, nhân viên khiếu nại
- **Severity**: Medium to High
- **Impact**: Functional incorrectness

### 1.2 Runtime Exceptions/Crashes

- **Pattern**: Application crashes hoặc throws unexpected exceptions
- **Business Definition**: Phần mềm đột ngột ngừng hoạt động hoặc hiển thị thông báo lỗi không mong muốn
- **Keywords Explained**:
  - **Runtime**: Thời gian phần mềm đang chạy
  - **Exception**: Lỗi xảy ra khi phần mềm đang hoạt động
  - **Crashes**: Phần mềm đột ngột tắt hoặc treo
- **Examples**:
  - NullPointerException (Lỗi truy cập dữ liệu không tồn tại)
  - IndexOutOfBoundsException (Lỗi truy cập vượt quá giới hạn dữ liệu)
  - Database connection timeouts (Hết thời gian kết nối cơ sở dữ liệu)
- **Issue Sample**:
  - *Tình huống*: Hệ thống CRM đột ngột tắt khi nhân viên đang nhập thông tin khách hàng
  - *Biểu hiện*: Màn hình hiển thị "Application has stopped working"
  - *Tác động kinh doanh*: Mất dữ liệu vừa nhập, gián đoạn công việc, khách hàng phải chờ
- **Severity**: High to Critical
- **Impact**: Application unavailability

### 1.3 Data Corruption

- **Pattern**: Data bị modify không đúng hoặc bị mất
- **Business Definition**: Thông tin trong hệ thống bị thay đổi sai hoặc bị mất mà không có sự cho phép
- **Keywords Explained**:
  - **Data Corruption**: Dữ liệu bị hỏng, không còn chính xác
  - **Database Transaction**: Giao dịch cơ sở dữ liệu (một loạt thao tác phải hoàn thành cùng lúc)
  - **Encoding/Decoding**: Quá trình chuyển đổi dữ liệu giữa các định dạng khác nhau
- **Examples**:
  - Incomplete database transactions (Giao dịch cơ sở dữ liệu không hoàn tất)
  - File corruption during write operations (File bị hỏng khi ghi dữ liệu)
  - Encoding/decoding errors (Lỗi mã hóa/giải mã dữ liệu)
- **Issue Sample**:
  - *Tình huống*: Hệ thống thanh toán bị gián đoạn khi đang xử lý giao dịch chuyển tiền
  - *Biểu hiện*: Tiền bị trừ ở tài khoản A nhưng không được cộng vào tài khoản B
  - *Tác động kinh doanh*: Khách hàng mất tiền, ngân hàng phải bồi thường, mất uy tín
- **Severity**: Critical
- **Impact**: Data integrity loss

### 1.4 Memory Leaks

- **Pattern**: Memory usage tăng dần theo thời gian
- **Business Definition**: Hệ thống sử dụng ngày càng nhiều bộ nhớ máy tính, dẫn đến chạy chậm và có thể treo máy
- **Keywords Explained**:
  - **Memory**: Bộ nhớ máy tính (RAM)
  - **Memory Leak**: Rò rỉ bộ nhớ - phần mềm không giải phóng bộ nhớ sau khi sử dụng
  - **Garbage Collection**: Quá trình tự động dọn dẹp bộ nhớ không dùng nữa
  - **Resources**: Tài nguyên hệ thống (files, connections)
- **Examples**:
  - Objects không được garbage collected (Đối tượng không được dọn dẹp tự động)
  - Unclosed resources (files, connections) (Không đóng các tài nguyên như file, kết nối)
  - Circular references (Tham chiếu vòng tròn)
- **Issue Sample**:
  - *Tình huống*: Phần mềm kế toán chạy chậm dần sau vài giờ sử dụng
  - *Biểu hiện*: Máy tính chạy chậm, quạt chạy ồn, cuối cùng phần mềm không phản hồi
  - *Tác động kinh doanh*: Nhân viên phải khởi động lại máy thường xuyên, giảm năng suất làm việc
- **Severity**: High
- **Impact**: Performance degradation, system crashes

### 1.5 Performance Degradation

- **Pattern**: Application chạy chậm hơn expected
- **Business Definition**: Hệ thống hoạt động chậm hơn mức độ người dùng mong đợi
- **Keywords Explained**:
  - **Performance**: Hiệu suất hoạt động của hệ thống
  - **Database Query**: Truy vấn cơ sở dữ liệu
  - **Algorithm**: Thuật toán - cách thức hệ thống xử lý dữ liệu
  - **Network Bottleneck**: Tắc nghẽn mạng
- **Examples**:
  - Slow database queries (Truy vấn cơ sở dữ liệu chậm)
  - Inefficient algorithms (Thuật toán không hiệu quả)
  - Network bottlenecks (Tắc nghẽn mạng)
- **Issue Sample**:
  - *Tình huống*: Website bán hàng mất 30 giây để tải trang sản phẩm
  - *Biểu hiện*: Khách hàng phải chờ lâu, trang web phản hồi chậm
  - *Tác động kinh doanh*: Khách hàng bỏ đi, giảm doanh số, ảnh hưởng danh tiếng
- **Severity**: Medium to High
- **Impact**: User experience degradation

### 1.6 UI/UX Inconsistencies

- **Pattern**: Interface không consistent hoặc không user-friendly
- **Business Definition**: Giao diện người dùng không thống nhất hoặc khó sử dụng, gây khó khăn cho người dùng
- **Keywords Explained**:
  - **UI (User Interface)**: Giao diện người dùng - những gì người dùng nhìn thấy trên màn hình
  - **UX (User Experience)**: Trải nghiệm người dùng - cảm giác khi sử dụng hệ thống
  - **Responsive Design**: Thiết kế tự động điều chỉnh theo kích thước màn hình
  - **Accessibility**: Khả năng tiếp cận cho người khuyết tật
- **Examples**:
  - Different styling across pages (Phong cách thiết kế khác nhau giữa các trang)
  - Broken responsive design (Thiết kế responsive bị lỗi)
  - Poor accessibility compliance (Tuân thủ khả năng tiếp cận kém)
- **Issue Sample**:
  - *Tình huống*: Website công ty có màu sắc, font chữ khác nhau ở mỗi trang, nút bấm ở vị trí khác nhau
  - *Biểu hiện*: Nhân viên bối rối khi chuyển trang, khách hàng khó tìm thông tin cần thiết
  - *Tác động kinh doanh*: Giảm hiệu quả làm việc, khách hàng có ấn tượng xấu về thương hiệu
- **Severity**: Low to Medium
- **Impact**: User satisfaction reduction

### 1.7 Integration Failures

- **Pattern**: Các component/service không communicate được với nhau
- **Business Definition**: Các bộ phận của hệ thống không thể giao tiếp với nhau hoặc với hệ thống bên ngoài
- **Keywords Explained**:
  - **Component**: Bộ phận/module của hệ thống
  - **Service**: Dịch vụ phần mềm
  - **API Endpoint**: Điểm kết nối để trao đổi dữ liệu
  - **Message Queue**: Hàng đợi tin nhắn - hệ thống truyền tải thông tin giữa các bộ phận
  - **Third-party**: Bên thứ ba - dịch vụ của công ty khác
- **Examples**:
  - API endpoint failures (Lỗi điểm kết nối API)
  - Message queue connection issues (Vấn đề kết nối hàng đợi tin nhắn)
  - Third-party service unavailability (Dịch vụ bên thứ ba không khả dụng)
- **Issue Sample**:
  - *Tình huống*: Hệ thống CRM không thể kết nối với hệ thống Email Marketing để gửi email tự động
  - *Biểu hiện*: Email khuyến mãi không được gửi đi, khách hàng không nhận được thông báo
  - *Tác động kinh doanh*: Mất cơ hội bán hàng, khách hàng cảm thấy bị bỏ rơi, giảm doanh thu
- **Severity**: High
- **Impact**: System functionality breakdown

## 2. Security Issues

### 2.1 Authentication Vulnerabilities

- **Pattern**: Weakness trong authentication mechanism
- **Business Definition**: Hệ thống xác thực danh tính người dùng có lỗ hổng, cho phép kẻ xấu giả mạo
- **Keywords Explained**:
  - **Authentication**: Xác thực danh tính - kiểm tra người dùng có phải là người họ tự nhận
  - **Password Policy**: Chính sách mật khẩu
  - **Session Hijacking**: Đánh cắp phiên đăng nhập
  - **Multi-factor Authentication (MFA)**: Xác thực đa yếu tố (mật khẩu + SMS/email)
- **Examples**:
  - Weak password policies (Chính sách mật khẩu yếu)
  - Session hijacking vulnerabilities (Lỗ hổng đánh cắp phiên đăng nhập)
  - Multi-factor authentication bypass (Bỏ qua xác thực đa yếu tố)
- **Issue Sample**:
  - *Tình huống*: Hệ thống cho phép mật khẩu chỉ có 4 ký tự, không có yêu cầu ký tự đặc biệt
  - *Biểu hiện*: Hacker dễ dàng đoán mật khẩu và đăng nhập vào tài khoản người khác
  - *Tác động kinh doanh*: Mất dữ liệu khách hàng, vi phạm bảo mật, mất uy tín, có thể bị phạt
- **Severity**: High to Critical
- **Impact**: Unauthorized access

### 2.2 Authorization Bypass

- **Pattern**: Users có thể access resources mà họ không có permission
- **Business Definition**: Người dùng có thể truy cập thông tin hoặc chức năng mà họ không được phép
- **Keywords Explained**:
  - **Authorization**: Phân quyền - quyết định ai được làm gì
  - **Role-based Access Control**: Kiểm soát truy cập dựa trên vai trò
  - **Privilege Escalation**: Nâng cấp đặc quyền trái phép
  - **Access Control**: Kiểm soát truy cập
- **Examples**:
  - Role-based access control failures (Lỗi kiểm soát truy cập theo vai trò)
  - Privilege escalation vulnerabilities (Lỗ hổng nâng cấp đặc quyền)
  - Missing access controls (Thiếu kiểm soát truy cập)
- **Issue Sample**:
  - *Tình huống*: Nhân viên bán hàng có thể truy cập vào báo cáo tài chính dành cho giám đốc
  - *Biểu hiện*: Thông tin nhạy cảm bị lộ cho người không có thẩm quyền
  - *Tác động kinh doanh*: Thông tin tài chính bị rò rỉ, cạnh tranh không lành mạnh, vi phạm quy định
- **Severity**: High to Critical
- **Impact**: Data breach potential

### 2.3 Data Exposure

- **Pattern**: Sensitive data bị exposed không có authorization
- **Business Definition**: Dữ liệu nhạy cảm bị lộ ra ngoài mà không có sự cho phép
- **Keywords Explained**:
  - **Sensitive Data**: Dữ liệu nhạy cảm (thông tin cá nhân, tài chính)
  - **Encryption**: Mã hóa dữ liệu
  - **Data Transmission**: Truyền tải dữ liệu
  - **Information Disclosure**: Tiết lộ thông tin
- **Examples**:
  - Unencrypted data transmission (Truyền tải dữ liệu không mã hóa)
  - Information disclosure in error messages (Tiết lộ thông tin trong thông báo lỗi)
  - Insecure data storage (Lưu trữ dữ liệu không an toàn)
- **Issue Sample**:
  - *Tình huống*: Website hiển thị số thẻ tín dụng đầy đủ trong thông báo lỗi khi thanh toán thất bại
  - *Biểu hiện*: Thông tin thẻ tín dụng khách hàng có thể bị nhìn thấy bởi người khác
  - *Tác động kinh doanh*: Vi phạm PCI DSS, khách hàng mất tiền, công ty bị phạt nặng, mất giấy phép
- **Severity**: Critical
- **Impact**: Privacy violations, compliance issues

### 2.4 SQL Injection

- **Pattern**: Malicious SQL code có thể được execute
- **Business Definition**: Kẻ tấn công có thể chèn mã độc vào database để đánh cắp hoặc phá hoại dữ liệu
- **Keywords Explained**:
  - **SQL**: Ngôn ngữ truy vấn cơ sở dữ liệu
  - **Injection**: Chèn mã độc
  - **User Input**: Dữ liệu nhập từ người dùng
  - **Sanitize**: Làm sạch dữ liệu đầu vào
  - **Stored Procedure**: Thủ tục lưu trữ trong database
- **Examples**:
  - Unsanitized user inputs in queries (Dữ liệu đầu vào không được làm sạch)
  - Dynamic SQL construction vulnerabilities (Lỗ hổng xây dựng SQL động)
  - Stored procedure injection (Chèn mã vào thủ tục lưu trữ)
- **Issue Sample**:
  - *Tình huống*: Form tìm kiếm sản phẩm cho phép nhập ký tự đặc biệt mà không kiểm tra
  - *Biểu hiện*: Hacker nhập mã SQL độc và có thể xem toàn bộ database khách hàng
  - *Tác động kinh doanh*: Mất toàn bộ dữ liệu khách hàng, vi phạm nghiêm trọng quyền riêng tư, phá sản
- **Severity**: Critical
- **Impact**: Database compromise

### 2.5 Cross-Site Scripting (XSS)

- **Pattern**: Malicious scripts có thể execute trong browser
- **Business Definition**: Kẻ tấn công có thể chèn mã độc vào website để tấn công người dùng khác
- **Keywords Explained**:
  - **Cross-Site Scripting (XSS)**: Tấn công chèn script độc qua trang web
  - **Browser**: Trình duyệt web
  - **Script**: Mã lệnh chạy trên trang web
  - **Reflected XSS**: XSS phản xạ qua URL
  - **Stored XSS**: XSS được lưu trong database
  - **DOM**: Document Object Model - cấu trúc trang web
- **Examples**:
  - Reflected XSS in search parameters (XSS phản xạ trong tham số tìm kiếm)
  - Stored XSS in user comments (XSS được lưu trong bình luận người dùng)
  - DOM-based XSS vulnerabilities (Lỗ hổng XSS dựa trên DOM)
- **Issue Sample**:
  - *Tình huống*: Form bình luận cho phép nhập HTML/JavaScript mà không kiểm tra
  - *Biểu hiện*: Khi khách hàng khác xem bình luận, mã độc chạy và đánh cắp thông tin đăng nhập
  - *Tác động kinh doanh*: Khách hàng bị hack, mất niềm tin, website bị đưa vào blacklist
- **Severity**: Medium to High
- **Impact**: Client-side attacks

### 2.6 API Security Flaws

- **Pattern**: API endpoints có security vulnerabilities
- **Business Definition**: Các điểm kết nối API có lỗ hổng bảo mật
- **Keywords Explained**:
  - **API (Application Programming Interface)**: Giao diện lập trình ứng dụng
  - **Endpoint**: Điểm cuối API - URL để truy cập dịch vụ
  - **Rate Limiting**: Giới hạn số lượng request
  - **Direct Object Reference**: Tham chiếu trực tiếp đến đối tượng
  - **Input Validation**: Kiểm tra dữ liệu đầu vào
- **Examples**:
  - Missing rate limiting (Thiếu giới hạn tần suất truy cập)
  - Insecure direct object references (Tham chiếu đối tượng không an toàn)
  - Insufficient input validation (Kiểm tra đầu vào không đủ)
- **Issue Sample**:
  - *Tình huống*: API không giới hạn số lần gọi, cho phép truy cập file bằng ID bất kỳ
  - *Biểu hiện*: Hacker có thể tải về mọi file trong hệ thống bằng cách thay đổi ID
  - *Tác động kinh doanh*: Mất toàn bộ dữ liệu công ty, thông tin bí mật bị lộ
- **Severity**: High
- **Impact**: System compromise

### 2.7 Dependency Vulnerabilities

- **Pattern**: Third-party libraries có known vulnerabilities
- **Business Definition**: Các thư viện phần mềm của bên thứ ba có lỗ hổng bảo mật đã biết
- **Keywords Explained**:
  - **Third-party Libraries**: Thư viện phần mềm của bên thứ ba
  - **Dependencies**: Phụ thuộc - các component cần thiết cho hệ thống
  - **Framework**: Khung phần mềm
  - **npm packages**: Gói phần mềm JavaScript
  - **Patch**: Bản vá lỗi
- **Examples**:
  - Outdated framework versions (Phiên bản framework cũ)
  - Vulnerable npm packages (Gói npm có lỗ hổng)
  - Unpatched security flaws (Lỗ hổng bảo mật chưa được vá)
- **Issue Sample**:
  - *Tình huống*: Website sử dụng thư viện JavaScript cũ có lỗ hổng bảo mật đã công bố
  - *Biểu hiện*: Hacker khai thác lỗ hổng này để chiếm quyền điều khiển website
  - *Tác động kinh doanh*: Website bị hack, dữ liệu khách hàng bị đánh cắp, phải đóng cửa tạm thời
- **Severity**: Medium to Critical
- **Impact**: Inherited security risks

## 3. Performance Issues

### 3.1 Slow Response Times

- **Pattern**: API/page response times vượt quá acceptable thresholds
- **Business Definition**: Thời gian phản hồi của hệ thống chậm hơn mức có thể chấp nhận được
- **Keywords Explained**:
  - **Response Time**: Thời gian phản hồi
  - **API**: Giao diện lập trình ứng dụng
  - **Threshold**: Ngưỡng, giới hạn cho phép
  - **Database Query**: Truy vấn cơ sở dữ liệu
  - **Thread**: Luồng xử lý
- **Examples**:
  - Database query timeouts (Truy vấn database bị timeout)
  - Heavy computation blocking threads (Tính toán nặng chặn luồng xử lý)
  - Network latency issues (Vấn đề độ trễ mạng)
- **Issue Sample**:
  - *Tình huống*: Trang web thương mại điện tử mất 15 giây để hiển thị kết quả tìm kiếm
  - *Biểu hiện*: Khách hàng phải chờ lâu, nhiều người bỏ cuộc và thoát
  - *Tác động kinh doanh*: Mất 40% khách hàng tiềm năng, giảm 25% doanh thu, uy tín giảm
- **Severity**: Medium to High
- **Impact**: Poor user experience

### 3.2 High CPU/Memory Usage

- **Pattern**: System resources usage abnormally high
- **Business Definition**: Hệ thống sử dụng quá nhiều tài nguyên máy tính (CPU/RAM) một cách bất thường
- **Keywords Explained**:
  - **CPU**: Bộ xử lý trung tâm
  - **Memory**: Bộ nhớ (RAM)
  - **System Resources**: Tài nguyên hệ thống
  - **Infinite Loop**: Vòng lặp vô hạn
  - **Recursive Call**: Gọi đệ quy
- **Examples**:
  - Infinite loops or recursive calls (Vòng lặp vô hạn hoặc gọi đệ quy)
  - Memory-intensive operations (Thao tác tốn nhiều bộ nhớ)
  - CPU-bound algorithms (Thuật toán tốn nhiều CPU)
- **Issue Sample**:
  - *Tình huống*: Phần mềm kế toán sử dụng 90% CPU khi tính báo cáo tháng
  - *Biểu hiện*: Máy tính chạy rất chậm, quạt kêu to, các ứng dụng khác không phản hồi
  - *Tác động kinh doanh*: Nhân viên không thể làm việc, deadline báo cáo bị trễ
- **Severity**: High
- **Impact**: System instability

### 3.3 Database Query Optimization

- **Pattern**: Database operations không optimized
- **Business Definition**: Các thao tác truy vấn cơ sở dữ liệu chưa được tối ưu hóa
- **Keywords Explained**:
  - **Database Query**: Truy vấn cơ sở dữ liệu
  - **Index**: Chỉ mục database để tăng tốc truy vấn
  - **N+1 Query**: Vấn đề truy vấn nhiều lần không cần thiết
  - **Join**: Phép nối bảng trong database
  - **Optimization**: Tối ưu hóa
- **Examples**:
  - Missing indexes on frequently queried columns (Thiếu chỉ mục trên cột thường truy vấn)
  - N+1 query problems (Vấn đề truy vấn N+1)
  - Complex joins without optimization (Phép nối phức tạp không tối ưu)
- **Issue Sample**:
  - *Tình huống*: Báo cáo khách hàng mất 10 phút để tải vì truy vấn không có index
  - *Biểu hiện*: Nhân viên phải chờ lâu, hệ thống trở nên chậm chạp
  - *Tác động kinh doanh*: Giảm năng suất làm việc, khách hàng phàn nàn về dịch vụ chậm
- **Severity**: Medium to High
- **Impact**: Application slowdown

### 3.4 Network Latency

- **Pattern**: Network communication delays
- **Business Definition**: Độ trễ trong việc truyền tải dữ liệu qua mạng
- **Keywords Explained**:
  - **Network Latency**: Độ trễ mạng
  - **Payload**: Dữ liệu được truyền
  - **Round Trip**: Chu kỳ gửi và nhận dữ liệu
  - **Protocol**: Giao thức truyền thông
- **Examples**:
  - Large payload sizes (Kích thước dữ liệu lớn)
  - Multiple round trips (Nhiều chu kỳ truyền tải)
  - Inefficient protocols (Giao thức không hiệu quả)
- **Issue Sample**:
  - *Tình huống*: Upload file lớn lên hệ thống quản lý tài liệu mất 30 phút
  - *Biểu hiện*: Nhân viên chờ lâu, kết nối thường bị ngắt
  - *Tác động kinh doanh*: Giảm hiệu quả công việc, tăng chi phí nhân công
- **Severity**: Medium
- **Impact**: Response time increase

### 3.5 Caching Problems

- **Pattern**: Caching mechanism không effective
- **Business Definition**: Hệ thống lưu trữ tạm thời không hoạt động hiệu quả
- **Keywords Explained**:
  - **Cache**: Bộ nhớ đệm - lưu trữ tạm thời để tăng tốc
  - **Cache Miss**: Không tìm thấy dữ liệu trong cache
  - **Stale Data**: Dữ liệu cũ
  - **Cache Invalidation**: Làm mới cache
- **Examples**:
  - Cache miss rates too high (Tỷ lệ cache miss quá cao)
  - Stale cache data (Dữ liệu cache cũ)
  - Cache invalidation issues (Vấn đề làm mới cache)
- **Issue Sample**:
  - *Tình huống*: Giá sản phẩm hiển thị sai vì cache không được cập nhật
  - *Biểu hiện*: Khách hàng thấy giá cũ, thanh toán bị lỗi
  - *Tác động kinh doanh*: Khách hàng khiếu nại, mất uy tín, có thể mất tiền
- **Severity**: Medium
- **Impact**: Performance degradation

### 3.6 Load Balancing Issues

- **Pattern**: Traffic distribution không even across servers
- **Business Definition**: Phân phối tải không đều giữa các máy chủ
- **Keywords Explained**:
  - **Load Balancing**: Cân bằng tải
  - **Traffic Distribution**: Phân phối lưu lượng
  - **Backend Server**: Máy chủ phía sau
  - **Algorithm**: Thuật toán
  - **Session Affinity**: Gắn kết phiên
- **Examples**:
  - Unhealthy backend servers (Máy chủ backend không khỏe)
  - Incorrect load balancing algorithms (Thuật toán cân bằng tải sai)
  - Session affinity problems (Vấn đề gắn kết phiên)
- **Issue Sample**:
  - *Tình huống*: Một máy chủ xử lý 80% traffic trong khi máy khác nhàn rỗi
  - *Biểu hiện*: Website chậm vào giờ cao điểm, một số người dùng không vào được
  - *Tác động kinh doanh*: Mất khách hàng, giảm doanh thu trong giờ vàng
- **Severity**: High
- **Impact**: System overload

## 4. Infrastructure Issues

### 4.1 Server Downtime

- **Pattern**: Servers become unavailable
- **Business Definition**: Máy chủ ngừng hoạt động, không thể cung cấp dịch vụ
- **Keywords Explained**:
  - **Server**: Máy chủ
  - **Downtime**: Thời gian ngừng hoạt động
  - **Hardware Failure**: Lỗi phần cứng
  - **Operating System**: Hệ điều hành
- **Examples**:
  - Hardware failures (Lỗi phần cứng)
  - Operating system crashes (Sự cố hệ điều hành)
  - Power outages (Mất điện)
- **Issue Sample**:
  - *Tình huống*: Máy chủ chính bị hỏng ổ cứng, toàn bộ website ngừng hoạt động
  - *Biểu hiện*: Khách hàng không thể truy cập website, nhân viên không làm việc được
  - *Tác động kinh doanh*: Mất doanh thu, khách hàng chuyển sang đối thủ, uy tín giảm
- **Severity**: Critical
- **Impact**: Service unavailability

### 4.2 Deployment Failures

- **Pattern**: Application deployment process fails
- **Business Definition**: Quá trình triển khai phần mềm lên server bị thất bại
- **Keywords Explained**:
  - **Deployment**: Triển khai phần mềm
  - **Build Pipeline**: Quy trình build tự động
  - **Configuration**: Cấu hình hệ thống
  - **Migration**: Di chuyển dữ liệu
- **Examples**:
  - Build pipeline errors (Lỗi quy trình build)
  - Configuration mismatches (Cấu hình không khớp)
  - Database migration failures (Lỗi migration database)
- **Issue Sample**:
  - *Tình huống*: Cập nhật phần mềm mới bị lỗi, website hiển thị trang trắng
  - *Biểu hiện*: Khách hàng không thể sử dụng dịch vụ, phải rollback về phiên bản cũ
  - *Tác động kinh doanh*: Trễ tính năng mới, tăng chi phí phát triển, mất lòng tin khách hàng
- **Severity**: High
- **Impact**: Release delays

### 4.3 Configuration Errors

- **Pattern**: System configuration không correct
- **Examples**:
  - Wrong environment variables
  - Incorrect firewall rules
  - DNS configuration issues
- **Severity**: Medium to High
- **Impact**: System malfunction

### 4.4 Environment Inconsistencies

- **Pattern**: Differences between environments cause issues
- **Examples**:
  - Dev vs Production configuration drift
  - Missing dependencies in staging
  - Version mismatches
- **Severity**: Medium to High
- **Impact**: Unpredictable behavior

### 4.5 Monitoring/Alerting Failures

- **Pattern**: Monitoring systems không detect issues
- **Examples**:
  - Missing metrics collection
  - Incorrect alert thresholds
  - Notification delivery failures
- **Severity**: Medium
- **Impact**: Delayed incident response

### 4.6 Backup/Recovery Problems

- **Pattern**: Backup or recovery processes fail
- **Examples**:
  - Corrupted backup files
  - Incomplete data restoration
  - Recovery time objective violations
- **Severity**: Critical
- **Impact**: Data loss risk

## 5. Integration Issues

### 5.1 API Connectivity Problems

- **Pattern**: Services cannot connect to external APIs
- **Examples**:
  - Network connectivity issues
  - API endpoint changes
  - Authentication token expiration
- **Severity**: High
- **Impact**: Feature unavailability

### 5.2 Third-Party Service Failures

- **Pattern**: External services become unavailable
- **Examples**:
  - Payment gateway downtime
  - Email service provider issues
  - Cloud service outages
- **Severity**: High
- **Impact**: Dependent functionality loss

### 5.3 Data Synchronization Issues

- **Pattern**: Data không sync properly between systems
- **Examples**:
  - Eventual consistency problems
  - Message ordering issues
  - Duplicate data processing
- **Severity**: Medium to High
- **Impact**: Data inconsistency

### 5.4 Message Queue Problems

- **Pattern**: Message queue system malfunctions
- **Examples**:
  - Message delivery failures
  - Queue overflow conditions
  - Dead letter queue accumulation
- **Severity**: High
- **Impact**: Asynchronous processing breakdown

### 5.5 Microservices Communication

- **Pattern**: Services trong microservices architecture cannot communicate
- **Examples**:
  - Service discovery failures
  - Circuit breaker activations
  - Timeout configuration issues
- **Severity**: High
- **Impact**: System functionality degradation

## 6. AMS Operational Issues

### 6.1 Service Degradation

- **Pattern**: Service quality decreases over time
- **Examples**:
  - Response time increases
  - Error rate increases
  - Throughput decreases
- **Severity**: Medium to High
- **Impact**: SLA violations

### 6.2 Capacity Planning

- **Pattern**: System capacity không sufficient for demand
- **Examples**:
  - Insufficient server resources
  - Database connection pool exhaustion
  - Storage capacity limits
- **Severity**: High
- **Impact**: Service unavailability

### 6.3 Resource Allocation

- **Pattern**: Resources không properly allocated
- **Examples**:
  - Uneven resource distribution
  - Resource contention issues
  - Inefficient resource utilization
- **Severity**: Medium
- **Impact**: Performance issues

### 6.4 SLA Violations

- **Pattern**: Service level agreements are not met
- **Examples**:
  - Availability below guaranteed levels
  - Response time exceeding limits
  - Recovery time violations
- **Severity**: High
- **Impact**: Customer dissatisfaction

### 6.5 Incident Escalation

- **Pattern**: Issues không resolved within expected timeframes
- **Examples**:
  - Delayed incident response
  - Inadequate severity classification
  - Poor communication during incidents
- **Severity**: Medium to High
- **Impact**: Extended downtime

## 7. AMS Maintenance Issues

### 7.1 Patch Management

- **Pattern**: System patches không properly applied
- **Examples**:
  - Security patches missing
  - Patch conflicts causing issues
  - Rollback procedures failing
- **Severity**: Medium to High
- **Impact**: Security vulnerabilities

### 7.2 Version Upgrades

- **Pattern**: Software upgrades cause problems
- **Examples**:
  - Compatibility issues with new versions
  - Data migration failures
  - Feature regression after upgrades
- **Severity**: High
- **Impact**: System instability

### 7.3 License Compliance

- **Pattern**: Software licensing requirements not met
- **Examples**:
  - Expired licenses
  - Over-deployment of licensed software
  - Audit compliance failures
- **Severity**: Medium
- **Impact**: Legal and financial risks

### 7.4 Documentation Updates

- **Pattern**: Documentation becomes outdated
- **Examples**:
  - Procedure documents not reflecting current state
  - API documentation inconsistencies
  - Training materials out of date
- **Severity**: Low to Medium
- **Impact**: Operational inefficiency

### 7.5 Change Management

- **Pattern**: Changes không properly managed
- **Examples**:
  - Unauthorized changes
  - Missing change approvals
  - Inadequate change testing
- **Severity**: Medium to High
- **Impact**: System instability

## 8. AMS Monitoring & Support Issues

### 8.1 Alert Configuration

- **Pattern**: Monitoring alerts không properly configured
- **Examples**:
  - False positive alerts
  - Missing critical alerts
  - Incorrect alert thresholds
- **Severity**: Medium
- **Impact**: Ineffective monitoring

### 8.2 Log Analysis

- **Pattern**: Log analysis processes are inadequate
- **Examples**:
  - Missing log aggregation
  - Insufficient log retention
  - Poor log search capabilities
- **Severity**: Medium
- **Impact**: Difficult troubleshooting

### 8.3 User Support Tickets

- **Pattern**: User support tickets không efficiently handled
- **Examples**:
  - Long resolution times
  - Inadequate first-level support
  - Poor ticket routing
- **Severity**: Medium
- **Impact**: User dissatisfaction

### 8.4 Knowledge Base Updates

- **Pattern**: Knowledge base becomes outdated
- **Examples**:
  - Missing troubleshooting guides
  - Outdated procedure documents
  - Incomplete FAQ sections
- **Severity**: Low to Medium
- **Impact**: Support inefficiency

### 8.5 Training Requirements

- **Pattern**: Staff training is inadequate
- **Examples**:
  - Lack of technical training
  - Missing process training
  - Outdated training materials
- **Severity**: Medium
- **Impact**: Operational errors

## 9. AMS Compliance & Governance

### 9.1 Audit Findings

- **Pattern**: Audit processes reveal compliance issues
- **Examples**:
  - Missing controls implementation
  - Inadequate documentation
  - Process non-compliance
- **Severity**: Medium to High
- **Impact**: Regulatory violations

### 9.2 Policy Violations

- **Pattern**: Organizational policies are not followed
- **Examples**:
  - Security policy violations
  - Data handling policy breaches
  - Access control policy non-compliance
- **Severity**: Medium to High
- **Impact**: Risk exposure

### 9.3 Risk Assessments

- **Pattern**: Risk management processes are inadequate
- **Examples**:
  - Missing risk identification
  - Inadequate risk mitigation
  - Outdated risk assessments
- **Severity**: Medium
- **Impact**: Unmanaged risks

### 9.4 Data Governance

- **Pattern**: Data management practices are insufficient
- **Examples**:
  - Poor data quality
  - Missing data lineage
  - Inadequate data classification
- **Severity**: Medium to High
- **Impact**: Data integrity issues

### 9.5 Regulatory Compliance

- **Pattern**: Regulatory requirements are not met
- **Examples**:
  - GDPR compliance failures
  - SOX compliance issues
  - Industry-specific regulation violations
- **Severity**: High to Critical
- **Impact**: Legal and financial penalties
