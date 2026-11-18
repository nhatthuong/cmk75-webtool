# CMK75 Web Tool

Trang web đồng bộ **ngày giờ GMT+7** và **đổi ngôn ngữ màn hình (Trung ⇄ Anh)** cho bàn phím FL-Esports CMK75 qua WebHID. Không cần cài phần mềm.

👉 **Dùng ngay:** https://nhatthuong.github.io/cmk75-webtool/

## Cách dùng
1. Cắm CMK75 bằng **cáp USB**.
2. Mở link trên bằng **Chrome** hoặc **Edge**.
3. Bấm **Kết nối CMK75**, chọn bàn phím trong hộp thoại.
4. Giờ GMT+7 được cập nhật tự động. Bấm **Đổi ngôn ngữ** để chuyển Trung ⇄ Anh.

## Kỹ thuật
- HID Feature Report 64 byte trên interface vendor (UsagePage `0xFFFF`, Usage `0x02`), USB ID `3151:4015` / `38A9:0000`.
- Checksum byte 7 = `0xFF − sum(byte 0..6)`.
- Đặt giờ: `0x28`, byte 8–14 = năm (2 byte, big-endian), tháng, ngày, giờ, phút, giây.
- Đổi ngôn ngữ: `0x27 0x01` (chuyển qua lại).

Lệnh được tham khảo từ web driver GearHub/qmk.top của hãng và driver mã nguồn mở [debloatedfl-driver](https://github.com/Some1sm/debloatedfl-driver). Dự án không liên quan chính thức tới FL-Esports. Sử dụng với rủi ro của bạn.
