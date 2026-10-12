# Bài 4 — GitHub Secret và đăng nhập GHCR

**Sinh viên:** Nguyễn Đăng Dương  
**Lớp:** CNTT2  
**Môn học:** IT209 — Session 11

Workflow chạy unit test và dùng `docker/login-action@v3` để đăng nhập `ghcr.io`. Vì token là bí mật riêng của chủ repository, workflow chỉ thực hiện bước đăng nhập sau khi secret `REGISTRY_TOKEN` được cấu hình; khi chưa có secret, nó sẽ ghi hướng dẫn và bỏ qua login mà không làm lộ token.

## Cấu hình Secret

1. Tạo Personal Access Token (classic) trên GitHub với quyền `write:packages`.
2. Mở repository **Settings → Secrets and variables → Actions → New repository secret**.
3. Đặt tên `REGISTRY_TOKEN`, dán token vào ô value rồi lưu.
4. Push commit mới hoặc chạy lại workflow. Log bước đăng nhập sẽ báo thành công nếu token hợp lệ.

Không lưu token trong mã nguồn, README hay Git history.

