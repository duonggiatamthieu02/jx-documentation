# Thiết lập môi trường dev JX

## :large_blue_diamond: 1. Các tool cần chuẩn bị

- **Editor Visual Studio Code (Community)** * -> [download](https://visualstudio.microsoft.com/vs/community/)
- **Editor Notepad++** -> [download](https://notepad-plus-plus.org/downloads/)
- **WinSCP*** : kết nối và cài đặt WinSCP ở đây -> [link](https://github.com/duonggiatamthieu02/jx-documentation/blob/master/cai-dat-jx-vltk1-offline.md#star-324-c%C3%A0i-%C4%91%E1%BA%B7t-winscp)
- **Bộ font chữ ABC*** (font tiếng Việt), tải về thì cài luôn nhé.
  - hoặc dùng bộ font Việt hóa `sonkt_Source Code Pro` của Kiều Tôn Sơn hội quán, xài bộ này cho đẹp :kissing:
- **Git Bash*** : vừa có dòng lệnh, vừa có GUI luôn rất tiện -> [download](https://git-scm.com/downloads)
- **QTTabBar** - đây là tool để mở explorer dạng tab giống Chrome, tool này ai cần thì cài nhé chủ yếu là win7, win10 dùng thôi -> [download](http://qttabbar.wikidot.com/)
- **Unikey*** : gõ tiếng Việt cho file định dạng mã `iso88591`

*Tool nào có đánh dấu sao `*` là bắt buộc cài.*

## :large_blue_diamond: 2. Cài đặt

### :small_red_triangle_down: 2.1 Editor Visual Studio Code

Editor này là để add cả source `jxser` **đã lọc** vào. Có đầy đủ các tính năng, phím tắt... cần thiết cho việc dev jx.

- **Extension**: sau khi cài xong VS Code thì cần cài thêm list extension sau
    <p align="center">
        <img width="500" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-1.png?raw=true">
    </p>
    
    - **Duplicate action**: để tạo/clone nhanh 1 file mới, backup file
    - **Lua**: đây là extension của Tencent hỗ trợ Lua có các tính năng chính sau:
      - Code Editing
      - Defintion Find 
      - Find All References 
      - Document Symbols 
      - Workspace Symbols 
      - Auto Code Completion 
      - Format Code 
      - Hover 
      - Hightlight Global Var 
      - Code Detection
      - Syntax Check 
      - Semantic Check 
      - Quick Analysis 
    - **Material Icon Theme:** cài cho đẹp :smiley:
    - **Symbol Masks**: đây là ext để convert những ký tự bị lỗi trong source `jxser`, cụ thể ở đây là chữ `"ư"` ai đã xem qua code thì sẽ biết đc lỗi này

- Mình chia sẽ luôn các setting cần thiết sau khi cài extension, bạn bấm F1 -> search `Settings JSON` rồi paste config bên dưới vào:
```json
{
    "editor.fontFamily": "sonkt_Source Code Pro",
    "editor.fontLigatures": false,
    "symbolMasks.masks": [
        {
            // SymbolMasks sẽ hoạt động với những file ngôn ngữ được liệt kê dưới đây.
            "language": [
                "lua",
                "plaintext",
                "ini",
                "log",
                "c",
                "csharp",
                "cpp",
                "markdown"
            ],
            "patterns": [
                {
                    // Trong "" đã có chữ "ư" mã Unicode, editor không hiển thị
                    "pattern": "­",
                    // Thay thế ký tự được liệt kê trong pattern bằng kí tự này
                    "replace": "ư"
                }
            ]
        }
    ],
    // Bỏ qua highlight những ký tự unicode (tiếng việt có dấu là những ký tự unicode)
    "editor.unicodeHighlight.ambiguousCharacters": false,
    "editor.unicodeHighlight.invisibleCharacters": false,

    // Vì ae dev jx, nên sử dụng mã iso88591 làm mặc định. Bạn có thể thiết lập mặc định này cho Workspace dùng riêng để dev jx
    "files.encoding": "iso88591",
    "workbench.iconTheme": "material-icon-theme",
    "[lua]": {
        "editor.defaultFormatter": "yinfei.luahelper"
    },
    // Setting cho format code theo chuẩn PSR của PHP
    "Lua.diagnostics.enable": false, // tắt báo error
    "luahelper.format.use_tab": true,
    "luahelper.format.tab_width": 1,
    "luahelper.format.column_limit": 500,
    "luahelper.format.indent_width": 1,
    "luahelper.Warn.AllEnable": false // tắt warning
}
```

- Lời khuyên là các bạn nên login vào VS Code để lưu lại tất những cài đặt phía trên, nếu đi qua PC khác thì chỉ cần login là có đầy đủ không cần cài lại.
- Theo mình thì setting phía trên rất tiện khi làm việc theo team, 
  - dùng chung 1 format
  - trình bày code sạch đẹp, làm cho việc code trở nên hứng thú hơn :grin:
  - ở đây mình cũng chỉnh format theo dạng `1 tab` thay vì `4 space`, vì mình thấy file gốc phía team China làm thế :kissing:
  - để màu mè hơn thì có thể install thêm theme `Dracula`, `Andromeda` ... màu của 2 theme này rất đẹp :grin:

<p align="center">
    <img width="750" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-5.png?raw=true">
</p>

### :small_red_triangle_down: 2.1.2 Editor Notepad++

Editor này dùng để mở & check file cho nhanh. Cũng nhẹ, nên cài.

- Cũng phải cài file font cho nó luôn, `Settings` -> `Style Configuarator`
    <p align="center">
        <img width="800" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-2.png?raw=true">
    </p>

- Tắt tự động encoding, `Settings` -> `Preferences`
    <p align="center">
        <img width="800" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-3.png?raw=true">
    </p>

### :small_red_triangle_down: 2.1.3 Cài đặt Unikey

- Để gõ được tiếng Việt trong file encoding `iso88591` (source code), thì chọn bảng mã `TCVN3 (ABC)`

- Phím tắt để chuyển đổi qua giữa `Unicode` & `TCVN3 (ABC)`: 
  - `Ctrl + Shift + F1` - Unicode
  - `Ctrl + Shift + F2` - TCVN3 (ABC)

:arrow_forward: Áp dụng cho việc đặt tên nhân vật có dấu + chat có dấu trong game jx luôn nhé.

<p align="center">
    <img width="500" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-4.png?raw=true">
</p>

## :large_blue_diamond: 3. Quản lý source code bằng Git - Git Bash

Dùng Git quản lý phiên bản source code, để lưu lại những gì đã thay đổi, muốn quay đầu hay copy lại code cũ gì cũng dễ. 

Tránh việc sửa code trực tiếp từ server bằng WinSCP, vì sửa trực tiếp sẽ làm loạn cả project, không biết/không nhớ là đã sửa những gì.

- Truy cập **Github** & tạo mới một **repository** sau đó copy url của repo:
<p align="center">
    <img width="400" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-11.png?raw=true">
</p>

- Từ source `server/jxser` của hội quán hoặc pgaming cũng đc, các bạn hãy lọc ra các folder như hình, chúng ta chỉ cần nhiêu đây là đủ để dev, ở đây mình dùng source eurofun để làm ví dụ, đây sẽ là bộ source ở `local`
<p align="center">
    <img width="300" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-7.png?raw=true">
</p>

- Tạo một folder rồi đặt tất cả file đã lọc ở trên vào, ở đây mình đặt là `src-eurofun-20230930`, right click chọn `Git Bash Here` 
<p align="center">
    <img width="400" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-10.png?raw=true">
</p>

- Sau đó, chạy các command sau để tiến hành đẩy code lên Github

> git init

Lấy link remote của repo đã tạo ở trên, thay thế vào link bên dưới nhé

> git remote add origin https://github.com/USERNAME_GITHUB_CUA_BAN/jx-eurofun.git

> git add .

> git commit -m "init project"

> git push origin master

- Push tất cả lên git, xong.
<p align="center">
    <img width="600" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-8.png?raw=true">
</p>

## :large_blue_diamond: 4. Chỉnh sửa code và đồng bộ lên server, github

Sau khi chỉnh sửa code/tính năng ở folder `/src-eurofun-20230930` xong, chúng ta sẽ dùng WinSCP để upload code từ `local` lên `server`, kéo file từ trái rồi thả vào bên phải

<p align="center">
    <img width="800" src="./images/dev-jx/cai-dat-moi-truong-dev-jx-9.png?raw=true">
</p>

Sau khi upload code `local` lên `server` xong, thì chúng ta tiến hành upload code `local` lên `repository` github.

End.

*Tổng hợp bởi Đường Gia Tam Thiếu.*