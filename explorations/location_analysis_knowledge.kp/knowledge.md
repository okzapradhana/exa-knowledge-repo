---
title: Location Analysis on Compfest Data Science Academy
authors:
- Okza Pradhana
- Faiz Al Hadiid
- Reza
tags:
- academy
- location
- compfest
created_at: 2019-06-29 00:00:00
updated_at: 2020-07-03 15:00:10.546246
tldr: Doing analysis on Travelers location
---

```python
from pandas.compat import StringIO
import pandas as pd
```

```python

csv_string: str = open('catatan_lokasi.csv').read()
csv_string = csv_string.replace('/19', '/2019')
csv_string

str_io = StringIO(csv_string)
df = pandas.read_csv(str_io)
df['tanggal'] = pandas.to_datetime(df['tanggal'], format = "%d/%m/%Y")
df = df.sort_values(by=["id", "tanggal"])
df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2019-05-21</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>100</th>
      <td>1</td>
      <td>2019-05-22</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>200</th>
      <td>1</td>
      <td>2019-05-23</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>300</th>
      <td>1</td>
      <td>2019-05-24</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>400</th>
      <td>1</td>
      <td>2019-05-25</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>500</th>
      <td>1</td>
      <td>2019-05-26</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>600</th>
      <td>1</td>
      <td>2019-05-27</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>700</th>
      <td>1</td>
      <td>2019-05-28</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>800</th>
      <td>1</td>
      <td>2019-05-29</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>900</th>
      <td>1</td>
      <td>2019-05-30</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1000</th>
      <td>1</td>
      <td>2019-05-31</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1100</th>
      <td>1</td>
      <td>2019-06-01</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1200</th>
      <td>1</td>
      <td>2019-06-02</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1300</th>
      <td>1</td>
      <td>2019-06-03</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1400</th>
      <td>1</td>
      <td>2019-06-04</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1500</th>
      <td>1</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1600</th>
      <td>1</td>
      <td>2019-06-06</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1700</th>
      <td>1</td>
      <td>2019-06-07</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1800</th>
      <td>1</td>
      <td>2019-06-08</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1900</th>
      <td>1</td>
      <td>2019-06-09</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>2000</th>
      <td>1</td>
      <td>2019-06-10</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>2100</th>
      <td>1</td>
      <td>2019-06-11</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>2200</th>
      <td>1</td>
      <td>2019-06-12</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>2300</th>
      <td>1</td>
      <td>2019-06-13</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>2400</th>
      <td>1</td>
      <td>2019-06-14</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>2500</th>
      <td>1</td>
      <td>2019-06-15</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>2019-05-21</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>101</th>
      <td>2</td>
      <td>2019-05-22</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>201</th>
      <td>2</td>
      <td>2019-05-23</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>301</th>
      <td>2</td>
      <td>2019-05-24</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2298</th>
      <td>99</td>
      <td>2019-06-12</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2398</th>
      <td>99</td>
      <td>2019-06-13</td>
      <td>Kota Depok</td>
    </tr>
    <tr>
      <th>2498</th>
      <td>99</td>
      <td>2019-06-14</td>
      <td>Kabupaten Bekasi</td>
    </tr>
    <tr>
      <th>2598</th>
      <td>99</td>
      <td>2019-06-15</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>99</th>
      <td>100</td>
      <td>2019-05-21</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>199</th>
      <td>100</td>
      <td>2019-05-22</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>299</th>
      <td>100</td>
      <td>2019-05-23</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>399</th>
      <td>100</td>
      <td>2019-05-24</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>499</th>
      <td>100</td>
      <td>2019-05-25</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>599</th>
      <td>100</td>
      <td>2019-05-26</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>699</th>
      <td>100</td>
      <td>2019-05-27</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>799</th>
      <td>100</td>
      <td>2019-05-28</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>899</th>
      <td>100</td>
      <td>2019-05-29</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>999</th>
      <td>100</td>
      <td>2019-05-30</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1099</th>
      <td>100</td>
      <td>2019-05-31</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1199</th>
      <td>100</td>
      <td>2019-06-01</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1299</th>
      <td>100</td>
      <td>2019-06-02</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1399</th>
      <td>100</td>
      <td>2019-06-03</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1499</th>
      <td>100</td>
      <td>2019-06-04</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1599</th>
      <td>100</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1699</th>
      <td>100</td>
      <td>2019-06-06</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1799</th>
      <td>100</td>
      <td>2019-06-07</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1899</th>
      <td>100</td>
      <td>2019-06-08</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1999</th>
      <td>100</td>
      <td>2019-06-09</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2099</th>
      <td>100</td>
      <td>2019-06-10</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2199</th>
      <td>100</td>
      <td>2019-06-11</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2299</th>
      <td>100</td>
      <td>2019-06-12</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2399</th>
      <td>100</td>
      <td>2019-06-13</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2499</th>
      <td>100</td>
      <td>2019-06-14</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2599</th>
      <td>100</td>
      <td>2019-06-15</td>
      <td>Jakarta Timur</td>
    </tr>
  </tbody>
</table>
<p>2600 rows × 3 columns</p>
</div>




```python
id_before = -1
start_loc = []
end_loc = []

