1. Praktek 1:
```sql
SELECT orders.OrderID, orderDate, orders.CustID,
customers.CompanyName, customers.ContactName, customers.City,
customers.Phone
FROM orders, customers
WHERE orders.CustID = customers.CustomerID;
```
![](Assets/praktikum2(1).jpg)
- `SELECT` : Untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil
- `orders.OrderID` : orders merupakan nama tabel yang ingin ditampilkan kolomnya yaitu OrdersID. Jadi kolom OrderID dalam tabel orders ingin ditampilkan.
- `orders.Order Date` : kolom orderDate dalam. tabel orders ingin ditampilkan
- `orders.custID` : kolom custID dalam tabel orders dipilih untuk ditampilkan
- `Customers.companyName` : kolom CompanyName dalam tabel customers dipilih untuk ditampilkan.
- `customers.contactnome` : kolom ContactName dalam tabel customers dipilih untuk ditampilkan.
- `customers.City` :  kolom City dalam tabel customers dipilih untuk ditampilkan.
- `customers.Phone` : kolom Phone dalam tabel customers dipilih untuk ditampilkan
- `FROM orders, customers`: untuk memilih dari tabel mana saja yang kolomnya ingin dipilih untuk ditampilkan. Orders adalah nama tabel Pertama yang dipilih dan customers adalah nama tabel kedua yang dipilih.
- `WHERE`: Kondisi Yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan 
- `(orders.custID = customers.customerID)` : Kondisi dari WHERE yang harus dipenuhi. Jadi, data Pada kolom custID dalam tabel orders hans sama dengan data Pada kolom customerID dalam tabel customers adar masing-masing data bisa ditampilkan.

Hasilnya yang akan adalah kolom Order ID, order Date dan custID dari tabel, orders dan kojom companyNume, contact Moyoe, city, dan Phane dari tabel astomers.

2. Praktek 2
```sql
SELECT o.OrderID, o.OrderDate, o.CustID,
c.CompanyName, c.ContactName, c.City,
c.Phone
FROM orders o, customers c
WHERE o.CustID = c.CustomerID AND c.City = "London";
```
![](Assets/praktikum2(2).jpg)
- `SELECT` : untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `o.orderID` : o merupakan Singkatan dari tabel orders, kolom order ID merupakan kolom dari tabel orders Yang dipilih untuk ditampilkan.
- `o.OrderDate `: kolom orderDate merupakan kolom dari tabel o Yaitu orders Yons dipilih untuk ditampilkan,
- `o.custID` : tolong custID merupakan kolom dari tabel o Yaitu orders yang dipilih untuk ditampilkan
- `c.CompanyName` : c merupakan singkatan dari tabel customers. kolom company Name merupakan kolom dari tabel customers Yang dipilih untuk ditampilkan.
- `c.ContactName` : kolom contactName merupakan kolom dari tabel c Yaitu custome Yang dipilih untuk ditampilkan.
- `c.City` : kolom city merupakan kolom dari tabel a Yaitu customers Yang dipilih
untuk ditampilkan.
- `c.Phone` : kolom Phone merupakan kolom dari tabel a Yaitu customers Yang dipilih untuk ditampilkan.
- `FROM orders o, customers c` : untuk memilih dari tabel mang saja yang kolomme ingin dipilih untuk ditampilkan. Orders adalah nama tabel yanů dipilih watue ditampilkan tapi disingkat Jadi O, agar lebih mudah dan cepat. customers adalah nama tabel Yan's dipilih untuk ditampilkan tapi disinskat Jadi C. 
- `WHERE` : kondisi yang harus dipenuhi oleh suatu kojom data agar bisa ditampilkan
- `(o.CustID = costumer ID)` : data Pada kolom CustID dalam tabel o (urders) hans Sama dengan data Pada kolom customer ID dalam tabel c (customers). AND = untuk menyekaksi dua data atau lebih Pada Perintah WHERE.
- `(c.city = "London")` : kondisi tambahan yang harus dipenuhi Juga. Jadi Pada kolom city dari tabel c(customers) datarra harus berisi data "London" agar bisa ditampil Hasilnya = Jadi hanya barisan data Yani kolom city dari tabel customers mempunyai data "London" Yang bisa tampil.

