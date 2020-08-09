
![image](https://user-images.githubusercontent.com/68532033/89723332-fa36f080-da1e-11ea-850e-416586f3e187.png)

<details>
  <summary>Click to show query sql</summary>
  <i>select no_urut,kode_produk,nama_produk,harga from ms_produk where harga >= 50000 and harga <= 150000;</i>
</details>

![image](https://user-images.githubusercontent.com/68532033/89723362-569a1000-da1f-11ea-866b-9d83fcc59145.png)
<details>
  <summary>Click to show query sql</summary>
  <i>
select no_urut,kode_produk,nama_produk,harga from ms_produk where nama_produk like '%Flashdisk%';
</i>
</details>














![image](https://user-images.githubusercontent.com/68532033/89723285-5e0ce980-da1e-11ea-97d9-9a0e8ec4cbc8.png)

<details>
  <summary>Click to show query sql</summary>
  <i>
select tr_penjualan_detail.kode_transaksi,ms_pelanggan.kode_pelanggan,ms_pelanggan.nama_pelanggan,tr_penjualan.tanggal_transaksi,count(tr_penjualan_detail.kode_produk) as jumlah_detail
from ms_pelanggan
LEFT JOIN tr_penjualan ON
tr_penjualan.kode_pelanggan = ms_pelanggan.kode_pelanggan
LEFT JOIN tr_penjualan_detail ON
tr_penjualan.kode_transaksi = tr_penjualan_detail.kode_transaksi
group by tr_penjualan_detail.kode_transaksi,ms_pelanggan.kode_pelanggan,ms_pelanggan.nama_pelanggan,tr_penjualan.tanggal_transaksi
having count(tr_penjualan_detail.kode_produk)>1;
  </i>
</details>






