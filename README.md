# Project1-DoTa
Project1-Dota created by GitHub Classroom
- Website giới thiệu sản phẩm: https://dotahilu.github.io/
# Danh sách thành viên nhóm:
1. Phạm Anh Quốc - 1612543 (trưởng nhóm)
2. Hoàng Thiên Nữ - 1612880
3. Võ Thị My Ny - 1612881
4. Cao Nguyễn Minh Hiếu - 1512157

# Ý tưởng : Trang web hỗ trợ tìm kiếm trung tâm học tiếng Anh phù hợp- English Center Finding Helper
## Làm gì?
--> Tạo một website cho phép người dùng xem review của những học viên trước đó về các trung tâm Anh ngữ, cũng như cho phép người dùng để lại review về trung tâm mà mình đã học, từ đó giúp đỡ nhau tìm một nơi học Anh văn tốt nhất.
--> Thông qua website, các trung tâm Anh ngữ cũng có thể quảng bá cho thương hiệu của mình.

## Đối tượng hướng đến?
- Những người cần tìm một nơi học tiếng Anh chất lượng.
- Những người đã từng học tại các trung tâm tiếng Anh, và muốn chia sẻ kinh nghiệm về trung tâm ấy.
- Những trung tâm Anh ngữ muốn tìm kiếm học viên, đặc biệt là những trung tâm mới mở.

## Tại sao làm?
Trong thời đại hội nhập, nhu cầu học Anh văn của học sinh sinh viên đang ngày càng tăng cao.
Việc tìm kiếm một nơi học tiếng Anh phổ biến thường thông qua các bước:
![GitHub Logo](/QuyTrinhCu.png)

## Giải pháp chung:
* Tạo một webapp chuyên tìm kiếm các trung tâm Anh ngữ -> giúp giải quyết những hạn chế của bước tìm kiếm nêu trên, đồng thời thông tin người dùng cần biết được hiển thị đầy đủ, dễ nhìn, dễ so sánh.
* Trang web cho phép người dùng comment về chất lượng những trung tâm này -> giúp những người học sau có được lời khuyên thiết thực, khách quan, chính xác về nơi mình muốn học.
* Trang web có các chức năng tính điểm cho reviewer -> khuyến khích cựu học viên bình luận
* Trang web có các ưu đãi cho trung tâm -> khuyến khích những trung tâm Anh ngữ cùng hợp tác.

## Lợi ích mỗi bên:
### Người dùng:
- Tìm được môi trường học phù hợp một cách nhanh chóng, tiện lợi, chính xác hơn.
- Đối với những reviewer, tích đủ điểm sẽ nhận được những phần quà giá trị như voucher giảm học phí, từ điển, e-book, bộ CV mẫu, ...
- Giao lưu kết bạn, cùng nhau chia sẻ kinh nghiệm.
### Trung tâm Anh ngữ:
- Có một nơi quảng cáo miễn phí.
- Nắm bắt được tâm lí học viên, từ đó thay đổi phương pháp giảng dạy sao cho hiệu quả và thu hút được nhiều học viên.
### Nhóm - ban quản trị website:
- Tạo được một cộng đồng học Anh văn rộng lớn, dược nhiều người biết đến.
- Nếu thành công, nhóm sẽ làm thêm mobile app, kiếm tiền từ quảng cáo.

# Giải pháp chi tiết:

## Về mặt kĩ thuật:
### Cơ chế Login:
- Để bình luận hoặc đặt câu hỏi, người dùng cần một tài khoản  trên cơ sở dữ liệu của website. Website cho phép người dùng tạo tài khoản bằng Facebook hoặc Google account.
- Cơ chế login như sau:
 ![GitHub Logo](/CoCheLogin.png)

### Gửi mail tự động:
- Sau khi người dùng bình luận, họ có thể cần nhận thông báo khi có ai đó reply bình luận của họ. Website chọn phương pháp thông báo là gửi mail tự động.
- Phương thức gửi mail tự động:
    1. Người dùng nhấn submit comment
    2. Từ web client gửi tín hiệu đến web server.
    3. Server xử lý tín hiệu:
        Nếu là tín hiệu gửi mail, server lấy id người dùng vừa gửi để lấy mail trong cơ sở dữ liệu. Từ đó gửi mail đến cho người dùng.
        Ngược lại, xử lý tín hiệu khác.

