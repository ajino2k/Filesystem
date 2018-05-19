# Filesystem
Các loại Filesystem trong Linux
Journaling
Khi một file được ghi vào ổ cứng, file sẽ được ghi vào Journaling trước.
Nếu file lỗi, file system kiểm tra lại journaling xem lỗi ở đâu, chỗ nào lỗi
Ngược lại, file sẽ được ghi vào ổ cứng và được xóa ở journaling


Đơn vị
Các đơn vị đang phổ biến

GiB = Gibibyte (1024 MiB)
TiB = Tebibyte (1024 GiB)
PiB = Pebibyte (1024 TiB)
EiB = Exbibyte (1024 PiB)
Các loại Filesystem
Định dạng	Kích thước tối đa của file	Kích thước tối đa của Partition	Journaling	Ghi chú
ext2	2TiB	32TiB	Không	
ext3	2TiB	32TiB	Có	
ext4	16TiB	1EiB	Có	
reiserFS	8TiB	16TiB	Có	Hoạt động hiệu quả với các file kích thước nhỏ như Logs, ...
JFS	4PiB	32PiB	Có (metadata)	
XFS	8EiB	8EiB	Có (metadata)	Hoạt động hiệu quả với các file kích thước lớn. Phù hợp với các mô hình File Server
Note: Metadata: là những thuộc tính của file như inodes, ngày tạo,...
Xem dung lượng của file, thư mục, ổ đĩa
Sử dụng hai câu lệnh du và df

Câu lệnh du
Xem dung lượng của các file ở thư mục hiện tại và tổng dung lượng hiện tại

# du -sh *



Xem dung lượng của các sub-folder

# du -h



Ngoài ra, còn nhiều thuộc tính khác xem thêm bằng câu lệnh

# du --help

Câu lệnh df
Xem dung lượng đã sử dung, còn trống,...

# df -h

-h xem dung lượng với đơn vị KiB, GiB,...

-T Hiển thị Type của filesystem