for row in df.iterrows():
    current_id = row[1]['id']
    location = row[1]['lokasi_dominan']
    
    if (current_id != id_before):
        start_loc.append(location)
        end_loc.append(location)
    else :
        end_loc[-1] = location
    id_before = current_id
    

```

```python
all([start_loc[i] == end_loc[i] for i in range(len(start_loc))])
```




    True




```python

```

```python
df.info()
```
    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 2600 entries, 0 to 2599
    Data columns (total 3 columns):
    id                2600 non-null int64
    tanggal           2600 non-null datetime64[ns]
    lokasi_dominan    2600 non-null object
    dtypes: datetime64[ns](1), int64(1), object(1)
    memory usage: 81.2+ KB



```python
df[df['tanggal'] == '2019-05-21']['lokasi_dominan'].value_counts()
```




    Kota Bogor                13
    Kota Depok                11
    Jakarta Timur             11
    Kota Bekasi               10
    Jakarta Pusat              8
    Jakarta Utara              8
    Kabupaten Bogor            7
    Jakarta Barat              6
    Kota Tangerang             6
    Kota Tangerang Selatan     6
    Kabupaten Bekasi           6
    Jakarta Selatan            5
    Kabupaten Tangerang        3
    Name: lokasi_dominan, dtype: int64




```python
df[df['id'] == 80]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>79</th>
      <td>80</td>
      <td>2019-05-21</td>
      <td>Kota Bogor</td>
    </tr>
    <tr>
      <th>179</th>
      <td>80</td>
      <td>2019-05-22</td>
      <td>Jakarta Barat</td>
    </tr>
    <tr>
      <th>279</th>
      <td>80</td>
      <td>2019-05-23</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>379</th>
      <td>80</td>
      <td>2019-05-24</td>
      <td>Kota Bogor</td>
    </tr>
    <tr>
      <th>479</th>
      <td>80</td>
      <td>2019-05-25</td>
      <td>Jakarta Barat</td>
    </tr>
    <tr>
      <th>579</th>
      <td>80</td>
      <td>2019-05-26</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>679</th>
      <td>80</td>
      <td>2019-05-27</td>
      <td>Kota Bogor</td>
    </tr>
    <tr>
      <th>779</th>
      <td>80</td>
      <td>2019-05-28</td>
      <td>Jakarta Barat</td>
    </tr>
    <tr>
      <th>879</th>
      <td>80</td>
      <td>2019-05-29</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>979</th>
      <td>80</td>
      <td>2019-05-30</td>
      <td>Kota Bogor</td>
    </tr>
    <tr>
      <th>1079</th>
      <td>80</td>
      <td>2019-05-31</td>
      <td>Jakarta Barat</td>
    </tr>
    <tr>
      <th>1179</th>
      <td>80</td>
      <td>2019-06-01</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>1279</th>
      <td>80</td>
      <td>2019-06-02</td>
      <td>Kabupaten Tangerang</td>
    </tr>
    <tr>
      <th>1379</th>
      <td>80</td>
      <td>2019-06-03</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>1479</th>
      <td>80</td>
      <td>2019-06-04</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>1579</th>
      <td>80</td>
      <td>2019-06-05</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>1679</th>
      <td>80</td>
      <td>2019-06-06</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>1779</th>
      <td>80</td>
      <td>2019-06-07</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>1879</th>
      <td>80</td>
      <td>2019-06-08</td>
      <td>Kabupaten Tangerang</td>
    </tr>
    <tr>
      <th>1979</th>
      <td>80</td>
      <td>2019-06-09</td>
      <td>Kota Bogor</td>
    </tr>
    <tr>
      <th>2079</th>
      <td>80</td>
      <td>2019-06-10</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>2179</th>
      <td>80</td>
      <td>2019-06-11</td>
      <td>Jakarta Barat</td>
    </tr>
    <tr>
      <th>2279</th>
      <td>80</td>
      <td>2019-06-12</td>
      <td>Kota Bogor</td>
    </tr>
    <tr>
      <th>2379</th>
      <td>80</td>
      <td>2019-06-13</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>2479</th>
      <td>80</td>
      <td>2019-06-14</td>
      <td>Jakarta Barat</td>
    </tr>
    <tr>
      <th>2579</th>
      <td>80</td>
      <td>2019-06-15</td>
      <td>Kota Bogor</td>
    </tr>
  </tbody>