3. Praktek 3
```sql
 SELECT o.OrderID, o.OrderDate, c.CompanyName,
    -> c.ContactName, c.Phone, e.LastName, e.Title
    -> FROM orders o, customers c, employees e
    -> WHERE o.CustID = c.CustomerID AND o.EmpID = e.Empld;
```
![](Assets/praktikum2(3).jpg)
- `SELECT` : untuk memilih kolam mana saja Yand insin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `o.OrderID, o.OrderDate` : kolom orderID dan order Date dati tabel o(orders) dipilih untuk ditampilkan
- `c.companyName, c.contactName, c.Phone` : kolom-kolom companyName, Contact Name dan Phone dari tabel c(customers) dipilih untuk ditampilkan. e. Lastname, e.Title = kolom Lastname dan Title dari tabel e(employees) dipilih Untuk ditampilkan.
- `From orders o. customers c, employees e` : untuk memilih dari tabel mana saja Yang kolomnya dipillh untur ditampilkan. orders disingkat jadi o adalah nama tabel Yang dipilih. Customers disingkat Jadi c adalah nama tabel Yang dipilih. employees disingkat Jadi e adalah nama tabel yang dipilih untuk ditampilkan. 
- `WHERE` : kondisi yang harus dipenuhi oleh suatu data ajat bisa ditampilkan.
- `(CustID = c.customerID)`: data Pada kolom custID dalam tabel o(orders) harus 
	Sama densan data Pada kotom customerID dalam tabel c(cocustomers).
- `AND` : untuk menyeleksi dua data atau lebih Pada Perintah WHERE.
- `(o.EmpID = e.EmpID)` = data pada kolom EMPID dalam tabel o(orders) hatus Sama dengan data Pada kolom EmpID dakam tabel e(employees) Hasilnya Yang tampil adalah kojom Yang memenuhi semua kondisi dari WHERE.

4. Praktek 4
```sql
 SELECT o.OrderID, o.OrderDate, c.CompanyName,
    -> c.ContactName, c.Phone, e.LastName, e.Title
    -> FROM orders o, customers c, employees e
    -> WHERE o.CustID = c.CustomerID AND o.EmpID = e.Empld AND
    -> e.FirstName = "Margaret";```

![](Assets/praktikum2(4).jpg)
- `SELECT` : untuk memilih kolom mana saja Yang insin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `o.orderID, o.OrderDate` : kolom orderID dan orderDate dari tabel o (orders) dipilih untuk ditampilkan.
- `c.companyName, c.contactName, c.Phone` : kolom company Name, ContactName dan Phone dari tabel c (customers) dipilih untuk ditampilkan.
- `e.Lastname, e.Title` : kolom LastName dan Title dari tabel e (employees) dipilih. untuk ditampilkan.
- `FROM orders o customers c, employees e` : untuk memilih dari tabel mana Saja Yang kolamnya dipilih untuk ditampilkan. orders atau o adalah nama tabel Yang dipilih untuk ditampilkan. customers atau c adalah nama tabel Yang dipilih untuk ditampilkan employees atau e adalah nama tabel yang dipilih untuk ditampilkan.
- `WHERE` : kondisi Yang harus difenuhi oleh suatu kolom data agar bisa ditampilkan. 
- `(o.custID = c.customerID)` : data Pada kolom CustID dalam tabel o(orders) harus Sama dengan data Pada kolom customerID dalam table c(customers).
- `AND` untuk menyeleksi dua data atau lebih Pada Perintah WHERE.
- `(o. EmpID=e.Empld)` : data Pada kolom EmpID dalam tabel (orders) harus sama dengan data Pada kolom Empld dalam tabel e(employees).
- `AND` : untuk menyeleksi dua data atau lebih Pada Perintah WHERE-
- `(e.FirstName = "Margaret")` : data Pada kolom Firstivame dalam tabel elemplo harus berisi data "Margaret" agar bisa tampil

Hasilnya jadi barisan data yang sudah memenuhi kondisi WHERE akan tampil. tentama kolam FirstName dari tabel employees Yang isinya "Margaret".

