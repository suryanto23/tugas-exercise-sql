<br>
Soal 1. Tampilkan semua Customer yang tinggal di Negara German atau Mexico<br>
SELECT * FROM Customers<br>
WHERE Country='Mexico' OR Country='Germany'<br>
<br>
<br>
Soal 2. Tampilkan semua Product yang Harganya kurang dari 15<br>
SELECT * FROM Products<br>
WHERE Price < 15<br>
<br>
<br>
Soal 3. Tampilkan semua Product yang range Harganya dari 10 - 30<br>
SELECT * FROM Products<br>
WHERE Price BETWEEN 10 AND 30<br>
<br>
<br>
Soal 4. Tampilkan semua Customer yang tinggal di Europa<br>
SELECT * FROM Customers<br>
WHERE Address LIKE '%Europe%'<br>
<br>
<br>
Soal 5. Hitung jumlah total Order Customer dengan Nama Rattlesnake Canyon Grocery<br>
SELECT COUNT (OrderID)<br>
FROM Customers<br>
INNER JOIN Orders<br>
ON Customers.CustomerID = Orders.CustomerID<br>
WHERE CustomerName = 'Rattlesnake Canyon Grocery'<br>
<br>
<br>
Soal 6. Tamplikan Orderan dari Federal Shipping dengan OrderDate kurang dari bulan 12<br>
SELECT *<br>
FROM Orders AS O <br>
INNER JOIN Shippers AS S<br>
ON O.ShipperID = S.ShipperID<br>
WHERE ShipperName = 'Federal Shipping'<br>
AND OrderDate NOT BETWEEN '1996-12-01' AND '1996-12-31'<br>
<br>
<br>
Soal 7. Tampilkan Semua Nama Barang yang dibeli oleh Save-a-lot Markets<br>
SELECT CustomerName,ProductName<br>
FROM Customers AS C<br>
INNER JOIN Orders AS O<br>
ON C.CustomerID = O.CustomerID<br>
INNER JOIN OrderDetails AS OD<br>
ON OD.OrderID = O.OrderID<br>
INNER JOIN Products AS P<br>
ON P.ProductID = OD.ProductID<br>
WHERE Customername = 'Save-a-lot Markets'<br>
<br>
<br>
Soal 8. Hitung total keseluruhan barang yang dibeli oleh B's Beverages<br>
SELECT  CustomerName, SUM (Quantity) AS ItemQuantity<br>
FROM Customers AS C<br>
INNER JOIN Orders AS O<br>
ON C.CustomerID = O.CustomerID<br>
INNER JOIN OrderDetails AS OD<br>
ON OD.OrderID = O.OrderID<br>
INNER JOIN Products AS P<br>
ON P.ProductID = OD.ProductID<br>
WHERE CustomerName = "B's Beverages"<br>
<br>
<br>
Soal 9. Hitung total pengiriman yang dilakukan oleh United Package pada bulan 8<br>
SELECT ShipperName, COUNT (ShipperName) AS AugustDeliveryCount<br>
FROM Shippers<br>
INNER JOIN Orders<br>
ON Shippers.ShipperID = Orders.ShipperID<br>
WHERE ShipperName = 'United Package'<br>
AND OrderDate BETWEEN '1996-08-01' AND '1996-08-31'<br>
<br>
<br>
Soal 10. Tampilkan Product dengan Category Beverages<br>
SELECT ProductName, CategoryName, Description<br>
FROM Products<br>
INNER JOIN Categories<br>
ON Products.CategoryID = Categories.CategoryID<br>
WHERE CategoryName = 'Beverages'<br>
<br>


