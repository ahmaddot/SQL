![image](https://user-images.githubusercontent.com/68532033/89723285-5e0ce980-da1e-11ea-97d9-9a0e8ec4cbc8.png)

<details>
  <summary>Click to show query sql</summary>
select tr_penjualan_detail.kode_transaksi,ms_pelanggan.kode_pelanggan,ms_pelanggan.nama_pelanggan,tr_penjualan.tanggal_transaksi,count(tr_penjualan_detail.kode_produk) as jumlah_detail
from ms_pelanggan
LEFT JOIN tr_penjualan ON
tr_penjualan.kode_pelanggan = ms_pelanggan.kode_pelanggan
LEFT JOIN tr_penjualan_detail ON
tr_penjualan.kode_transaksi = tr_penjualan_detail.kode_transaksi
group by tr_penjualan_detail.kode_transaksi,ms_pelanggan.kode_pelanggan,ms_pelanggan.nama_pelanggan,tr_penjualan.tanggal_transaksi
having count(tr_penjualan_detail.kode_produk)>1;
</details>