5. Praktek 5
```sql
SELECT c.CustomerID, c.CompanyName, o.OrderID,
    -> o.OrderDate, od.ProductID, p.ProductName,
    -> od.Quantity AS Qty, od.UnitPrice
    -> FROM customers c, orders o, orderdetails od, products p
    -> WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID
    -> AND p.ProductID = od.ProductID
    -> ORDER BY c.CustomerID;
```
![](Assets/praktikum2(5).jpg)
- `SELECT` : untuk memilih kojom mana sata Yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `c.CustomerID, c.CompanyName` : kolom customerID dan companyName dari tabel C (customers) dipilih untuk ditampilkan.
- `o.order ID, o.OrderDate` : kolom orderID dan order Date dari tabel o(orders) dipilih untuk ditampilkan.
- `od.ProductID, od.Quantity, od.UnitPrice` : kolom ProductID, Quantity dan UnitPrice dari tabel od (orderdetails) dipilih uritur ditampilkan.
- `p.ProductName` : kolom ProductName merupakan kolom dari tabel p(Products) Yang dipilih untuk ditampilkan.
- `od.Quantity AS Qty` : kolom Quantity ditampilkan sebagai nama sementaranta Yaitu Qty. AS untuk mengubah nama suatu kolom secara sementara.
- `FROM customers c. orders o, orderdetails od, products p` : Untuk memilih dark tabel mana saja Yang Kolomnya dipilih untuk ditampilkan, Customers atav C adalah nama tabel Yang dipilih untuk ditampilkan orders atau o adalah nama tabel Yang dipilih untuk ditampilkan orderdetails atau ad adalah nama tubel yang dipilih untuk ditampilkan. Products atau P adalah nama tabel Yang dipilih untuk ditampilkan.
- `WHERE` : Kondisi Yang harus dipenuhi oleh suatu kolom data avar bisa ditampilkan (c) (c.customerID = O.CustID) = data Pada kolom customerID dari tabel customers atau a harus sama dengan data Pada kolom custio dari tabel orders atau o.
- `AND` : Untuk menyeleksi dua data atau lebih Pada perintah WHERE.
- `(o. orderID = od.orderID)` : Data Pada kolom orderID dari tabel orders
	atau o harus sama dengan data Pada kolom orderId dari tabel orderdetails atau od.
- `AND` : untuk menyeleksi dua data atau lebih Pada Perintah WHERE.
- `(p.ProductID = od.ProductID)` : data Pada kolom ProductID dari tabel Products atau p harus sama dengan duta Pada kolam ProductID dati tabel orderdetails atau d..
- `OrderBy c.customerID` : untuk mengurut data berdasarkan kolom customerId dan tabel customers.

Hasilnya kolam-kolom data yang tampil adalah data Yang telah memenuhi Fondisi-kondisi Yang ada, dan seluruh isi data tersebut diurut berdasarkan satu kolom Yaitu customerID dari tabel customers.

