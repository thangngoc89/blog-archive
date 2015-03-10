---
layout: post
title: Tắt plugin Wordpress khi không vào được Bảng điều khiển
date: 2014-11-16 14:25:54.000000000 -05:00
---

Hôm qua mình có nghịch với mấy cái plugin WordPress và kết quả là không truy cập vào Bảng điểu khiển (Admin Dashboard) được nữa. Nên chẳng thể nào tắt plugin ấy đi được. Sau một hồi tìm kiếm, mình tìm ra tới 2 giải pháp để tắt plugin WordPress mà không cần truy cập và Bảng điều khiển. Mời các bạn tham khảo nếu đang gặp trường hợp này nhé.

<div class="toc_wrap_right toc_transparent no_bullets" id="toc_container">Contents

- [1. Tắt thông qua các trình quản lí file](#1_Tt_thng_qua_cc_trnh_qun_l_file)
- [ 2. Tắt thông qua cơ sở dữ liệu](#2_Tt_thng_qua_c_s_d_liu)
- [Kết luận](#Kt_lun)

</div>
# <span id="1_Tt_thng_qua_cc_trnh_qun_l_file">1. Tắt thông qua các trình quản lí file</span>

Bạn có thể dùng bất cứ công cụ quản lí file nào cũng được (FTP, SSH, cPanel,…) . Nguyên tắc cơ bản chính là đổi tên của thư mục plugin. Khi đó, WordPress sẽ tự động tắt plugin cho bạn.

Truy cập vào thư mục

wp-content/plugins

Thư mục này sẽ liệt kê tất cả các plugin đã được cài đặt trên site của bạn cả kích hoạt và không kích hoạt.

[![tắt plugin wordpress 1](https://khoanguyen.me/wp-content/uploads/2014/11/disable-wordpress-plugins-1-285x300.jpg)](https://khoanguyen.me/wp-content/uploads/2014/11/disable-wordpress-plugins-1.jpg)

Ví dụ: muốn tắt plugin TinyMCE-Advanced thì chỉ cần đổi tên thư mục **tinymmce-advanced **thành bất cứ tên gì các bạn muốn ví dụ **tinymmce-advanced-disabled**

Thử truy cập vào Bảng điều khiển, bạn sẽ thấy thông báo plugin **TinyMCE-Advanced** đã được tắt đi

 

[![tắt plugin wordpress 2](http://khoanguyen.me/wp-content/uploads/2015/01/disable-wordpress-plugins-2_dohhca.jpg)](http://khoanguyen.me/wp-content/uploads/2015/01/disable-wordpress-plugins-2_dohhca.jpg)

 


# <span id="2_Tt_thng_qua_c_s_d_liu"> 2. Tắt thông qua cơ sở dữ liệu</span>

Đăng nhập vào phpMyAdmin và chọn database của site WordPress bạn đang sử dụng.

<span style="color: #ff0000;">**Lưu ý:** Cần sao lưu lại cơ sở dữ liệu trước khi thực hiện bất kì thao tác nào bên dưới</span>

Nhấn chọn nút SQL ở thanh công cụ phía trên.

[![disable-wordpress-plugins-4](http://khoanguyen.me/wp-content/uploads/2015/01/disable-wordpress-plugins-4_yzlefg.jpg)](http://khoanguyen.me/wp-content/uploads/2015/01/disable-wordpress-plugins-4_yzlefg.jpg)

 

Xóa hết các lệnh có sẵn và gõ lệnh sau đây vào khung lệnh

SELECT * FROM wp_options WHERE option_name = 'active_plugins';

[![disable-wordpress-plugins-5](http://khoanguyen.me/wp-content/uploads/2015/01/disable-wordpress-plugins-5_ov7h0r.jpg)](http://khoanguyen.me/wp-content/uploads/2015/01/disable-wordpress-plugins-5_ov7h0r.jpg)

Xóa bỏ hết và ghi nội dung sau đây vào khung đỏ

a:0:{}

Nhấn Go.

Thao tác trên là các bạn đã tắt toàn bộ plugin của WordPress. Các bạn có thể bật lại từng plugin sau khi đăng nhập trong Bảng Điều Khiển.


# <span id="Kt_lun">Kết luận</span>

Vọc phá plugin là một điều nên làm nhưng mà các bạn hãy cẩn thận. Luôn nhớ Backup cơ sở dữ liệu và file trước khi thực hiện bất kì thao tác nào trên site WordPress.

Nếu có thắc mắc gì hãy gửi trả lời bên dưới các bạn nhé


