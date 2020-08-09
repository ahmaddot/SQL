![image](https://user-images.githubusercontent.com/68532033/89724335-d5954580-da2b-11ea-8058-bed5e3995cdd.png)
```
Project SQL pertama di DQLab yaitu "Data Engineer Challenge with SQL". Dimana di project ini kita menggunakan 
syntax left join,right join,inner join, dan union. Kita menggunakan table yang sudah di sediakan DQLab yaitu 
ms_pelanggan,ms_produk,tr_penjualan dan tr_penjualan_detail.Semua table sudah tersedia, kita tinggal menulis query dalam Code Editor.
```
![image](https://user-images.githubusercontent.com/68532033/89724369-6c620200-da2c-11ea-99ff-89538ede7ccc.png)

<b>1. Overall Performance by Year</b>
<br>
![image](https://user-images.githubusercontent.com/68532033/89724378-8dc2ee00-da2c-11ea-89c1-d8d97d513c88.png)

<details>
  <summary>Click to show query sql</summary>
  <p>

```
select left(order_date,4) as years,sum(sales) as sales,count(order_status) as number_of_order from dqlab_sales_store
where order_status = 'Order Finished'
group by left(order_date,4);
```
  </p>
</details>
