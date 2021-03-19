
Soal 1. Tampilkan semua Customer yang tinggal di Negara German atau Mexico
SELECT * FROM Customers;
WHERE Country='Mexico' OR Country='Germany'

Soal 2. Tampilkan semua Product yang Harganya kurang dari 15
SELECT * FROM Products
WHERE Price < 15

Soal 3. Tampilkan semua Product yang range Harganya dari 10 - 30
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 30;

Soal 4. Tampilkan semua Customer yang tinggal di Europa
SELECT * FROM Customers
WHERE Address LIKE '%Europe%'

Soal 5. Hitung jumlah total Order Customer dengan Nama Rattlesnake Canyon Grocery
SELECT COUNT (OrderID)
FROM Customers
INNER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID
WHERE CustomerName = 'Rattlesnake Canyon Grocery'

Soal 6. Tamplikan Orderan dari Federal Shipping dengan OrderDate kurang dari bulan 12
SELECT * 
FROM Orders AS O 
INNER JOIN Shippers AS S
ON O.ShipperID = S.ShipperID
WHERE ShipperName = 'Federal Shipping' 
AND OrderDate NOT BETWEEN '1996-12-01' AND '1996-12-31'


Soal 7. Tampilkan Semua Nama Barang yang dibeli oleh Save-a-lot Markets
SELECT CustomerName,ProductName
FROM Customers AS C
INNER JOIN Orders AS O
ON C.CustomerID = O.CustomerID
INNER JOIN OrderDetails AS OD
ON OD.OrderID = O.OrderID
INNER JOIN Products AS P
ON P.ProductID = OD.ProductID
WHERE Customername = 'Save-a-lot Markets'


Soal 8. Hitung total keseluruhan barang yang dibeli oleh B's Beverages
SELECT  CustomerName, SUM (Quantity) AS ItemQuantity
FROM Customers AS C
INNER JOIN Orders AS O
ON C.CustomerID = O.CustomerID
INNER JOIN OrderDetails AS OD
ON OD.OrderID = O.OrderID
INNER JOIN Products AS P
ON P.ProductID = OD.ProductID
WHERE CustomerName = "B's Beverages"


Soal 9. Hitung total pengiriman yang dilakukan oleh United Package pada bulan 8
SELECT ShipperName, COUNT (ShipperName) AS AugustDeliveryCount
FROM Shippers
INNER JOIN Orders
ON Shippers.ShipperID = Orders.ShipperID
WHERE ShipperName = 'United Package'
AND OrderDate BETWEEN '1996-08-01' AND '1996-08-31'

Soal 10. Tampilkan Product dengan Category Beverages
SELECT ProductName, CategoryName, Description
FROM Products
INNER JOIN Categories
ON Products.CategoryID = Categories.CategoryID
WHERE CategoryName = 'Beverages'



