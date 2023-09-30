link maclifevn
curl https://raw.githubusercontent.com/maclifevn/bypasmdm/main/mdm.sh -o test.sh && chmod +x ./test.sh && ./test.sh

link fork me
curl https://raw.githubusercontent.com/shinichiok2614/bypasmdm/main/mdm.sh -o test.sh && chmod +x ./test.sh && ./test.sh


GateKeeper
xattr -cr [khoảng trắng]

check file hosts
sudo nano /private/etc/host

sudo profiles show -type enrollment

Các máy MDM nếu đã được tắt từ bước install macOS thì sẽ đều hiện no nhá. Chỉ có 2 cách 1 là check seri, 2 là cài mới và kết nối với mạng nếu có MDM sẽ hiện lên thôi!

////////
Cách 1: Ẩn bằng cách sửa file hệ thống
- Sau khi máy cài đặt xong , tới bước chọn ngôn ngữ để kích hoạt lên. chúng ta sẽ không kích hoạt mà tắt máy luôn. Sau đó khởi động lại và giữ tổ hợp phím CMD + R để vào recovery mode và chọn Ultilities, chọn Terminal rồi gõ lần lượt các câu lệnh sau:

csrutil disable
ls /Volumes
//xem tên ổ cứng 
cd /
cd /Volumes/Macintosh\ HD
//Macintosh\ HD là tên ổ cứng của chúng ta, tuỳ cách đặt tên ổ cứng của bạn mà câu lệnh có thể thay đổi
rm System/Library/LaunchAgents/com.apple.Managed*
rm System/Library/LaunchDaemons/com.apple.Managed*
Reboot
//Khởi động lại máy
////////