</table>
</div>




```python
data_join = pd.read_csv('data_join.csv')
```

```python
data_join
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>jenis_kelamin</th>
      <th>divisi</th>
      <th>umur</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-21</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-22</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-23</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-24</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-25</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-26</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-27</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-28</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-29</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-30</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-31</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-01</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-02</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-03</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-04</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>16</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-06</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>17</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-07</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>18</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-08</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>19</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-09</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>20</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-10</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>21</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-11</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>22</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-12</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>23</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-13</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>24</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-14</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>25</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-15</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>26</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-05-21</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>27</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-05-22</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>28</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-05-23</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>29</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-05-24</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2570</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-12</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2571</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-13</td>
      <td>Kota Depok</td>
    </tr>
    <tr>
      <th>2572</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-14</td>
      <td>Kabupaten Bekasi</td>
    </tr>
    <tr>
      <th>2573</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-15</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2574</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-21</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2575</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-22</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2576</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-23</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2577</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-24</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2578</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-25</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2579</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-26</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2580</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-27</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2581</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-28</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2582</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-29</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2583</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-30</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2584</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-31</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2585</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-01</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2586</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-02</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2587</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-03</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2588</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-04</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2589</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2590</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-06</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2591</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-07</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2592</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-08</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2593</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-09</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2594</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-10</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2595</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-11</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2596</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-12</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2597</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-13</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2598</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-14</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2599</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-15</td>
      <td>Jakarta Timur</td>
    </tr>
  </tbody>
</table>
<p>2600 rows × 6 columns</p>
</div>




```python
data_join[data_join['tanggal'] == "2019-06-05"]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>jenis_kelamin</th>
      <th>divisi</th>
      <th>umur</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>15</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>41</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-05</td>
      <td>Kota Manado</td>
    </tr>
    <tr>
      <th>67</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>93</th>
      <td>4</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>21</td>
      <td>2019-06-05</td>
      <td>Kota Bandar Lampung</td>
    </tr>
    <tr>
      <th>119</th>
      <td>5</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>145</th>
      <td>6</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>171</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>197</th>
      <td>8</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>22</td>
      <td>2019-06-05</td>
      <td>Kota Semarang</td>
    </tr>
    <tr>
      <th>223</th>
      <td>9</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>21</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>249</th>
      <td>10</td>
      <td>Laki-laki</td>
      <td>Data Science</td>
      <td>21</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>275</th>
      <td>11</td>
      <td>Perempuan</td>
      <td>Marketing</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>301</th>
      <td>12</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>327</th>
      <td>13</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kabupaten Tasikmalaya</td>
    </tr>
    <tr>
      <th>353</th>
      <td>14</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>379</th>
      <td>15</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>33</td>
      <td>2019-06-05</td>
      <td>Kota Bandung</td>
    </tr>
    <tr>
      <th>405</th>
      <td>16</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>33</td>
      <td>2019-06-05</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>431</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>457</th>
      <td>18</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kota Semarang</td>
    </tr>
    <tr>
      <th>483</th>
      <td>19</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>31</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>509</th>
      <td>20</td>
      <td>Perempuan</td>
      <td>Customer Service</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>535</th>
      <td>21</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>30</td>
      <td>2019-06-05</td>
      <td>Kota Bandung</td>
    </tr>
    <tr>
      <th>561</th>
      <td>22</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>35</td>
      <td>2019-06-05</td>
      <td>Kota Bandar Lampung</td>
    </tr>
    <tr>
      <th>587</th>
      <td>23</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>613</th>
      <td>24</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kabupaten Tasikmalaya</td>
    </tr>
    <tr>
      <th>639</th>
      <td>25</td>
      <td>Perempuan</td>
      <td>Data Engineer</td>
      <td>32</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>665</th>
      <td>26</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>691</th>
      <td>27</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>717</th>
      <td>28</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kabupaten Kebumen</td>
    </tr>
    <tr>
      <th>743</th>
      <td>29</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>32</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>769</th>
      <td>30</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1835</th>
      <td>71</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>33</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>1861</th>
      <td>72</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-05</td>
      <td>Kota Semarang</td>
    </tr>
    <tr>
      <th>1887</th>
      <td>73</td>
      <td>Laki-laki</td>
      <td>Data Science</td>
      <td>24</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1913</th>
      <td>74</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bekasi</td>
    </tr>
    <tr>
      <th>1939</th>
      <td>75</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kota Tangerang Selatan</td>
    </tr>
    <tr>
      <th>1965</th>
      <td>76</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>27</td>
      <td>2019-06-05</td>
      <td>Kota Tangerang Selatan</td>
    </tr>
    <tr>
      <th>1991</th>
      <td>77</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>26</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bekasi</td>
    </tr>
    <tr>
      <th>2017</th>
      <td>78</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2043</th>
      <td>79</td>
      <td>Perempuan</td>
      <td>Data Engineer</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2069</th>
      <td>80</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>33</td>
      <td>2019-06-05</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>2095</th>
      <td>81</td>
      <td>Laki-laki</td>
      <td>Data Science</td>
      <td>30</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2121</th>
      <td>82</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>27</td>
      <td>2019-06-05</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2147</th>
      <td>83</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>2173</th>
      <td>84</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>32</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>2199</th>
      <td>85</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2225</th>
      <td>86</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-05</td>
      <td>Jakarta Barat</td>
    </tr>
    <tr>
      <th>2251</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2277</th>
      <td>88</td>
      <td>Laki-laki</td>
      <td>Marketing</td>
      <td>24</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>2303</th>
      <td>89</td>
      <td>Perempuan</td>
      <td>Marketing</td>
      <td>24</td>
      <td>2019-06-05</td>
      <td>Kota Bogor</td>
    </tr>
    <tr>
      <th>2329</th>
      <td>90</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kota Semarang</td>
    </tr>
    <tr>
      <th>2355</th>
      <td>91</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>27</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>2381</th>
      <td>92</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>27</td>
      <td>2019-06-05</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2407</th>
      <td>93</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>27</td>
      <td>2019-06-05</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>2433</th>
      <td>94</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2459</th>
      <td>95</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kota Bandung</td>
    </tr>
    <tr>
      <th>2485</th>
      <td>96</td>
      <td>Perempuan</td>
      <td>Customer Service</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2511</th>
      <td>97</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>32</td>
      <td>2019-06-05</td>
      <td>Kota Bandar Lampung</td>
    </tr>
    <tr>
      <th>2537</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2563</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2589</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 6 columns</p>
