# basisdata
Nama : Saifulloh Rahman
Nim : 2108561028
Kelas : C
skema:
1. siswa(siswa-nim, siswa-nama, siswa-tanggal-lahir, siswa-alamat)
2. pelajaran(pelajaran-kode, pelajaran-nama, guru-nig)
3. guru(guru-nig, guru-nama)
4. kelas(kelas-nomor, guru-nig)
5. jadwal(jadwal-kode, jadwal-hari, kelas-nomor, guru-nig)
6. daftar-hadir(jadwal-kode, siswa-nim)

Soal
1. Cari nama seluruh siswa pada kelas "1C"
2. Cari seluruh guru yang tidak menjadi wali kelas.
3. Tampilkan siswa yang lahir setelah tanggal 1 Januari 2002.

Jawaban
1.  π siswa-nama (σ daftar-hadir.siswa-nim=siswa.siswa-nim (σ jadwal.jadwal-kode=daftar-hardir.jadwal-kode ^ kelas-nomor="1C" (jadwal X daftar-hadir) X siswa))
2.  σ guru - π guru-nig,guru-nama (σ guru.guru-nig=kelas.guru-nig(guru x kelas))
3.  σ siswa-tanggal-lahir > 01-01-2002 (siswa)
select σ
project π 
