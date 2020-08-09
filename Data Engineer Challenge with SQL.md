Tampilkan transaksi-transaksi yang memiliki jumlah item produk lebih dari 1 jenis produk. Dengan lain kalimat, tampilkan transaksi-transaksi yang memiliki jumlah baris data pada table tr_penjualan_detail lebih dari satu.
Nama kolom yang harus ditampilkan:  kode_transaksi, kode_pelanggan, nama_pelanggan, tanggal_transaksi, jumlah_detail
Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.


<details>
  <summary>Click to expand!</summary>
  
'''
select tr_penjualan_detail.kode_transaksi,ms_pelanggan.kode_pelanggan,ms_pelanggan.nama_pelanggan,tr_penjualan.tanggal_transaksi,count(tr_penjualan_detail.kode_produk) as jumlah_detail
from ms_pelanggan
LEFT JOIN tr_penjualan ON
tr_penjualan.kode_pelanggan = ms_pelanggan.kode_pelanggan
LEFT JOIN tr_penjualan_detail ON
tr_penjualan.kode_transaksi = tr_penjualan_detail.kode_transaksi
group by tr_penjualan_detail.kode_transaksi,ms_pelanggan.kode_pelanggan,ms_pelanggan.nama_pelanggan,tr_penjualan.tanggal_transaksi
having count(tr_penjualan_detail.kode_produk)>1;
'''

</details>