</div>




```python
jabodetabek = 'Jakarta|Bogor|Depok|Tangerang|Bekasi'
```

```python
hari_mudik = data_join[data_join['tanggal'] == "2019-06-05"]
```

```python
yang_mudik = hari_mudik[~hari_mudik['lokasi_dominan'].str.contains(jabodetabek)]
```

```python
yang_mudik[yang_mudik['tanggal'] == '2019-05-30']
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>jenis_kelamin</th>
      <th>divisi</th>
      <th>umur</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
yang_mudik['divisi'].value_counts()
```




    Software Engineer        26
    Business Intelligence    19
    Customer Service         15
    Data Engineer            13
    Data Science             10
    Marketing                 8
    Name: divisi, dtype: int64




```python
yang_mudik['divisi'].describe()
```




    count                    91
    unique                    6
    top       Software Engineer
    freq                     26
    Name: divisi, dtype: object




```python
marketing = data_join[data_join['divisi'] == 'Customer Service']
```

```python
marketing[marketing['tanggal'] == '2019-06-05'].describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>umur</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>15.000000</td>
      <td>15.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>48.000000</td>
      <td>28.933333</td>
    </tr>
    <tr>
      <th>std</th>
      <td>35.231885</td>
      <td>4.772940</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>22.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>19.500000</td>
      <td>25.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>37.000000</td>
      <td>28.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>83.500000</td>
      <td>34.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>96.000000</td>
      <td>35.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
tigapuluh_mei = data_join[data_join['tanggal'] == '2019-05-30']
```

