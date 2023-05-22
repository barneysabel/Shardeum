# Shardeum
Dành cho bạn nào đang chạy node Shardeum, trường hợp bí bách sắp hết hạn VPS. Mà không lấy được Key của Validator, hiện tại dự án Shardeum họ chưa share, nhưng mà nhìn AE đang vướng chỗ này.

Chạy lệnh này để lấy key nhé:

docker exec shardeum-dashboard cat cli/build/secrets.json
Lưu lại đoạn mã {"publicKey":"","secretKey":""} này để sau này Restore.

Restore
Lưu ý dùng Mobaxterm hoặc Termius để dễ copy paste trong nano.

Sau khi chuyển VPS mới và cài shardeum.

Bước 1 :

cd .shardeum
Bước 2 :

Nếu node đã start trước đó thì vào ./shell.sh chạy lệnh operator-cli stop thì mới bắt đầu làm tiếp bước dưới.

docker exec shardeum-dashboard cat cli/build/secrets.json
-> không lưu lại đoạn mã này, mục đích để tạo ra file secrets.json để lấy đoạn mã của node cũ chép vào

Bước 3 :

./shell.sh
Bước 4 :

sudo apt install nano
Bước 5 :

nano cli/build/secrets.json
Bước 6 :

Ctrl + K để xóa dòng secrets hiện tại, copy {"publicKey":"","secretKey":""} ở node VPS cũ dán vào.

Ctrl + X

Y
Bước 7 :

operator-cli start
