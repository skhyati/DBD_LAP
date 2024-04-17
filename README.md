**creating table**
table 1
create table vehicle(
vid int primary key,
vname varchar(20),
price int,
descp varchar(20));
table 2
create table customer(
custid int primary key auto_increment,
cname varchar(20),
caddres varchar(20));

table 3
create table salesman ( sid int primary key,
sname varchar(20),
saddres varchar(20));

table 4 
create table cust_vehicle(
custid int,
vid int,
sid int,
buy_price int,
constraint fk_cid foreign key (custid) references 
customer (custid) on delete set null
on update cascade,
constraint fk_vid foreign key (vid) references 
vehicle (vid) on delete set null
on update cascade);  

table 5
create table category(cid int primary key,
cname varchar (20),
descp varchar(50));

table 6
create table product(pid int primary key,
pname varchar (40),
price float(9,2),
qty int,
cid int,
sid int,
constraint fk_caid foreign key (cid) references category (cid),
constraint fk_said foreign key (sid) references salesman (sid));

 
**insert date**
table 1
insert into vehicle(vid,vname,price,descp) values
(1,'activa',80000,'white,black'),
(2,'santro',800000,'white only'),
(3,'motor bike',100000,'all');

table 2
insert into customer(cname,caddres) VALUES
('GANESH','PUNE'),
('PANKAJ','MUMBAI');

 table 3
 insert into salesman values (10,'Rajesh','Mumbai'),
(11,'Seema','Pune'),
(13,'Rakhi','Pune');

table 4
insert into cust_vehicle(custid,vid,sid,buy_price) values (1,1,10,75000),
(1,2,10,790000),
(2,3,11,80000),
(3,3,11,75000),
(3,2,10,8000000);

table 5
insert into product values(01,'maggie',20,4,100,10),
(02,'parle Biscuit',30,5,101,13),(03,'UNIBIC',60,15,101,13),(04,'yuppy',34,7,100,11),
(05,'Britannia',40,33,101,10),(06,'Lays',60,12,102,10),(07,'Funyon',68,12,102,13);

table 6
insert into category values(100,'noddles','yummy'),
(101,'biscuits','snacks'),(102,'chips','salty');