```python
tigapuluh_mei[~tigapuluh_mei['lokasi_dominan'].str.contains(jabodetabek)]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>jenis_kelamin</th>
      <th>divisi</th>
      <th>umur</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-30</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>35</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-05-30</td>
      <td>Kota Manado</td>
    </tr>
    <tr>
      <th>113</th>
      <td>5</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-05-30</td>
      <td>Kota Bandung</td>
    </tr>
    <tr>
      <th>139</th>
      <td>6</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-05-30</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>217</th>
      <td>9</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>21</td>
      <td>2019-05-30</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>243</th>
      <td>10</td>
      <td>Laki-laki</td>
      <td>Data Science</td>
      <td>21</td>
      <td>2019-05-30</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>295</th>
      <td>12</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>28</td>
      <td>2019-05-30</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>321</th>
      <td>13</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>25</td>
      <td>2019-05-30</td>
      <td>Kabupaten Tasikmalaya</td>
    </tr>
    <tr>
      <th>425</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-05-30</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>451</th>
      <td>18</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-05-30</td>
      <td>Kota Semarang</td>
    </tr>
    <tr>
      <th>477</th>
      <td>19</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>31</td>
      <td>2019-05-30</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>503</th>
      <td>20</td>
      <td>Perempuan</td>
      <td>Customer Service</td>
      <td>23</td>
      <td>2019-05-30</td>
      <td>Kabupaten Lampung Selatan</td>
    </tr>
    <tr>
      <th>529</th>
      <td>21</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>30</td>
      <td>2019-05-30</td>
      <td>Kota Bandung</td>
    </tr>
    <tr>
      <th>555</th>
      <td>22</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>35</td>
      <td>2019-05-30</td>
      <td>Kota Bandar Lampung</td>
    </tr>
    <tr>
      <th>581</th>
      <td>23</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>34</td>
      <td>2019-05-30</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>607</th>
      <td>24</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-05-30</td>
      <td>Kabupaten Tasikmalaya</td>
    </tr>
    <tr>
      <th>659</th>
      <td>26</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>34</td>
      <td>2019-05-30</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>815</th>
      <td>32</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>30</td>
      <td>2019-05-30</td>
      <td>Kota Bandung</td>
    </tr>
    <tr>
      <th>841</th>
      <td>33</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-05-30</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>919</th>
      <td>36</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>23</td>
      <td>2019-05-30</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1023</th>
      <td>40</td>
      <td>Perempuan</td>
      <td>Data Engineer</td>
      <td>24</td>
      <td>2019-05-30</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1309</th>
      <td>51</td>
      <td>Laki-laki</td>
      <td>Marketing</td>
      <td>35</td>
      <td>2019-05-30</td>
      <td>Kota Manado</td>
    </tr>
    <tr>
      <th>1361</th>
      <td>53</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>32</td>
      <td>2019-05-30</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>1543</th>
      <td>60</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-05-30</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>1673</th>
      <td>65</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>33</td>
      <td>2019-05-30</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>1777</th>
      <td>69</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>32</td>
      <td>2019-05-30</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2089</th>
      <td>81</td>
      <td>Laki-laki</td>
      <td>Data Science</td>
      <td>30</td>
      <td>2019-05-30</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2271</th>
      <td>88</td>
      <td>Laki-laki</td>
      <td>Marketing</td>
      <td>24</td>
      <td>2019-05-30</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>2349</th>
      <td>91</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>27</td>
      <td>2019-05-30</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>2375</th>
      <td>92</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>27</td>
      <td>2019-05-30</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2479</th>
      <td>96</td>
      <td>Perempuan</td>
      <td>Customer Service</td>
      <td>23</td>
      <td>2019-05-30</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2531</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-05-30</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2557</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-05-30</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2583</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-05-30</td>
      <td>Kabupaten Sleman</td>
    </tr>
  </tbody>
</table>
</div>




```python
tidak_mudik = hari_mudik[hari_mudik['lokasi_dominan'].str.contains(jabodetabek)]
```

```python
tidak_mudik.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>umur</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>9.000000</td>
      <td>9.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>69.333333</td>
      <td>27.333333</td>
    </tr>
    <tr>
      <th>std</th>
      <td>22.383029</td>
      <td>3.708099</td>
    </tr>
    <tr>
      <th>min</th>
      <td>16.000000</td>
      <td>23.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>74.000000</td>
      <td>24.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>76.000000</td>
      <td>27.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>78.000000</td>
      <td>29.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>89.000000</td>
      <td>33.000000</td>
    </tr>
  </tbody>
