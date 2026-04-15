# Eduquiz
1. Cấu trúc hệ thống trên linux
Internet → Nginx :80
              ├── /        → dist/ (React đã build)
              └── /api/    → Express :3001 (PM2)
                                  │
                              PostgreSQL :5432



Deploy chương trình với các lệnh:

# 1. Copy project lên server Linux
  scp -r eduquiz-fixed/ user@your-server:/opt/eduquiz

# 2. SSH vào server và chạy
  cd /opt/eduquiz
  sudo bash deploy/install.sh

Sau khi cài, quản lý băng:
  bash manage.sh start      # Khởi động
  bash manage.sh restart    # Khởi động lại
  bash manage.sh logs       # Xem log
  bash manage.sh update     # Cập nhật code mới
  bash manage.sh db-backup  # Backup database

Muốn thêm https sau khi có domain thật chỉ cần:
  sudo certbot --nginx -d your-domain.com
