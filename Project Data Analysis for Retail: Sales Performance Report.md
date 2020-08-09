![image](https://user-images.githubusercontent.com/68532033/89724335-d5954580-da2b-11ea-8058-bed5e3995cdd.png)
```
Untuk menyelesaikan project, maka kita akan mengetikkan code yang perlu disubmit untuk dicek jawabannya benar atau salah.
Dari data yang sudah diberikan, dari pihak manajemen DQLab store ingin mengetahui:
1A. Overall perofrmance DQLab Store dari tahun 2009 - 2012 untuk jumlah order dan total sales order finished
1B. Overall performance DQLab by subcategory product yang akan dibandingkan antara tahun 2011 dan tahun 2012
2A. Efektifitas dan efisiensi promosi yang dilakukan selama ini, dengan menghitung burn rate dari promosi yang dilakukan overall berdasarkan tahun
2B. Efektifitas dan efisiensi promosi yang dilakukan selama ini, dengan menghitung burn rate dari promosi yang dilakukan overall berdasarkan sub-category

Setelah melihat hasil analisa di Sub Bab 1 dan 2, selanjutnya dilakukan analisa terhadap customer DQLab. Analisa dari sisi customer dengan menggunakan metrics:
3A. Analisa terhadap customer setiap tahunnya
3B. Analisa terhadap jumlah customer baru setiap tahunnya
3C. Cohort untuk mengetahui angka retention customer tahun 2009
```

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


<b>2. Overall Performance by Product Sub Category</b>
<br>
![image](https://user-images.githubusercontent.com/68532033/89724456-49841d80-da2d-11ea-8034-0a76560cd6c2.png)
<details>
  <summary>Click to show query sql</summary>
  <p>

```
select left(order_date,4) as years,product_sub_category,sum(sales) as sales
from dqlab_sales_store
where left(order_date,4) in ('2011','2012') and order_status = 'Order Finished'
group by left(order_date,4),product_sub_category
order by left(order_date,4),sum(sales) desc;
```
  </p>
</details>