</table>
</div>



## Persentase Pemudik Paling Sedikit


```python
data_join[data_join['lokasi_dominan'].str.contains('Medan')]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>jenis_kelamin</th>
      <th>divisi</th>
      <th>umur</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-05-26</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>166</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-05-31</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>167</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-01</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>168</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-02</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>169</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-03</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>170</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-04</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>171</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>172</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-06</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>173</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-07</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>174</th>
      <td>7</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-08</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>424</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-05-29</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>425</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-05-30</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>426</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-05-31</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>427</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-01</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>428</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-02</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>429</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-03</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>430</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-04</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>431</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>432</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-06</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>433</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-07</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>434</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-08</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>435</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-09</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>436</th>
      <td>17</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-10</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>477</th>
      <td>19</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>31</td>
      <td>2019-05-30</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>487</th>
      <td>19</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>31</td>
      <td>2019-06-09</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>919</th>
      <td>36</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>23</td>
      <td>2019-05-30</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>920</th>
      <td>36</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>23</td>
      <td>2019-05-31</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>921</th>
      <td>36</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>23</td>
      <td>2019-06-01</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>922</th>
      <td>36</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>23</td>
      <td>2019-06-02</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>923</th>
      <td>36</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>23</td>
      <td>2019-06-03</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1500</th>
      <td>58</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-08</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1573</th>
      <td>61</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>33</td>
      <td>2019-06-03</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1574</th>
      <td>61</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>33</td>
      <td>2019-06-04</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1575</th>
      <td>61</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>33</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1576</th>
      <td>61</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>33</td>
      <td>2019-06-06</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1577</th>
      <td>61</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>33</td>
      <td>2019-06-07</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1623</th>
      <td>63</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-01</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1624</th>
      <td>63</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-02</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1625</th>
      <td>63</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-03</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1626</th>
      <td>63</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-04</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1627</th>
      <td>63</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1628</th>
      <td>63</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-06</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1629</th>
      <td>63</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-07</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>1630</th>
      <td>63</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-08</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2246</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-05-31</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2247</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-01</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2248</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-02</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2249</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-03</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2250</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-04</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2251</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2252</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-06</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2253</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-07</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2254</th>
      <td>87</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>22</td>
      <td>2019-06-08</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2430</th>
      <td>94</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>28</td>
      <td>2019-06-02</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2431</th>
      <td>94</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>28</td>
      <td>2019-06-03</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2432</th>
      <td>94</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>28</td>
      <td>2019-06-04</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2433</th>
      <td>94</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2434</th>
      <td>94</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>28</td>
      <td>2019-06-06</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2435</th>
      <td>94</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>28</td>
      <td>2019-06-07</td>
      <td>Kota Medan</td>
    </tr>
    <tr>
      <th>2436</th>
      <td>94</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>28</td>
      <td>2019-06-08</td>
      <td>Kota Medan</td>
    </tr>
  </tbody>
</table>
<p>85 rows × 6 columns</p>
</div>




```python
#Yogya
diy = "Sleman|Yogyakarta|Bantul"
hari_mudik[hari_mudik['lokasi_dominan'].str.contains(diy)]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>jenis_kelamin</th>
      <th>divisi</th>
      <th>umur</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>119</th>
      <td>5</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>21</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>145</th>
      <td>6</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>249</th>
      <td>10</td>
      <td>Laki-laki</td>
      <td>Data Science</td>
      <td>21</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>275</th>
      <td>11</td>
      <td>Perempuan</td>
      <td>Marketing</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>301</th>
      <td>12</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>483</th>
      <td>19</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>31</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>639</th>
      <td>25</td>
      <td>Perempuan</td>
      <td>Data Engineer</td>
      <td>32</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>665</th>
      <td>26</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>743</th>
      <td>29</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>32</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>769</th>
      <td>30</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>847</th>
      <td>33</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>26</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>899</th>
      <td>35</td>
      <td>Perempuan</td>
      <td>Data Science</td>
      <td>26</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>977</th>
      <td>38</td>
      <td>Laki-laki</td>
      <td>Marketing</td>
      <td>24</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1133</th>
      <td>44</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>22</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1159</th>
      <td>45</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>35</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>1185</th>
      <td>46</td>
      <td>Laki-laki</td>
      <td>Marketing</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1237</th>
      <td>48</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>1341</th>
      <td>52</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>1445</th>
      <td>56</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1471</th>
      <td>57</td>
      <td>Perempuan</td>
      <td>Marketing</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>1679</th>
      <td>65</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>33</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>1783</th>
      <td>69</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>32</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>1835</th>
      <td>71</td>
      <td>Laki-laki</td>
      <td>Business Intelligence</td>
      <td>33</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>1887</th>
      <td>73</td>
      <td>Laki-laki</td>
      <td>Data Science</td>
      <td>24</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2043</th>
      <td>79</td>
      <td>Perempuan</td>
      <td>Data Engineer</td>
      <td>25</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2095</th>
      <td>81</td>
      <td>Laki-laki</td>
      <td>Data Science</td>
      <td>30</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2199</th>
      <td>85</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2355</th>
      <td>91</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>27</td>
      <td>2019-06-05</td>
      <td>Kabupaten Bantul</td>
    </tr>
    <tr>
      <th>2485</th>
      <td>96</td>
      <td>Perempuan</td>
      <td>Customer Service</td>
      <td>23</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2537</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-05</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2589</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-05</td>
      <td>Kabupaten Sleman</td>
    </tr>
  </tbody>