6. Praktek 6
```sql
 SELECT c.CustomerID, c.CompanyName, o.OrderID AS OrdID, o.OrderDate,
    -> CONCAT(e.LastName, ', ' ,e.FirstName) AS Qyt
    -> FROM customers c, orders o, orderdetails od, products p, employees e
    -> WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID AND p.ProductID=od.ProductID AND e.Empld=o.EmpID
    -> ORDER BY o.OrderID;
```
![](Assets/praktikum2(6).jpg)
- `SELECT` : Untuk memilih kolom mana sata Yang ingin ditampilkan dan dilabuniton Serta dari tabel mara kolom tersebut dipilih.
- `c.customerID, c.company Name` : kolom customerID dan company Name dari tabel c(customers) dipilih untuk ditampilkan.
- `o.OrderID AS ordID, o.OrderDate` : Kolom orderID dan order Date dari tabel o(orders) dipilih untuk ditampilkan. As merupakan Perintah untuk mengubah nama Suatu kolom secara sementara. Dalam hal ini kolom order ID diubah namanya sementara mentual ordID
- `CONCAT (e.Lastname,',', e.FirstName) AS EmployeeName` : CONCAT adalah Perintah untuk mengabungkan beberapa kojom data menjadi satu kolom data. (e. Lastname,',' e.FirstName) merupakan kolom-kolom Yang ingin digabung LastName dan FirstName merupakan kolom dari tabel employee) Yand indin digabung. ('.') merupakan separator atau Pemisah dari kedua kolom Yang ingin digabungkan. As EmployeeName untuk mengubah hasil concat tadi menjadi Employevan (namanya) untuk sementara
- `od.ProductID AS ProdID, Od.Quantity AS Qty`: kolom ProductID dan Quantity dari tabel ad(orderdetails), dipilih untuk ditampilkan, kolom ProductID namanya diubah sementara Jadi ProdID. kolom Quantity namanya diubah Sementara Jadi aty.
- `p.ProductName`: kolom ProductName dari taber P(Products) dipilih untuk ditampilkan. 
- FROM customers c. orders o, orderdetails od, Products P, employees e = untuk memit dari tabel mana saja yang kolomnya dipilih untuk ditampilkan, customers atau C adalah nama tabel Yang dipilih. orders atau o adalah nama tabel Yang difilih order details od adalah nama tabel Yang dipilih. Products atau P adalah nama tabel Yang dipilih, employees atau e adalah nama tabel Yant dipilih.
- `WHERE` : kondisi Yang harus dipenuhi oleh suatu kolom data adar bisa ditampilkan
- `(C-CustomerID = 0. custID)` : data Pada kolom customerID dari tabel c(customers)harus sama dengan data Pada kolom CustID dari tabel o(orders).
- `AND` : untuk menyeleksi dua data atau lebih Pada Perintah WHERE.--
- `(o.OrderID=od-orderID)` : data pada kolom orderID dari tabel (orders) harus Sama dengan data Pada kolom order ID dari tabel od (orderdetails). 
- `AND`: untuk menyeleksi dua data atau lebih Pada Perintah WHERE. 
- `(P.ProductID=od. ProductID)` : Data Pada kolom ProductID dari tabel (ProductID) harus sama dengan data Pada kolom ProductID dari tabel od (orderdetails) 
- `AND`: untuk menyeleksi dua data atau lebih Pada Perintah WHERE. 
- `(e. Empld o. EmpID)` : data Pada kolom EmpID dari tabel e(employees) hans Sama dengan data Pada kolom EmPID dati tabel o(orders). order By o. orderID = untuk mengurut data berdasarkan kolom orderID dari tabel orders.
- `order By o.orderID` : untuk mengurut data berdasarkan kolom orderID dari tabel orders.

Hasilnya kolom LastName dan FirstName dari tabel e(employees) digabung dengan Concat dan hasil kotomnya namanya diubah sementara Jadi EmployeeName.

