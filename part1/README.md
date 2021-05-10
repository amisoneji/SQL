
**1.Write a SQL statement to prepare a list with salesman name, customer name and their cities for the salesmen and customer who belongs to the same city.**
 

mysql> select * from salesman inner join customer on salesman.city=customer.city;

[image](https://user-images.githubusercontent.com/71078788/117627165-82f0e180-b195-11eb-9c62-4f5abb357266.png)


**2. Write a SQL statement to make a list with order no, purchase amount, customer name and their cities for those orders which order amount between 500 and 2000**


mysql> select o.ord_no,o.purch_amt,o.customer_id,c.city from orders as o inner join customer as c on o.customer_id=c.customer_id where o.purch_amt>=500 and o.purch_amt<=2000;

![image](https://user-images.githubusercontent.com/71078788/117627242-9734de80-b195-11eb-8548-bfb040c497b3.png)


**3. Write a SQL statement to know which salesmen are working for which customer.**


select s.salesman_id,c.customer_id,c.cust_name from salesman as s inner join customer as c on s.salesman_id=c.salesman_id;

![image](https://user-images.githubusercontent.com/71078788/117627290-a4ea6400-b195-11eb-9939-b024c8442af7.png)


**4. Write a SQL statement to find the list of customers who appointed a salesman for their jobs who gets a commission from the company is more than 12%.**


select c.cust_name,s.commission from  customer as c inner join salesman as s on c.salesman_id=s.salesman_id where s.commission>=0.12;

![image](https://user-images.githubusercontent.com/71078788/117627337-b0d62600-b195-11eb-8f1f-0a863023466d.png)

**5. Write a SQL statement to find the list of customers who appointed a salesman for their jobs who does not live in the same city where their customer lives, and gets a commission is above 12%**

select c.cust_name from  customer as c inner join salesman as s on c.salesman_id=s.salesman_id where (c.city!=s.city and s.commission>=0.12);

![image](https://user-images.githubusercontent.com/71078788/117627388-bd5a7e80-b195-11eb-8d73-2ae2018db869.png)

**6. Write a SQL statement to make a list in ascending order for the customer who works either through a salesman or by own.**

select c.cust_name from  customer as c left join salesman as s on c.salesman_id=s.salesman_id order by c.customer_id asc;

![image](https://user-images.githubusercontent.com/71078788/117627435-c9ded700-b195-11eb-80a8-4d9d845aa7f9.png)

**7. Write a SQL statement to make a list in ascending order for the salesmen who works either for one or more customer or not yet join under any of the customers.**

select s.name from salesman as s left join customer as c on s.salesman_id=c.salesman_id order by s.name asc;

![image](https://user-images.githubusercontent.com/71078788/117627469-d400d580-b195-11eb-9184-d46efcd9682a.png)