</table>
</div>




```python
pulang = data_join[data_join['tanggal'] > '2019-06-05']
```

```python
pulang
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>jenis_kelamin</th>
      <th>divisi</th>
      <th>umur</th>
      <th>tanggal</th>
      <th>lokasi_dominan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>16</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-06</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>17</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-07</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>18</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-08</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>19</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-09</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>20</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-10</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>21</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-11</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>22</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-12</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>23</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-13</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>24</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-14</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>25</th>
      <td>1</td>
      <td>Laki-laki</td>
      <td>Customer Service</td>
      <td>34</td>
      <td>2019-06-15</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>42</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-06</td>
      <td>Kota Manado</td>
    </tr>
    <tr>
      <th>43</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-07</td>
      <td>Kota Manado</td>
    </tr>
    <tr>
      <th>44</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-08</td>
      <td>Kota Manado</td>
    </tr>
    <tr>
      <th>45</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-09</td>
      <td>Kota Manado</td>
    </tr>
    <tr>
      <th>46</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-10</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>47</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-11</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>48</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-12</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>49</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-13</td>
      <td>Jakarta Selatan</td>
    </tr>
    <tr>
      <th>50</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-14</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>51</th>
      <td>2</td>
      <td>Laki-laki</td>
      <td>Data Engineer</td>
      <td>26</td>
      <td>2019-06-15</td>
      <td>Kabupaten Bogor</td>
    </tr>
    <tr>
      <th>68</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-06</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>69</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-07</td>
      <td>Kota Padang</td>
    </tr>
    <tr>
      <th>70</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-08</td>
      <td>Kota Depok</td>
    </tr>
    <tr>
      <th>71</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-09</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>72</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-10</td>
      <td>Kabupaten Bekasi</td>
    </tr>
    <tr>
      <th>73</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-11</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>74</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-12</td>
      <td>Kabupaten Bekasi</td>
    </tr>
    <tr>
      <th>75</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-13</td>
      <td>Kota Bekasi</td>
    </tr>
    <tr>
      <th>76</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-14</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>77</th>
      <td>3</td>
      <td>Laki-laki</td>
      <td>Software Engineer</td>
      <td>28</td>
      <td>2019-06-15</td>
      <td>Jakarta Pusat</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2538</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-06</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2539</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-07</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2540</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-08</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2541</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-09</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2542</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-10</td>
      <td>Kota Yogyakarta</td>
    </tr>
    <tr>
      <th>2543</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-11</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2544</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-12</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2545</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-13</td>
      <td>Kota Bogor</td>
    </tr>
    <tr>
      <th>2546</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-14</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2547</th>
      <td>98</td>
      <td>Perempuan</td>
      <td>Business Intelligence</td>
      <td>28</td>
      <td>2019-06-15</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2564</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-06</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2565</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-07</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2566</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-08</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2567</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-09</td>
      <td>Kabupaten Wonogiri</td>
    </tr>
    <tr>
      <th>2568</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-10</td>
      <td>Kota Depok</td>
    </tr>
    <tr>
      <th>2569</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-11</td>
      <td>Kabupaten Bekasi</td>
    </tr>
    <tr>
      <th>2570</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-12</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2571</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-13</td>
      <td>Kota Depok</td>
    </tr>
    <tr>
      <th>2572</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-14</td>
      <td>Kabupaten Bekasi</td>
    </tr>
    <tr>
      <th>2573</th>
      <td>99</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>25</td>
      <td>2019-06-15</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2590</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-06</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2591</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-07</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2592</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-08</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2593</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-09</td>
      <td>Kabupaten Sleman</td>
    </tr>
    <tr>
      <th>2594</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-10</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2595</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-11</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2596</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-12</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2597</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-13</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2598</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-14</td>
      <td>Jakarta Timur</td>
    </tr>
    <tr>
      <th>2599</th>
      <td>100</td>
      <td>Perempuan</td>
      <td>Software Engineer</td>
      <td>29</td>
      <td>2019-06-15</td>
      <td>Jakarta Timur</td>
    </tr>
  </tbody>
</table>
<p>1000 rows × 6 columns</p>
</div>




```python
pulang[pulang['lokasi_dominan'].str.contains(jabodetabek)].describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>umur</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>675.000000</td>
      <td>675.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>52.223704</td>
      <td>27.669630</td>
    </tr>
    <tr>
      <th>std</th>
      <td>28.275542</td>
      <td>4.290858</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>21.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>29.000000</td>
      <td>24.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>53.000000</td>
      <td>27.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>76.500000</td>
      <td>32.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>100.000000</td>
      <td>35.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
pulang[pulang['lokasi_dominan'].str.contains(jabodetabek)]['tanggal'].value_counts()
```




    2019-06-15    100
    2019-06-14    100
    2019-06-11     98
    2019-06-12     98
    2019-06-13     97
    2019-06-10     81
    2019-06-09     66
    2019-06-08     17
    2019-06-06      9
    2019-06-07      9
    Name: tanggal, dtype: int64




```python
orang_mudik = data_join[data_join['tanggal'] < '2019-06-05']
```

```python
orang_mudik[~orang_mudik['lokasi_dominan'].str.contains(jabodetabek)]['tanggal'].value_counts()
```




    2019-06-03    93
    2019-06-04    91
    2019-06-02    83
    2019-06-01    73
    2019-05-31    58
    2019-05-30    34
    2019-05-29    19
    2019-05-28     9
    2019-05-27     5
    2019-05-26     5
    2019-05-23     3
    2019-05-25     2
    2019-05-24     2
    Name: tanggal, dtype: int64




```python

```