7. Praktek 7
```sql
CREATE VIEW CustOrdersEmp
    -> AS
    -> SELECT c.CustomerID, c.CompanyName, c.ContactName,
    -> o.OrderID, o.OrderDate, e.Empld, e.LastName, e.FirstName
    -> FROM customers c, orders o, employees e
    -> WHERE c.CustomerID = o.CustID AND o.EmpID = e.Empld;
```
![](Assets/praktikum2(7'1).jpg)
![](Assets/praktikum2(7'2).jpg)
![](Assets/praktikum2(7'3).jpg)
- `CREATE VIEW Custorder Emp` : merupakan tabel virtual Yang dibuat dendan Nama custorderEmp
- `AS SELECT`: untuk memilih kolom-kolom maria Sava Yang ingin dipilih untuk dimasukkan ke tabel virtual.
- `c.CustomerID, c.CompanyName, c.contactName` : kolom customerID, company name dan contactinome dari tabel c(customers) dipilih untuk dimasukkan ke dalam tabel virtual.
- `o.orderID, o. OrderDate` : kolom order ID dan orderDate dari tabel (orders) dipilih untuk dimasukkan ke dalam tabel virtual.
- `e.EmpID, e.Lastname, e.FirstName`: kolom EmpID, LastName, dan FirstName, dari tabel e(employees) dipilih untuk dimasukkan ke dalam tabel virtual.
- `FROM customers c, orders o, employees e`: untuk memilih dari tabel mana saja Yang kolomnya dipilih untuk dimasukkan. customers, orders dan employees merupakan nama tabel yang kolomnya dipilih.
- `WHERE` kondisi yang harus dipenuhi oleh suatu data adar bisa dimasukkan ke dalam tabel virtual.
- `(c.customerID = a custID)` : data Pada kolom customer ID dari tabel c(costumers) harus sama dengan data pada kolom custIO dari tabel (orders) agar bisa dimasukkan.
- `AND` : untuk menyeleksi dua data atau lebih Pada WHERE.
- `(o. EmpID = e.EmpID)` : data Pada kolom EmPID dari tabel ocorders) harus Sama dengan data Pada kolom EmPID dari tabel e(employees) agar bisa dimasukkan.

Hasilnya sebuah Tabel virtual telah dibuat dengan nama custorder Emi Yang berisi kolom-kolom dari 3 Tabel customers, orders, employees dan telah memenuhi semua kondisi.

8. Praktek 8
```sql
 CREATE VIEW odproducts
    -> AS
    -> SELECT od.OrderID, od.ProductID, p.ProductName,
    -> od.Quantity, od.UnitPrice
    -> FROM orderdetails od, products p
    -> WHERE p.ProductID = od.ProductID;
```
![](Assets/praktikum2(8'1).jpg)
![](Assets/praktikum2(8'2).jpg)
![](Assets/praktikum2(8'3).jpg)

- `CREATE VIEW odProducts` : untuk membuat tabel virtual dengan nama odproducts. 
- `AS SELECT` : untuk memilih kolom-kolom mana saja Yang ingin dipilih untuk dimasukkan ke tabel virtual.
- `od.orderID, od.ProductID, od.UnitPrice, od.Quantity` : kolom orderID, ProductID, unit Price dan Quantity dari tabel od (orderdetails) dipilih untuk dimasukkan. 
- `p.ProductName` : kolom Productivame dari tabel P(Products) dipilih untuk dimasukkan. 
- `FROM orderdetails od.Products p` : untuk memilih dari tabel mana saja yang kolomnya dipilih untuk dimasukkan. orderdetails dan Products adalah nama tabel Yang dipilih.
- `WHERE` : Kondisi Yang harus dipenuhi oleh suatu data agar bisa dimasukkan ke dalam tabel virtual.
- (ProductID = od. ProductID) : data Pada kolom productID dari tabel P(Products) hatu sama dengan kolom ProductID dari tabel od (orderdetails). a bisa dimasukan 

Hasilnya Tabel virtual yang bermama odproducts Yang terbuat dari kolam dalam
2 Tabel ordendetails dan products.

9. Praktek 9
```sql
 SELECT c.CustomerID, c.CompanyName, o.OrderID, od.ProductID, ROUND(od.UnitPrice, 2) AS UnitPrice, od.Quantity
    -> FROM customers c, orders o, orderdetails od
    -> WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID
    -> ORDER BY c.CustomerID;
```
![](Assets/praktikum2(9).jpg)
- `SELECT` : untuk memilih Kolom mana saja Yang ingin ditampilkan dan dihitung.
- `c. customerID, c.CompanyName` : kolom customerID dan company Name dari tabel c(customers) dipilih untuk ditampilkan. 
- `o.orderID` : Kolom orderID dari tabel o (orders) dipilih untuk ditampilkan. 
- `od.ProductID, od.unitPrice, od.quantity, od.Discount` = kolom ProductID, unit Price, Quan dan Discount dari tabel od (orderdetails) dipilih untuk ditampilkan dan dibulatkan. 
- `ROUND (od.unitprice, 2)` : untuk membulatkan bilangan dari kolom unitPrice Sampai Jumlah digit tertentu, sesuai dengan Pilihan, yang dibuat Yaitu 2.
- `ROUND (CC1-od. Discount) od unitprice #ad. Quantity), 2) AS Jumlah`: untuk membulatkan bilangan dari kolom hasil dari (1 diurant kolom discount lalu dikali unitprice dan kali Quantity) sampai jumlah digit Yaitu 2. As Jumlah untuk menubah kolom. hasil tersebut noma sementaranya Jadi Jumlah 
- `WHERE` : kondisi yang harus dipenuhi oleh suatu data alar bisa ditampilkan. 
- `(C.customer ID = o.cust ID)` : data Pada kolam customerID. dari tabel c(customers) harus sama dengan data Poda kolom custID dari tabel o(orders). AND untuk menyeleksi dua data atau lebih Pada kondisi WHERE.
- `FROM customers c, orders o, orderdetails od` : untuk memilih dari tabel mana Saja yang kolamnya dipilih untuls ditampilkan dan dibulatkan. customer orders, orderdetails merupakan nama-nama tabel Yang dipilih.
- `WHERE` : kondisi yang harus dipenuhi oleh suatu data alar bisa ditampilkan
- `(o.OrderID = od.OrderID)` : data pada kolom orderID dari tabel o(orders) hous
	Sama dengan data Pada kolom OrderID dari tabel od (orderdetails).
- `ORDER BY c.customerID` : untuk mengurut data berdasarkan kolom customer
	dari tabel (customers).

Hasil akan tampil hasil Pembulatan dari kolom-kolom Yang telah memenuhi kondisi dari WHERE.

10. Praktek 10
```sql
 SELECT c.CustomerID, c.CompanyName, ROUND(SUM((1-od.discount)*od.UnitPrice*od.Quantity),2) AS TotalJumlah
    -> FROM customers c, orders o, orderdetails od WHERE c.CustomerID=o.CustID AND o.OrderID=od.OrderID
    -> GROUP BY c.CustomerID, c.CompanyName ORDER BY c.CustomerID;
```
![](Assets/praktikum2(10).jpg)
- `SELECT` : untuk memilih kolom mana saja yang ingin ditampilkan dan dibulatkan
- `c.CustomerID, c.CompanyName` : kolom customerID dan companyName dari tabel c(customers) dipilih untuk ditampilkan.
- `ROUND (SUM((1-od.discount)* od.UnitPrice * od.quantity), 2) As Total Jumlah` : untuk membulatkan hasil sum dari ((1 dikurang kolom Discount) dikali unitPrice Kali Quantity) sampai 2 digit.Dan nama kolom hasilnya diubah sementara Jadi TotalJumlah.
- `FROM Customers c, orders o, orderdetails od` : untuk memilih dari tabel mana saja Yang kolomnya dipilih untuk ditampilkan dan dibulatkan. customers, orders dan orderdetails, adalah nama tabel yang dipilih.
- `WHERE` : kondisi Yang harus dipenuhi oleh suatu data adar bisa ditampilkan.
- `(c.customerID = o.custID)` : data Pada kolom customerID dari tabel c(customers) harus sama dengan data Pada kolom CustID dari tabel o (orders).
- `AND` : untuk menyeleksi dua data atau lebih rada kondisi WHERE. 
- `(o.orderID)=od.orderID)` : data Pada kolom orderID dari tabel o (orders) harus
	sama dengan data pada kolom orderID dari tabel od(orderdetails). 
- `GROUP BY c.customerID, c.CompanyName` : untuk mengelompokkan data sesuai dengan kolom customerID dan companyName dari tabel c(customers).
- `ORDER BY c.customerID` : untuk mengurut data berdasarkan kolom CustomerID dori tabel c(customers)

Hasilnya Jadi, kolom yang dikelompokkan adalah customerID dan company Name dan tampilannya diurutkan berdasarkan kolom customerID.
Data

Penilaian:

| No  | Nama               | Nilai | Tugas                               |
| --- | ------------------ | ----- | ----------------------------------- |
| 1.  | Condrado           | 3     | Membuat Catatan dan Praktek dan PPT |
| 2.  | Adrian             | 3     | Membuat Soal                        |
| 3.  | Fahri Ilham        | 2     | Membantu membuat soal               |
| 4.  | Muh. Nabil Maulana | 2     | Mencari Soal                        |
| 5.  | Yeremia Tasik      | 2     | Beli Gorengan                       |
