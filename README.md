# 🐧 Bash Scripting and Shell Programming: Linux Command Line

[![Language](https://img.shields.io/badge/Language-Bash%20%7C%20Shell-4EAA25?logo=gnu-bash&logoColor=white)](https://www.gnu.org/software/bash/)
[![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20macOS%20%7C%20WSL-FCC624?logo=linux&logoColor=black)](https://kernel.org/)
[![Linter](https://img.shields.io/badge/Linter-ShellCheck-blue.svg)](https://www.shellcheck.net/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

> **Tổng hợp toàn bộ kiến thức, bài giảng, bài tập thực hành kèm lời giải và bộ sưu tập kịch bản (scripts) Bash thực tế dành cho Quản trị viên hệ thống (SysAdmin) và Kỹ sư DevOps.**

---

## 📑 Mục lục (Table of Contents)

1. [Giới thiệu (Overview)](#-giới-thiệu-overview)
2. [Cấu trúc thư mục (Directory Structure)](#-cấu-trúc-thư-mục-directory-structure)
3. [Nội dung khóa học & Bài tập (Curriculum & Exercises)](#-nội-dung-khóa-học--bài-tập-curriculum--exercises)
4. [Bộ kịch bản thực tế (Real-World SysAdmin Scripts)](#-bộ-kịch-bản-thực-tế-real-world-sysadmin-scripts)
5. [Tài liệu & Bảng tra cứu (Cheat Sheets & References)](#-tài-liệu--bảng-tra-cứu-cheat-sheets--references)
6. [Hướng dẫn cài đặt & Thực thi (Getting Started & Execution)](#-hướng-dẫn-cài-đặt--thực-thi-getting-started--execution)
7. [Quy chuẩn viết Bash Script chuyên nghiệp (Best Practices)](#-quy-chuẩn-viết-bash-script-chuyên-nghiệp-best-practices)
8. [Tác giả & Đóng góp (Contributing & Author)](#-tác-giả--đóng-góp-contributing--author)

---

## 📖 Giới thiệu (Overview)

Kho lưu trữ này cung cấp lộ trình học tập toàn diện từ cơ bản đến nâng cao về **Lập trình Shell và Bash Scripting trên nền tảng Linux**, kết hợp giữa lý thuyết, thực hành theo module và các kịch bản tự động hóa thực tế trong môi trường sản xuất (Production).

### 🎯 Mục tiêu đạt được:
- Nắm vững cú pháp Bash, quản lý biến, điều kiện `if/then/else`, vòng lặp `for`/`while`, hàm và mã thoát (Exit Statuses).
- Xử lý chuỗi, ký tự đại diện (Wildcards), cấu trúc rẽ nhánh `case`, và ghi log hệ thống (`logger` / syslog).
- Kỹ năng gỡ lỗi (Debugging) chuyên sâu bằng các cờ tùy chọn của Bash (`-x`, `-e`, `-u`, `-v`).
- Tự động hóa các tác vụ quản trị máy chủ Linux: sao lưu dữ liệu, giám sát ổ đĩa, kiểm tra mạng, quản lý cấu hình card mạng (NIC bonding), và bảo mật.

---

## 📁 Cấu trúc thư mục (Directory Structure)

```plaintext
.
├── PracticeExercises-ShellScriptingSuccinctly.pdf   # Tài liệu tổng hợp bài tập thực hành Shell Scripting
├── README.md                                       # Tài liệu hướng dẫn chính của repository
├── real-world-scripts/                             # Bộ 14 script tự động hóa quản trị hệ thống thực tế
│   ├── backup-rhevm                                # Tự động sao lưu node RHEV-M
│   ├── convert-nic-to-bonded                       # Ghép cặp và cấu hình Network Bonding (NIC Teaming)
│   ├── email-when-up                               # Gửi email cảnh báo khi server/thiết bị online
│   ├── generate-random-password                    # Tạo mật khẩu ngẫu nhiên an toàn bằng OpenSSL
│   ├── ping-host                                   # Kiểm tra trạng thái ping hàng loạt máy chủ
│   ├── prettify-multipath                          # Định dạng và làm đẹp báo cáo SAN multipath
│   ├── show-cmdb-info                              # Thu thập thông tin phần cứng/OS phục vụ CMDB
│   ├── show-disk-space-used-by-vg                  # Kiểm tra dung lượng sử dụng theo LVM Volume Group
│   ├── show-io-scheduler                           # Liệt kê I/O Scheduler của các ổ đĩa khối
│   ├── show-network-port-info                      # Hiển thị switch, port, VLAN kết nối thiết bị Cisco
│   ├── show-total-disk-space-used                  # Tóm tắt tổng dung lượng đĩa cứng cục bộ đang dùng
│   ├── show-wwpns                                  # Liệt kê các địa chỉ WWPN (Fibre Channel)
│   ├── tail-db2diag                                # Theo dõi log chẩn đoán IBM DB2 theo thời gian thực
│   └── touch-test                                  # Kiểm tra tính toàn vẹn và quyền ghi trên các mount point
└── shell-scripting-course/                         # Khóa học bài bản chia theo từng chuyên đề
    ├── ShellScriptingCheatSheetandReference.pdf    # Bảng tra cứu nhanh lệnh và cú pháp Bash
    ├── case-statements/                            # Chuyên đề: Cấu trúc rẽ nhánh case...esac
    ├── debugging/                                  # Chuyên đề: Kỹ thuật gỡ lỗi trong Bash
    ├── exit-statuses-and-return-codes/             # Chuyên đề: Mã thoát ($?) và toán tử điều kiện (&&, ||)
    ├── functions/                                  # Chuyên đề: Định nghĩa và sử dụng hàm (Functions)
    ├── logging/                                    # Chuyên đề: Ghi log tập trung với Syslog (logger)
    ├── scripts-used-to-create-this-course/         # Script phụ trợ (chuyển đổi slides, audio)
    ├── shell-script-checklist-and-template/        # Template script mẫu và danh mục kiểm tra (Checklist)
    ├── shell-scripting-in-a-nutshell/              # Chuyên đề: Nhập môn và kiến thức căn bản
    ├── while-loops/                                # Chuyên đề: Vòng lặp while và đọc dữ liệu theo dòng
    └── wildcards/                                  # Chuyên đề: Ký tự đại diện và xử lý tệp hàng loạt
```

---

## 📚 Nội dung khóa học & Bài tập (Curriculum & Exercises)

Mỗi thư mục trong `shell-scripting-course/` đều bao gồm 2 phần:
- `lessons/`: Các ví dụ minh họa từng bước theo bài giảng.
- `practice-exercises/`: Đề bài thực hành dạng PDF kèm theo các script giải mẫu (`solution-*.sh`).

| STT | Chuyên mục | Nội dung trọng tâm | Bài tập & Lời giải |
|:---:|:---|:---|:---:|
| 1 | **[shell-scripting-in-a-nutshell](shell-scripting-course/shell-scripting-in-a-nutshell)** | Shebang (`#!/bin/bash`), biến, lệnh `echo`, nhận tham số dòng lệnh (`$0`, `$1`), toán tử kiểm tra file (`-f`, `-d`, `-r`, `-w`, `-x`) | `practice-exercises/` (Bài tập 1 - 8) |
| 2 | **[exit-statuses-and-return-codes](shell-scripting-course/exit-statuses-and-return-codes)** | Mã trạng thái thoát (`$?`), lệnh `exit [n]`, toán tử logic thực thi có điều kiện (`&&`, `\|\|`) | `practice-exercises/` (Bài tập 1 - 3) |
| 3 | **[functions](shell-scripting-course/functions)** | Khai báo hàm, truyền tham số vào hàm (`$1`, `$@`), phạm vi biến cục bộ (`local`), giá trị trả về của hàm | `practice-exercises/` (Bài tập 1 - 2) |
| 4 | **[wildcards](shell-scripting-course/wildcards)** | Ký tự đại diện (Globbing: `*`, `?`, `[]`), duyệt file và viết script đổi tên tệp hàng loạt (Batch Rename) | `practice-exercises/` (Bài tập 1 - 2) |
| 5 | **[case-statements](shell-scripting-course/case-statements)** | Cú pháp `case ... in`, xử lý tùy chọn người dùng, viết script khởi động dịch vụ (Daemon controller: `start`, `stop`, `status`) | `practice-exercises/` (Bài tập 1) |
| 6 | **[logging](shell-scripting-course/logging)** | Tiện ích `logger`, mức độ nghiêm trọng (Syslog Facilities & Priorities), gắn tag thông báo, tạo hàm ghi log chuẩn | `practice-exercises/` (Bài tập 1 - 2) |
| 7 | **[while-loops](shell-scripting-course/while-loops)** | Vòng lặp `while`, đọc tệp tin theo từng dòng bằng `while IFS= read -r LINE`, xử lý luồng với `break` và `continue` | `practice-exercises/` (Bài tập 1 - 3) |
| 8 | **[debugging](shell-scripting-course/debugging)** | Cờ gỡ lỗi `bash -x`, `set -x` (xtrace), `set -e` (errexit), `set -v` (verbose), tùy biến tiền tố gỡ lỗi bằng `PS4` | `practice-exercises/` (Bài tập 1 - 2) |
| 9 | **[shell-script-checklist-and-template](shell-scripting-course/shell-script-checklist-and-template)** | Khung sườn kịch bản mẫu ([`template.sh`](shell-scripting-course/shell-script-checklist-and-template/template.sh)) và danh sách các tiêu chuẩn kiểm tra trước khi đưa vào vận hành | `ShellScriptCheckList.pdf` |

---

## 🛠️ Bộ kịch bản thực tế (Real-World SysAdmin Scripts)

Nằm trong thư mục [`real-world-scripts/`](real-world-scripts/), đây là tập hợp các script tự động hóa tiêu chuẩn, có thể sử dụng ngay trong công việc quản trị hệ thống Linux hàng ngày:

| Tên Script | Mục đích & Chức năng | Cú pháp sử dụng (Usage) |
|:---|:---|:---|
| [`backup-rhevm`](real-world-scripts/backup-rhevm) | Sao lưu cấu hình node ảo hóa Red Hat Enterprise Virtualization Manager (RHEV-M). | `./backup-rhevm` |
| [`convert-nic-to-bonded`](real-world-scripts/convert-nic-to-bonded) | Tự động cấu hình gom nhóm card mạng (NIC Bonding/Teaming) tạo kênh dự phòng chịu lỗi. | `./convert-nic-to-bonded -s eth0 -p eth1 -b bond0` |
| [`email-when-up`](real-world-scripts/email-when-up) | Theo dõi một máy chủ hoặc thiết bị mạng qua ping và tự động gửi email thông báo ngay khi máy chủ hoạt động trở lại. | `./email-when-up -e admin@example.com -h 192.168.1.100` |
| [`generate-random-password`](real-world-scripts/generate-random-password) | Sinh chuỗi mật khẩu ngẫu nhiên có độ bảo mật cao sử dụng OpenSSL. | `./generate-random-password [số_lượng] [độ_dài]` |
| [`ping-host`](real-world-scripts/ping-host) | Kiểm tra kết nối ping tới danh sách nhiều host cùng lúc, trả về mã thoát `0` nếu tất cả phản hồi hoặc `1` nếu có máy lỗi. | `./ping-host server1 server2 192.168.1.1` |
| [`prettify-multipath`](real-world-scripts/prettify-multipath) | Định dạng và làm sạch kết quả hiển thị từ lệnh `multipath -ll` để dễ dàng kiểm tra SAN storage. | `./prettify-multipath` |
| [`show-cmdb-info`](real-world-scripts/show-cmdb-info) | Thu thập tự động thông số cấu hình hệ điều hành, CPU, RAM, IP để phục vụ cập nhật cơ sở dữ liệu quản lý cấu hình (CMDB). | `./show-cmdb-info [-c]` |
| [`show-disk-space-used-by-vg`](real-world-scripts/show-disk-space-used-by-vg) | Báo cáo chi tiết dung lượng lưu trữ đang được phân bổ và sử dụng theo từng LVM Volume Group. | `./show-disk-space-used-by-vg [vg_name...]` |
| [`show-io-scheduler`](real-world-scripts/show-io-scheduler) | Tra cứu nhanh I/O Scheduler hiện tại của các thiết bị lưu trữ dạng khối trên hệ thống (`/sys/block`). | `./show-io-scheduler` |
| [`show-network-port-info`](real-world-scripts/show-network-port-info) | Hiển thị thông tin Switch, Port và VLAN mà card mạng vật lý đang kết nối (qua giao thức Cisco CDP/LLDP). | `sudo ./show-network-port-info` |
| [`show-total-disk-space-used`](real-world-scripts/show-total-disk-space-used) | Tính toán và tổng kết tổng dung lượng ổ đĩa cục bộ đang được sử dụng trên máy chủ. | `./show-total-disk-space-used` |
| [`show-wwpns`](real-world-scripts/show-wwpns) | Hiển thị danh sách các cổng World Wide Port Name (WWPN) của card quang (Fibre Channel HBA). | `./show-wwpns` |
| [`tail-db2diag`](real-world-scripts/tail-db2diag) | Tự động tìm vị trí và theo dõi trực tiếp tệp log chẩn đoán (`db2diag.log`) của cơ sở dữ liệu IBM DB2. | `./tail-db2diag` |
| [`touch-test`](real-world-scripts/touch-test) | Thử tạo và xóa file trên từng phân vùng mount cục bộ nhằm phát hiện các ổ đĩa bị chuyển sang chế độ chỉ đọc (Read-Only) hoặc bị treo I/O. | `./touch-test` |

---

## 📑 Tài liệu & Bảng tra cứu (Cheat Sheets & References)

Kho lưu trữ đã đính kèm sẵn các tài liệu hướng dẫn và bảng tra cứu định dạng PDF chất lượng cao:

1. **[ShellScriptingCheatSheetandReference.pdf](shell-scripting-course/ShellScriptingCheatSheetandReference.pdf)**:
   - Bảng tra cứu nhanh cú pháp, các biến đặc biệt (`$0`, `$#`, `$@`, `$?`, `$$`), toán tử so sánh chuỗi/số/tệp, và cấu trúc lệnh cơ bản.
2. **[PracticeExercises-ShellScriptingSuccinctly.pdf](PracticeExercises-ShellScriptingSuccinctly.pdf)**:
   - Bộ bài tập thực hành tổng hợp từ nhập môn đến nâng cao.
3. **[ShellScriptCheckList.pdf](shell-scripting-course/shell-script-checklist-and-template/ShellScriptCheckList.pdf)**:
   - Danh sách kiểm tra chất lượng mã nguồn script trước khi triển khai môi trường thực tế (Error handling, Security, Performance, Coding Style).

---

## 🚀 Hướng dẫn cài đặt & Thực thi (Getting Started & Execution)

### 1. Yêu cầu môi trường
- Hệ điều hành: Linux (Ubuntu, Debian, CentOS, RHEL, Fedora, Arch Linux), macOS, hoặc Windows (thông qua **WSL** hoặc **Git Bash**).
- Trình thông dịch: `GNU bash` (phiên bản 4.x trở lên được khuyến nghị).

Kiểm tra phiên bản Bash hiện tại:
```bash
bash --version
```

### 2. Tải mã nguồn về máy
```bash
git clone https://github.com/nguyenduykhanhit04/Bash-Scripting-and-Shell-Programming-Linux-Command-Line-.git
cd Bash-Scripting-and-Shell-Programming-Linux-Command-Line-
```

### 3. Cấp quyền thực thi và chạy script
Trước khi chạy bất kỳ script nào, hãy đảm bảo script đã được cấp quyền thực thi (`execute`):

```bash
# Cấp quyền thực thi cho một file
chmod +x real-world-scripts/generate-random-password

# Hoặc cấp quyền cho tất cả script trong thư mục
chmod +x real-world-scripts/*

# Thực thi script
./real-world-scripts/generate-random-password 3 16
```

### 4. Chạy script ở chế độ gỡ lỗi (Debugging)
Để kiểm tra từng dòng lệnh thực thi và giá trị biến:
```bash
bash -x shell-scripting-course/functions/lessons/functions-01.sh
```

---

## 💡 Quy chuẩn viết Bash Script chuyên nghiệp (Best Practices)

Để viết mã nguồn Shell Script an toàn, dễ bảo trì và hạn chế tối đa lỗi tiềm ẩn, bạn nên tuân thủ các quy tắc sau:

1. **Luôn sử dụng Shebang rõ ràng**:
   ```bash
   #!/usr/bin/env bash
   # hoặc
   #!/bin/bash
   ```

2. **Sử dụng cờ an toàn (`Strict Mode`) ở đầu script**:
   ```bash
   set -euo pipefail
   ```
   - `-e`: Dừng script ngay lập tức nếu có lệnh trả về lỗi (exit status khác 0).
   - `-u`: Báo lỗi và dừng script nếu sử dụng biến chưa được định nghĩa.
   - `-o pipefail`: Trả về mã lỗi nếu bất kỳ lệnh nào trong đường ống (`pipe |`) thất bại.

3. **Luôn trích dẫn biến (Quote Variables)**:
   ```bash
   # Đúng (Ngăn ngừa word splitting và pathname expansion)
   rm -f "$TARGET_FILE"
   if [ -f "$FILE_PATH" ]; then ... fi

   # Sai (Có thể gây lỗi nghiêm trọng nếu biến chứa khoảng trắng)
   rm -f $TARGET_FILE
   ```

4. **Sử dụng biến cục bộ trong hàm (`local`)**:
   ```bash
   my_function() {
       local item_name="$1"
       local -i count=0
       echo "Processing: $item_name"
   }
   ```

5. **Kiểm tra cú pháp bằng [ShellCheck](https://www.shellcheck.net/)**:
   ```bash
   # Cài đặt trên Ubuntu/Debian:
   sudo apt-get install shellcheck

   # Kiểm tra file script:
   shellcheck my-script.sh
   ```

6. **Tham khảo mẫu kịch bản chuẩn**:
   Xem file mẫu [`shell-script-checklist-and-template/template.sh`](shell-scripting-course/shell-script-checklist-and-template/template.sh) để cấu trúc hóa script một cách chuẩn chỉ.

---

## 🤝 Đóng góp & Tác giả (Contributing & Author)

- **Tác giả / Học viên**: [nguyenduykhanhit04](https://github.com/nguyenduykhanhit04)
- **Đóng góp (Contribution)**: Mọi đóng góp, chỉnh sửa lỗi cú pháp, cải tiến script hoặc thêm các bài tập mới đều được chào đón! Bạn có thể tạo **Pull Request** hoặc mở một **Issue** mới.

⭐ **Nếu thấy kho lưu trữ hữu ích, hãy để lại một Star để ủng hộ dự án!**