### Thuật toán tìm kiếm:
- Website cho phép người dùng tìm kiếm trung tâm theo mong muốn. Người dùng có thể:
    Tìm kiếm bằng cách nhập text
    Tìm kiếm thông tin nâng cao với các mục: địa chỉ, học phí, môn học
- Để tìm kiếm trong trang web, nhóm sẽ sử dụng custom search engine được cung cấp sẵn của Google. Link: https://cse.google.com/cse/
- Cơ chế hoạt động của search egine Google:
    1. Google đã sử dụng các web crawler, spider để tạo cơ sở dữ liệu.
    2. Khi người dùng nhập chuỗi, google sẽ sử dụng thuật toán Penguin để xử lý (https://moz.com/google-algorithm-change)
    3. Gửi trả lại kết quả theo độ ưu tiên đã định.

## Về mặt thương mại:
### Cách tính điểm cho reviewer và quà tặng:
- Với mỗi lượt đánh giá và bình luận, người dùng sẽ được hệ thống tích lũy điểm. Đến khi đạt được số điểm theo quy định, sẽ được nhận voucher giảm giá cho khóa học tiếng Anh tại các trung tâm. Cách tính điểm được tính như sau:
- Điểm cộng:        Bình luận: 5d     Hình ảnh: 1d     Trả lời bình luận: 0,25d     Báo lỗi: 5d
- Các điểm cộng khác:
    + Khi tạo tài khoản, người dùng hoàn thành profile của mình hết 100% và được hệ thống xác thực được tặng 10 điểm.
    + Website cung cấp các tiêu chí đánh giá trung tâm bao gồm: cơ sở vật chất, học phí, chất lượng giảng dạy. Người dùng đánh giá mỗi tiêu chí được cộng 1 điểm.
    + Combo: Trong 1 lần truy cập duy nhất, người dùng làm cả đánh giá, bình luận, trong đó có ít nhất 1 hình ảnh, được cộng 4đ.
- Điểm trừ:
    Trừ 50% : bình luận quá ngắn, tiếng Việt không dấu, nội dung không rõ ràng.
    Trừ 100%: hình ảnh không phải của mình hoặc của mình nhưng đăng lại nhiều lần, ảnh mờ (độ phân giải tối thiểu 720x960px),
              spam, nội dung quảng cáo, không lành mạnh.
- Với mỗi bình luận, hình ảnh người dùng sẽ được hệ thống kiểm duyệt trong vòng 48 giờ. Sau đó, điểm sẽ được tự động cập nhật.
* Quà tặng:
    -  50 điểm: voucher giảm học phí 200.000 đồng
    -  80 điểm: voucher giảm học phí 400.000 đồng
    - 100 điểm: voucher giảm học phí 800.000 đồng

### Quảng cáo website:
- Thời gian đầu, khi website chưa được biết đến, cần có phương pháp marketing để đem website đến với người dùng.
// đang cập nhật...

### Giữ chân người dùng
- Sau khi tìm được nơi học phù hợp, cần có chiến lược thu hút người dùng ghé thăm website lần nữa.
// đang cập nhật

## Cần học những môn gì ?
- Để xây dựng website:
    + Nhập môn Công nghệ phần mềm
    + Quản lí dự án phần mềm
    + Phát triển ứng dụng web
- Để quản lí, bảo mật, truy xuất thông tin người dùng:
    + Hệ quản trị cơ cở dữ liệu
    + Phân tích thiết kế Hệ thống thông tin
    + An toàn và bảo mật Hệ thống thông tin
- Để có chính sách tốt trong việc cải thiện trải nghiệm người dùng:
    + Tương tác người - máy
    + Thương mại điện tử
    
---------------------------------------------------------------------------------------------------------------------------------------
