# :zap: Hướng dẫn cài đặt JX game Võ Lâm Truyền Kỳ 1 - Phiên bản Offline

<p align="center">
	<a href="https://www.facebook.com/duonggiatamthieu01/" title="JX Dev Community - Đường Gia Tam Thiếu">
		<img width="200" height="200" src="./images/vltk-offline-ico.png?raw=true">
	</a>
</p>

<p align="center">
	<a href="https://www.facebook.com/duonggiatamthieu01/" title="JX Dev Community - Đường Gia Tam Thiếu">
		<img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" />
	</a>
	<a href="https://github.com/duonggiatamthieu02" title="JX Dev Community - Đường Gia Tam Thiếu">
 		<img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="platform, system_requirements">
	</a>
</p>

## :large_blue_diamond: 1. Thông tin cơ bản

JXLinux 8.x Offline (Võ lâm truyền kỳ 1 - bản PC)

Nguồn: [Hội quán Võ Lâm](https://fb.com/groups/volamquan)

## :large_blue_diamond: 2. Yêu cầu hệ thống

Phần cứng:
- Tối thiểu: 8GB RAM, ổ cứng trống ít nhất 20GB. Máy có hỗ trợ ảo hoá.
- Chuẩn: 16GB RAM, ổ cứng trống ít nhất 40GB. Máy có hỗ trợ ảo hoá.

Phần mềm và hệ thống
- Windows 8, 7, Vista, XP, 2000, 9x, 10, 11
- VMWare 15, 16 hoặc mới nhất cũng OK.
- Microsoft Visual C++ 2005 Redistributable Package (x86).
	- Gói thư viện C++ 2005 này có thể đã được cài sẵn nếu máy bạn từng cài nhiều game khác trước đó. Có thể kiểm tra xem đã cài chưa ở Control Panel > Programs and Features.
	- Nếu chưa có trên máy. Download tại https://www.microsoft.com/en-us/download/confirmation.aspx?id=26347

## :large_blue_diamond: 3. Download & cài đặt các tài nguyên cần thiết

### :small_red_triangle_down: 3.1 Download

* Pass giải nén nếu có: `https://fb.com/groups/volamquan`

* VMWare bản mới nhất tại [Trang chủ VMWare](https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html)
    - Sau khi cài thì nhập Free VMware Workstation Pro 17 full license keys tại [đây](https://gist.github.com/PurpleVibe32/30a802c3c8ec902e1487024cdea26251)

* Download WinSCP 5.9.5 -> [link](https://sourceforge.net/projects/winscp/files/WinSCP/5.9.5/)
* Download resource game:
    - Source game gốc: [link](https://volam.zing.vn/cam-nang-chi-tiet/tan-thu/tai-game.html). Download & cài đặt sau đó chạy autoupdate để lấy source mới nhất. `(*1)`
    - Source của Hội quán gồm 2 phần:
        - Download máy chủ ảo VMWare `WinXP` và `CentOS` -> [link](https://www.mediafire.com/file/3i9biis3j27urzq/server.7z/file) `(*2)`
            * Tạo folder `D:\server\` (bỏ 2 folder `WinXP` và `CentOS` vào đây)
        - Download source code `client & server` từ github của Hội quán (jxser) -> [link](https://github.com/jxoffline/jx1linux/archive/refs/heads/main.zip) `(*3)`
            - Tạo folder `D:\client\` -> Giải nén & bỏ tất cả vào folder này

### :small_red_triangle_down: 3.2 Cài đặt

#### :star: 3.2.1 Start server với VMWare

- Mở thư mục `D:\server` và click vào 2 file bên bên dưới để chạy lần lượt các máy ảo đã download ở `(*2)`. Nếu có hiện thông báo, thì bấm chọn `I move it`

    - `D:\server\CentOS\CentOS16-EuroFun.vmx`
    - `D:\server\Win\JXWindows-EuroFun.vmx`

hoặc mở `VMWare` lên và chọn như ảnh bên dưới để chạy máy ảo

<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-1.png?raw=true">
</p>

- Cài đặt IP để 2 máy ảo "tâm linh tương thông", làm theo thứ tự theo các bước bên dưới

    - Cài đặt DHCP `192.168.1.0` cho card mạng VMnet8

    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-2.png?raw=true">
    </p>
    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-3.png?raw=true">
    </p>

    - Add card mạng VMnet8 vào lần lượt máy ảo CentOS và Win, chú ý là nếu PC của bạn 16Gb ram trở lên thì cứ mạnh dạng set `Memory = 8Gb` cho máy CentOS như mình

    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-4.png?raw=true">
    </p>


  - Sau đó, Bấm `nút Start` hoặc `Power on...` để chạy 2 máy ảo, hiện lên như hình bên dưới là coi như thành công 1 nửa
    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-5.png?raw=true">
    </p>
    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-6.png?raw=true">
    </p>
  
  - Test xem 2 máy đã thông chưa, bằng cách ping IP của nhau, các IP này đã được setup mặc định. Nếu bước này test mà 2 PC ko ping được cho nhau thì sẽ không chạy được game.

    - Login vào CentOS bằng username: `root` | pass: `123456`
    - Chạy lệnh `ping 192.168.1.200` và có response các gói tin như hình dưới là OK
    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-7.png?raw=true">
    </p>

    - Tương tự như bên windows, bấm `Windows + R` -> gõ `cmd` -> `Enter` để mở Command line 
    - Chạy lệnh `ping 192.168.1.100`, như thế là Xong.
    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-8.png?raw=true">
    </p>

#### :star: 3.2.2 Chạy Server game

- Vào máy ảo Windows, sau đó bấm chạy theo thứ tự như bên dưới:

<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-12.png?raw=true">
</p>

- sau khi chạy Bước 3, thì bấm chọn nút `(C)` như hình
<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-13.png?raw=true">
</p>

- Chờ load một lúc, sẽ hiện ra giao diện dòng lệnh của máy linux
<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-14.png?raw=true">
</p>

- Chuột phải vào tab `EurofunSys`, chọn (N) để tạo thêm 3 tab nữa
<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-15.png?raw=true">
</p>

- sau đó, mỗi tab sẽ click vào các nút `1 2 3 S1` tương ứng như hình. Xong. 
<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-16.png?raw=true">
</p>

#### :star: 3.2.3 Cài client game.exe

- Bước này quan trọng, copy 2 folder `data` & `music` từ game gốc đã cài ở mục `(*1)` 

- Sau đó, paste đè vào folder `D:\client\jx1linux-main\client` đã giải nén ở mục `(*3)`, ta được folder game hoàn chỉnh sau

<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-11.png?raw=true">
</p>

- Chạy file `Game.exe` để start game
<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-18.png?raw=true">
</p>

- Lưu ý, nếu game bị đen màn hình thì setup như sau, chuột phải vào file `Game.exe` -> chọn `Properties` -> `Compatibility` -> `16-bit` để chuyển về chế độ 2D
<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-17.png?raw=true">
</p>

- Acc login game mặc định - username: `eurofun` | pass: `123` 
<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-19.png?raw=true">
</p>

- Tạo acc mới ở máy ảo Win, sau đó relogin lại 4 lần sẽ nhận được lệnh bài GM trong hành trang
<p align="center">
    <img width="750" src="./images/install/cai-dat-vltk1-20.png?raw=true">
</p>

Như vậy, xong bước này là đã có thể chơi game được rồi. Nếu muốn phát triển tính năng, chỉnh sửa lệnh bài này nọ... thì cần xem thêm rất nhiều thứ khác nữa.

#### :star: 3.2.4 Cài đặt WinSCP

App này là để tương tác với Server CentOS như upload, download, thêm xóa sửa file, script... Lưu ý là nên tải version bé hơn 6.0 để xài đc nha.

- Kết nối CentOS
  ```
  Hostname: 192.168.1.100
  Username: root
  Password: 123456
  ```
  
    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-9.png?raw=true">
    </p>

- Kết nối OK, nhập đường dẫn chứa source code `/home/jxser/`. Xong.

    <p align="center">
        <img width="750" src="./images/install/cai-dat-vltk1-10.png?raw=true">
    </p>

*Tổng hợp bởi Đường Gia Tam Thiếu.*