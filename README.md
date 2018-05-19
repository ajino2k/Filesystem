# Các loại Filesystem trong Linux

### Journaling
-	Khi một file được ghi vào ổ cứng, file sẽ được ghi vào Journaling trước.
-	Nếu file lỗi, file system kiểm tra lại journaling xem lỗi ở đâu, chỗ nào lỗi
-	Ngược lại, file sẽ được ghi vào ổ cứng và được xóa ở journaling

<img src="http://www.howtogeek.com/wp-content/uploads/2010/12/640x250xJournal.png.pagespeed.gp+jp+jw+pj+js+rj+rp+rw+ri+cp+md.ic.4h1Q9x_447.png" />

### Đơn vị
Các đơn vị đang phổ biến

- GiB = Gibibyte (1024 MiB)
- TiB = Tebibyte (1024 GiB)
- PiB = Pebibyte (1024 TiB)
- EiB = Exbibyte (1024 PiB)


### Các loại Filesystem

File system	| Năm giới thiệu	| Kích thước file tối đa	| Kích thước ổ đĩa tối đa	| Block journaling	|Ghi chú |
--- | --- | --- | ---| --- | --- |
FAT16	| 1984	|2GB or 4GB	|2GB or 4GB	|Không	|Đã lạc hậu, không nên sử dụng||
FAT32	|1996	|2GB or 4GB	|2TB or 16TB	|Không	|Đã lạc hậu, không nên sử dụng||
NTFS (3.1)	|2001	|16EB	|16EB		|Có	|Nên sử dụng, nếu đang chạy Hệ thống Windows||
EXT2	|1993	|2TB	|32TB	|Không	|Đã lạc hậu không nên sử dụng||
EXT3	|1999	|2TB	|32TB	|Có	|Đã lạc hậu, không nên sử dụng||
EXT4	|2006	|16TB	|1EB	|Có	|Nên sử dụng ,nếu đang chạy Hệ thống Linux||
reiserFS	|2001	|8TB	|16TB	|Có	|Với những File có kích thước dưới 4KB, reiserFS có tốc độ xử lý nhanh hơn (Có thể sử dụng reiserFS cho các hệ thống nơi chú trọng hiệu suất xử lý với các tập tin nhỏ như HTTP Cache)||
XFS	|1994	|8EB	|8EB	|Có	|Nên sử dụng cho các Hệ thống Server lớn, lên đến hàng trăm TB (Không hỗ trợ để lưu trữ thư mục root hay /boot trong hệ thống Linux)||
JFS1	|1990	|8EB	|4PB	|Có	|Đã lạc hậu, không nên sử dụng||
JFS	|1999	|4 PB	|32 PB	|Có	|Không còn được hỗ trợ và duy trì bởi IBM (Thua kém về hiệu năng và độ tin cậy so với EXT4)||
HFS	|1985	|2GB	|2TB	|Không	|Đã lạc hậu, không nên sử dụng||
HFS+	|1998	|8EB	|8EB	|Có	|Sử dụng chính trong MacOS||


### Xem dung lượng của file, thư mục, ổ đĩa
Sử dụng hai câu lệnh `du` và `df`

#### Câu lệnh `du`

Xem dung lượng của các file ở thư mục hiện tại và tổng dung lượng hiện tại

`# du -sh *`

<img src="https://github.com/ajino2k/Filesystem/blob/master/0001.png" />

Xem dung lượng của các sub-folder

`# du -h`

<img src="https://github.com/ajino2k/Filesystem/blob/master/0002.png" />

Ngoài ra, còn nhiều thuộc tính khác xem thêm bằng câu lệnh

`# du --help`

#### Câu lệnh `df`

Xem dung lượng đã sử dung, còn trống,...

`# df -h`

<img src="https://github.com/ajino2k/Filesystem/blob/master/0004.png" />
`-h` xem dung lượng với đơn vị KiB, GiB,...

`-T` Hiển thị Type của filesystem


