# SUB_QUERY
SUB_QUERY

1. Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika
SELECT k.nik, k.id_dept, k.nama
FROM k
WHERE id_dept = (
SELECT id_dept
FROM k
WHERE nama ='Dika'
);
Output :
![gambar](https://github.com/alfaza-putra/SUB_QUERY/blob/main/ss_hasil/ss1.png)

2. Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua karyawan. Urutkan menurun berdasarkan besaran gaji
SELECT AVG (gaji_pokok) AS RerataGaji
FROM k;
SELECT nik, nama, gaji_pokok AS "Rerata Gaji"
FROM k
WHERE gaji_pokok > (
SELECT AVG(gaji_pokok)
FROM k
ORDER BY gaji_pokok
);
Output :
![gambar](https://github.com/alfaza-putra/SUB_QUERY/blob/main/ss_hasil/ss2.png)

3. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K'
SELECT nik, nama
FROM k
WHERE nama IN (
SELECT nama
FROM k
WHERE nama LIKE'__k%'
);
Output :
![gambar](https://github.com/alfaza-putra/SUB_QUERY/blob/main/ss_hasil/ss3.png)

4. Tampilkan data karyawan yang bekerja pada departemen yang ada di kantor pusat
SELECT nik, nama
FROM k
WHERE id_dept = (
SELECT id_dept
FROM dept
WHERE id_p =
(SELECT id_p FROM p WHERE nama='Kantor Pusat')
);
Output :
![gambar](https://github.com/alfaza-putra/SUB_QUERY/blob/main/ss_hasil/ss4.png)

5. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di department yang sama dengan karyawan dengan nama yang mengandung huruf 'K' dan yang gajinya lebih besar dari rata-rata gaji semua karyawan
SELECT nik, nama, gaji_pokok
FROM k
WHERE gaji_pokok > (
SELECT AVG (gaji_pokok)
FROM k)
AND nama IN (
SELECT nama
FROM k
WHERE nama LIKE'__k%'
);
Output :
![gambar](https://github.com/alfaza-putra/SUB_QUERY/blob/main/ss_hasil/ss5.png)
