# databaseHW1

create database store;

create table  countries (
    code int(10) primary key ,
  name varchar(20)  unique ,
   continent_name varchar(20) not null );

create table users (
    id int  primary key ,
    full_name varchar(20)   ,
    email varchar(255)  not null ,
    gender char(1) check(gender='m' or gender = 'f'),
    date_of_birth varchar(15)  not null ,
    creted_at datetime,
    country_code int
);
create table  orders (
  id int  primary key ,
  user_id VARCHAR(20),
  status VARCHAR(6) check(status='start' or status = 'finish'),
  creted_at datetime,
    foreign key (user_id) references  users(id)
);

create table  order_prouducts (
  order_id int ,
  product_id int,
  quntity int default 0,
    foreign key ( order_id) references  users(id),
    foreign key ( product_id) references  prouducts(id)
);
create table  prouducts (
 id int primary key   ,
  name VARCHAR(10) not null ,
  price int default 0,
  status varchar(10) check(status='valid' or status = 'expired'));


insert into countries values  (9,'rawan','s@s.com','123456');
insert  into users values  ('2','rawanali','rawan@ali.com','f','1998-2-8','2023',111);
insert into  orders values (1,100,'start',2);
insert into  order_prouducts values (2,10,6);
insert into  prouducts values (4,'bayan','2000','valid','1-7-2023');



update  countries set  name='wesam' where code=3;

delete from  prouducts where id=4;
