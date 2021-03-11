


# **Mariadb**

How [Install Mariadb on Linux](https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04-pt/) ?


# Connecting to Mariadb 

 After the installation we can connect with Mariadb through the command line:


```bash
sudo mariadb
```
```sql
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 40
Server version: 10.1.47-MariaDB-0ubuntu0.18.04.1 Ubuntu 18.04
Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.
Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
``` 


## Checking if exists any database

```sql
SHOW DATABASES;

MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
3 rows in set (0.00 sec)
```

## Creating a new database
```sql
CREATE DATABASE TEST;
```
> **Note:**  We can put database name between **``** or not.
```sql
Query OK, 1 row affected (0.00 sec)
```

```sql
MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| TEST               |
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
4 rows in set (0.01 sec)
```
## Referencing the created database

```sql
MariaDB [mysql]> USE TEST;
Database changed
MariaDB [TEST]>
```

## Checking if exists any table on database.
```sql
MariaDB [TEST]> SHOW TABLES;
Empty set (0.00 sec)
```

## Creating a new table on database


```sql
MariaDB [TEST]> DROP TABLE IF EXISTS `Cars`;
Query OK, 0 rows affected, 1 warning (0.00 sec)

MariaDB [TEST]>     CREATE TABLE `Cars` (
        `Make` VARCHAR(50) NULL DEFAULT NULL,
         `Model` VARCHAR(255) NULL DEFAULT NULL,
          `Type` VARCHAR(50) NULL DEFAULT NULL,
         `Origin` VARCHAR(50) NULL DEFAULT NULL,
          `DriveTrain` VARCHAR(50) NULL DEFAULT NULL,
         `Lenght` INT NULL
          )
         COLLATE='latin1_swedish_ci'
        ;
Query OK, 0 rows affected (0.06 sec)
```
> **Note:**  the Collate type can be changed for a necessity. For more information check: [Collation Settings](https://mariadb.com/kb/en/setting-character-sets-and-collations/) 


# Verifying that the table has been created

```SQL
MariaDB [TEST]> SHOW TABLES;
+----------------+
| Tables_in_TEST |
+----------------+
| Cars           |
+----------------+
1 row in set (0.00 sec)
```


## Inserting values ​​in the created table

```SQL
insert into Cars Values('Acura','MDX','SUV','Asia','All',4451);
insert into Cars Values('Acura','RSX Type S 2dr','Sedan','Asia','Front',2778);
insert into Cars Values('Acura','TSX 4dr','Sedan','Asia','Front',3230);
insert into Cars Values('Acura','TL 4dr','Sedan','Asia','Front',3575);
insert into Cars Values('Acura','3.5 RL 4dr','Sedan','Asia','Front',3880);
insert into Cars Values('Acura','3.5 RL w/Navigation 4dr','Sedan','Asia','Front',3893);
insert into Cars Values('Acura','NSX coupe 2dr manual S','Sports','Asia','Rear',3153);
insert into Cars Values('Audi','A4 1.8T 4dr','Sedan','Europe','Front',3252);
insert into Cars Values('Audi','A41.8T convertible 2dr','Sedan','Europe','Front',3638);
insert into Cars Values('Audi','A4 3.0 4dr','Sedan','Europe','Front',3462);
insert into Cars Values('Audi','A4 3.0 Quattro 4dr manual','Sedan','Europe','All',3583);
insert into Cars Values('Audi','A4 3.0 Quattro 4dr auto','Sedan','Europe','All',3627);
insert into Cars Values('Audi','A6 3.0 4dr','Sedan','Europe','Front',3561);
insert into Cars Values('Audi','A6 3.0 Quattro 4dr','Sedan','Europe','All',3880);
insert into Cars Values('Audi','A4 3.0 convertible 2dr','Sedan','Europe','Front',3814);
insert into Cars Values('Audi','A4 3.0 Quattro convertible 2dr','Sedan','Europe','All',4013);
insert into Cars Values('Audi','A6 2.7 Turbo Quattro 4dr','Sedan','Europe','All',3836);
insert into Cars Values('Audi','A6 4.2 Quattro 4dr','Sedan','Europe','All',4024);
insert into Cars Values('Audi','A8 L Quattro 4dr','Sedan','Europe','All',4399);
insert into Cars Values('Audi','S4 Quattro 4dr','Sedan','Europe','All',3825);
insert into Cars Values('Audi','RS 6 4dr','Sports','Europe','Front',4024);
insert into Cars Values('Audi','TT 1.8 convertible 2dr (coupe)','Sports','Europe','Front',3131);
insert into Cars Values('Audi','TT 1.8 Quattro 2dr (convertible)','Sports','Europe','All',2921);
insert into Cars Values('Audi','TT 3.2 coupe 2dr (convertible)','Sports','Europe','All',3351);
insert into Cars Values('Audi','A6 3.0 Avant Quattro','Wagon','Europe','All',4035);
insert into Cars Values('Audi','S4 Avant Quattro','Wagon','Europe','All',3936);
insert into Cars Values('BMW','X3 3.0i','SUV','Europe','All',4023);
insert into Cars Values('BMW','X5 4.4i','SUV','Europe','All',4824);
insert into Cars Values('BMW','325i 4dr','Sedan','Europe','Rear',3219);
insert into Cars Values('BMW','325Ci 2dr','Sedan','Europe','Rear',3197);
insert into Cars Values('BMW','325Ci convertible 2dr','Sedan','Europe','Rear',3560);
insert into Cars Values('BMW','325xi 4dr','Sedan','Europe','All',3461);
insert into Cars Values('BMW','330i 4dr','Sedan','Europe','Rear',3285);
insert into Cars Values('BMW','330Ci 2dr','Sedan','Europe','Rear',3285);
insert into Cars Values('BMW','330xi 4dr','Sedan','Europe','All',3483);
insert into Cars Values('BMW','525i 4dr','Sedan','Europe','Rear',3428);
insert into Cars Values('BMW','330Ci convertible 2dr','Sedan','Europe','Rear',3616);
insert into Cars Values('BMW','530i 4dr','Sedan','Europe','Rear',3472);
insert into Cars Values('BMW','545iA 4dr','Sedan','Europe','Rear',3814);
insert into Cars Values('BMW','745i 4dr','Sedan','Europe','Rear',4376);
insert into Cars Values('BMW','745Li 4dr','Sedan','Europe','Rear',4464);
insert into Cars Values('BMW','M3 coupe 2dr','Sports','Europe','Rear',3415);
insert into Cars Values('BMW','M3 convertible 2dr','Sports','Europe','Rear',3781);
insert into Cars Values('BMW','Z4 convertible 2.5i 2dr','Sports','Europe','Rear',2932);
insert into Cars Values('BMW','Z4 convertible 3.0i 2dr','Sports','Europe','Rear',2998);
insert into Cars Values('BMW','325xi Sport','Wagon','Europe','All',3594);
insert into Cars Values('Buick','Rainier','SUV','USA','All',4600);
insert into Cars Values('Buick','Rendezvous CX','SUV','USA','Front',4024);
insert into Cars Values('Buick','Century Custom 4dr','Sedan','USA','Front',3353);
insert into Cars Values('Buick','LeSabre Custom 4dr','Sedan','USA','Front',3567);
insert into Cars Values('Buick','Regal LS 4dr','Sedan','USA','Front',3461);
insert into Cars Values('Buick','Regal GS 4dr','Sedan','USA','Front',3536);
insert into Cars Values('Buick','LeSabre Limited 4dr','Sedan','USA','Front',3591);
insert into Cars Values('Buick','Park Avenue 4dr','Sedan','USA','Front',3778);
insert into Cars Values('Buick','Park Avenue Ultra 4dr','Sedan','USA','Front',3909);
insert into Cars Values('Cadillac','Escalade','SUV','USA','Front',5367);
insert into Cars Values('Cadillac','SRX V8','SUV','USA','Front',4302);
insert into Cars Values('Cadillac','CTS VVT 4dr','Sedan','USA','Rear',3694);
insert into Cars Values('Cadillac','Deville 4dr','Sedan','USA','Front',3984);
insert into Cars Values('Cadillac','Deville DTS 4dr','Sedan','USA','Front',4044);
insert into Cars Values('Cadillac','Seville SLS 4dr','Sedan','USA','Front',3992);
insert into Cars Values('Cadillac','XLR convertible 2dr','Sports','USA','Rear',3647);
insert into Cars Values('Cadillac','Escalade EXT','Truck','USA','All',5879);
insert into Cars Values('Chevrolet','Suburban 1500 LT','SUV','USA','Front',4947);
insert into Cars Values('Chevrolet','Tahoe LT','SUV','USA','All',5050);
insert into Cars Values('Chevrolet','TrailBlazer LT','SUV','USA','Front',4425);
insert into Cars Values('Chevrolet','Tracker','SUV','USA','Front',2866);
insert into Cars Values('Chevrolet','Aveo 4dr','Sedan','USA','Front',2370);
insert into Cars Values('Chevrolet','Aveo LS 4dr hatch','Sedan','USA','Front',2348);
insert into Cars Values('Chevrolet','Cavalier 2dr','Sedan','USA','Front',2617);
insert into Cars Values('Chevrolet','Cavalier 4dr','Sedan','USA','Front',2676);
insert into Cars Values('Chevrolet','Cavalier LS 2dr','Sedan','USA','Front',2617);
insert into Cars Values('Chevrolet','Impala 4dr','Sedan','USA','Front',3465);
insert into Cars Values('Chevrolet','Malibu 4dr','Sedan','USA','Front',3174);
insert into Cars Values('Chevrolet','Malibu LS 4dr','Sedan','USA','Front',3297);
insert into Cars Values('Chevrolet','Monte Carlo LS 2dr','Sedan','USA','Front',3340);
insert into Cars Values('Chevrolet','Impala LS 4dr','Sedan','USA','Front',3476);
insert into Cars Values('Chevrolet','Impala SS 4dr','Sedan','USA','Front',3606);
insert into Cars Values('Chevrolet','Malibu LT 4dr','Sedan','USA','Front',3315);
insert into Cars Values('Chevrolet','Monte Carlo SS 2dr','Sedan','USA','Front',3434);
insert into Cars Values('Chevrolet','Astro','Sedan','USA','All',4605);
insert into Cars Values('Chevrolet','Venture LS','Sedan','USA','Front',3699);
insert into Cars Values('Chevrolet','Corvette 2dr','Sports','USA','Rear',3246);
insert into Cars Values('Chevrolet','Corvette convertible 2dr','Sports','USA','Rear',3248);
insert into Cars Values('Chevrolet','Avalanche 1500','Truck','USA','All',5678);
insert into Cars Values('Chevrolet','Colorado Z85','Truck','USA','All',3623);
insert into Cars Values('Chevrolet','Silverado 1500 Regular Cab','Truck','USA','Rear',4142);
insert into Cars Values('Chevrolet','Silverado SS','Truck','USA','All',4804);
insert into Cars Values('Chevrolet','SSR','Truck','USA','Rear',4760);
insert into Cars Values('Chevrolet','Malibu Maxx LS','Wagon','USA','Front',3458);
insert into Cars Values('Chrysler','PT Cruiser 4dr','Sedan','USA','Front',3101);
insert into Cars Values('Chrysler','PT Cruiser Limited 4dr','Sedan','USA','Front',3105);
insert into Cars Values('Chrysler','Sebring 4dr','Sedan','USA','Front',3173);
insert into Cars Values('Chrysler','Sebring Touring 4dr','Sedan','USA','Front',3222);
insert into Cars Values('Chrysler','300M 4dr','Sedan','USA','Front',3581);
insert into Cars Values('Chrysler','Concorde LX 4dr','Sedan','USA','Front',3479);
insert into Cars Values('Chrysler','Concorde LXi 4dr','Sedan','USA','Front',3548);
insert into Cars Values('Chrysler','PT Cruiser GT 4dr','Sedan','USA','Front',3217);
insert into Cars Values('Chrysler','Sebring convertible 2dr','Sedan','USA','Front',3357);
insert into Cars Values('Chrysler','300M Special Edition 4dr','Sedan','USA','Front',3650);
insert into Cars Values('Chrysler','Sebring Limited convertible 2dr','Sedan','USA','Front',3448);
insert into Cars Values('Chrysler','Town and Country LX','Sedan','USA','Front',4068);
insert into Cars Values('Chrysler','Town and Country Limited','Sedan','USA','Front',4331);
insert into Cars Values('Chrysler','Crossfire 2dr','Sports','USA','Rear',3060);
insert into Cars Values('Chrysler','Pacifica','Wagon','USA','Rear',4675);
insert into Cars Values('Dodge','Durango SLT','SUV','USA','All',4987);
insert into Cars Values('Dodge','Neon SE 4dr','Sedan','USA','Front',2581);
insert into Cars Values('Dodge','Neon SXT 4dr','Sedan','USA','Front',2626);
insert into Cars Values('Dodge','Intrepid SE 4dr','Sedan','USA','Front',3469);
insert into Cars Values('Dodge','Stratus SXT 4dr','Sedan','USA','Front',3182);
insert into Cars Values('Dodge','Stratus SE 4dr','Sedan','USA','Front',3175);
insert into Cars Values('Dodge','Intrepid ES 4dr','Sedan','USA','Front',3487);
insert into Cars Values('Dodge','Caravan SE','Sedan','USA','Front',3862);
insert into Cars Values('Dodge','Grand Caravan SXT','Sedan','USA','All',4440);
insert into Cars Values('Dodge','Viper SRT-10 convertible 2dr','Sports','USA','Rear',3410);
insert into Cars Values('Dodge','Dakota Regular Cab','Truck','USA','Rear',3714);
insert into Cars Values('Dodge','Dakota Club Cab','Truck','USA','Rear',3829);
insert into Cars Values('Dodge','Ram 1500 Regular Cab ST','Truck','USA','Rear',4542);
insert into Cars Values('Ford','Excursion 6.8 XLT','SUV','USA','All',7190);
insert into Cars Values('Ford','Expedition 4.6 XLT','SUV','USA','Front',5000);
insert into Cars Values('Ford','Explorer XLT V6','SUV','USA','All',4463);
insert into Cars Values('Ford','Escape XLS','SUV','USA','All',3346);
insert into Cars Values('Ford','Focus ZX3 2dr hatch','Sedan','USA','Front',2612);
insert into Cars Values('Ford','Focus LX 4dr','Sedan','USA','Front',2606);
insert into Cars Values('Ford','Focus SE 4dr','Sedan','USA','Front',2606);
insert into Cars Values('Ford','Focus ZX5 5dr','Sedan','USA','Front',2691);
insert into Cars Values('Ford','Focus SVT 2dr','Sedan','USA','Front',2750);
insert into Cars Values('Ford','Taurus LX 4dr','Sedan','USA','Front',3306);
insert into Cars Values('Ford','Taurus SES Duratec 4dr','Sedan','USA','Front',3313);
insert into Cars Values('Ford','Crown Victoria 4dr','Sedan','USA','Rear',4057);
insert into Cars Values('Ford','Crown Victoria LX 4dr','Sedan','USA','Rear',4057);
insert into Cars Values('Ford','Crown Victoria LX Sport 4dr','Sedan','USA','Rear',4057);
insert into Cars Values('Ford','Freestar SE','Sedan','USA','Front',4275);
insert into Cars Values('Ford','Mustang 2dr (convertible)','Sports','USA','Rear',3290);
insert into Cars Values('Ford','Mustang GT Premium convertible 2dr','Sports','USA','Rear',3347);
insert into Cars Values('Ford','Thunderbird Deluxe convert w/hardtop 2d','Sports','USA','Front',3780);
insert into Cars Values('Ford','F-150 Regular Cab XL','Truck','USA','Rear',4788);
insert into Cars Values('Ford','F-150 Supercab Lariat','Truck','USA','All',5464);
insert into Cars Values('Ford','Ranger 2.3 XL Regular Cab','Truck','USA','Rear',3028);
insert into Cars Values('Ford','Focus ZTW','Wagon','USA','Front',2702);
insert into Cars Values('Ford','Taurus SE','Wagon','USA','Front',3497);
insert into Cars Values('GMC','Envoy XUV SLE','SUV','USA','Front',4945);
insert into Cars Values('GMC','Yukon 1500 SLE','SUV','USA','Front',5042);
insert into Cars Values('GMC','Yukon XL 2500 SLT','SUV','USA','All',6133);
insert into Cars Values('GMC','Safari SLE','Sedan','USA','Rear',4309);
insert into Cars Values('GMC','Canyon Z85 SL Regular Cab','Truck','USA','Rear',3351);
insert into Cars Values('GMC','Sierra Extended Cab 1500','Truck','USA','Rear',4548);
insert into Cars Values('GMC','Sierra HD 2500','Truck','USA','All',5440);
insert into Cars Values('GMC','Sonoma Crew Cab','Truck','USA','All',4083);
insert into Cars Values('Honda','Civic Hybrid 4dr manual (gas/electric)','Hybrid','Asia','Front',2732);
insert into Cars Values('Honda','Insight 2dr (gas/electric)','Hybrid','Asia','Front',1850);
insert into Cars Values('Honda','Pilot LX','SUV','Asia','All',4387);
insert into Cars Values('Honda','CR-V LX','SUV','Asia','All',3258);
insert into Cars Values('Honda','Element LX','SUV','Asia','All',3468);
insert into Cars Values('Honda','Civic DX 2dr','Sedan','Asia','Front',2432);
insert into Cars Values('Honda','Civic HX 2dr','Sedan','Asia','Front',2500);
insert into Cars Values('Honda','Civic LX 4dr','Sedan','Asia','Front',2513);
insert into Cars Values('Honda','Accord LX 2dr','Sedan','Asia','Front',2994);
insert into Cars Values('Honda','Accord EX 2dr','Sedan','Asia','Front',3047);
insert into Cars Values('Honda','Civic EX 4dr','Sedan','Asia','Front',2601);
insert into Cars Values('Honda','Civic Si 2dr hatch','Sedan','Asia','Front',2782);
insert into Cars Values('Honda','Accord LX V6 4dr','Sedan','Asia','Front',3349);
insert into Cars Values('Honda','Accord EX V6 2dr','Sedan','Asia','Front',3294);
insert into Cars Values('Honda','Odyssey LX','Sedan','Asia','Front',4310);
insert into Cars Values('Honda','Odyssey EX','Sedan','Asia','Front',4365);
insert into Cars Values('Honda','S2000 convertible 2dr','Sports','Asia','Rear',2835);
insert into Cars Values('Hummer','H2','SUV','USA','All',6400);
insert into Cars Values('Hyundai','Santa Fe GLS','SUV','Asia','Front',3549);
insert into Cars Values('Hyundai','Accent 2dr hatch','Sedan','Asia','Front',2255);
insert into Cars Values('Hyundai','Accent GL 4dr','Sedan','Asia','Front',2290);
insert into Cars Values('Hyundai','Accent GT 2dr hatch','Sedan','Asia','Front',2339);
insert into Cars Values('Hyundai','Elantra GLS 4dr','Sedan','Asia','Front',2635);
insert into Cars Values('Hyundai','Elantra GT 4dr','Sedan','Asia','Front',2635);
insert into Cars Values('Hyundai','Elantra GT 4dr hatch','Sedan','Asia','Front',2698);
insert into Cars Values('Hyundai','Sonata GLS 4dr','Sedan','Asia','Front',3217);
insert into Cars Values('Hyundai','Sonata LX 4dr','Sedan','Asia','Front',3217);
insert into Cars Values('Hyundai','XG350 4dr','Sedan','Asia','Front',3651);
insert into Cars Values('Hyundai','XG350 L 4dr','Sedan','Asia','Front',3651);
insert into Cars Values('Hyundai','Tiburon GT V6 2dr','Sports','Asia','Front',3023);
insert into Cars Values('Infiniti','G35 4dr','Sedan','Asia','Rear',3336);
insert into Cars Values('Infiniti','G35 Sport Coupe 2dr','Sedan','Asia','Rear',3416);
insert into Cars Values('Infiniti','G35 4dr','Sedan','Asia','All',3677);
insert into Cars Values('Infiniti','I35 4dr','Sedan','Asia','Front',3306);
insert into Cars Values('Infiniti','M45 4dr','Sedan','Asia','Rear',3851);
insert into Cars Values('Infiniti','Q45 Luxury 4dr','Sedan','Asia','Rear',3977);
insert into Cars Values('Infiniti','FX35','Wagon','Asia','Rear',4056);
insert into Cars Values('Infiniti','FX45','Wagon','Asia','All',4309);
insert into Cars Values('Isuzu','Ascender S','SUV','Asia','All',4967);
insert into Cars Values('Isuzu','Rodeo S','SUV','Asia','Front',3836);
insert into Cars Values('Jaguar','X-Type 2.5 4dr','Sedan','Europe','All',3428);
insert into Cars Values('Jaguar','X-Type 3.0 4dr','Sedan','Europe','All',3516);
insert into Cars Values('Jaguar','S-Type 3.0 4dr','Sedan','Europe','Rear',3777);
insert into Cars Values('Jaguar','S-Type 4.2 4dr','Sedan','Europe','Rear',3874);
insert into Cars Values('Jaguar','S-Type R 4dr','Sedan','Europe','Rear',4046);
insert into Cars Values('Jaguar','Vanden Plas 4dr','Sedan','Europe','Rear',3803);
insert into Cars Values('Jaguar','XJ8 4dr','Sedan','Europe','Rear',3803);
insert into Cars Values('Jaguar','XJR 4dr','Sedan','Europe','Rear',3948);
insert into Cars Values('Jaguar','XK8 coupe 2dr','Sports','Europe','Rear',3779);
insert into Cars Values('Jaguar','XK8 convertible 2dr','Sports','Europe','Rear',3980);
insert into Cars Values('Jaguar','XKR coupe 2dr','Sports','Europe','Rear',3865);
insert into Cars Values('Jaguar','XKR convertible 2dr','Sports','Europe','Rear',4042);
insert into Cars Values('Jeep','Grand Cherokee Laredo','SUV','USA','Front',3790);
insert into Cars Values('Jeep','Liberty Sport','SUV','USA','All',3826);
insert into Cars Values('Jeep','Wrangler Sahara convertible 2dr','SUV','USA','All',3575);
insert into Cars Values('Kia','Sorento LX','SUV','Asia','Front',4112);
insert into Cars Values('Kia','Optima LX 4dr','Sedan','Asia','Front',3281);
insert into Cars Values('Kia','Rio 4dr manual','Sedan','Asia','Front',2403);
insert into Cars Values('Kia','Rio 4dr auto','Sedan','Asia','Front',2458);
insert into Cars Values('Kia','Spectra 4dr','Sedan','Asia','Front',2661);
insert into Cars Values('Kia','Spectra GS 4dr hatch','Sedan','Asia','Front',2686);
insert into Cars Values('Kia','Spectra GSX 4dr hatch','Sedan','Asia','Front',2697);
insert into Cars Values('Kia','Optima LX V6 4dr','Sedan','Asia','Front',3279);
insert into Cars Values('Kia','Amanti 4dr','Sedan','Asia','Front',4021);
insert into Cars Values('Kia','Sedona LX','Sedan','Asia','Front',4802);
insert into Cars Values('Kia','Rio Cinco','Wagon','Asia','Front',2447);
insert into Cars Values('Land Rover','Range Rover HSE','SUV','Europe','All',5379);
insert into Cars Values('Land Rover','Discovery SE','SUV','Europe','All',4576);
insert into Cars Values('Land Rover','Freelander SE','SUV','Europe','All',3577);
insert into Cars Values('Lexus','GX 470','SUV','Asia','All',4740);
insert into Cars Values('Lexus','LX 470','SUV','Asia','All',5590);
insert into Cars Values('Lexus','RX 330','SUV','Asia','All',4065);
insert into Cars Values('Lexus','ES 330 4dr','Sedan','Asia','Front',3460);
insert into Cars Values('Lexus','IS 300 4dr manual','Sedan','Asia','Rear',3255);
insert into Cars Values('Lexus','IS 300 4dr auto','Sedan','Asia','Rear',3285);
insert into Cars Values('Lexus','GS 300 4dr','Sedan','Asia','Rear',3649);
insert into Cars Values('Lexus','GS 430 4dr','Sedan','Asia','Rear',3715);
insert into Cars Values('Lexus','LS 430 4dr','Sedan','Asia','Rear',3990);
insert into Cars Values('Lexus','SC 430 convertible 2dr','Sports','Asia','Rear',3840);
insert into Cars Values('Lexus','IS 300 SportCross','Wagon','Asia','Rear',3410);
insert into Cars Values('Lincoln','Navigator Luxury','SUV','USA','All',5969);
insert into Cars Values('Lincoln','Aviator Ultimate','SUV','USA','Front',4834);
insert into Cars Values('Lincoln','LS V6 Luxury 4dr','Sedan','USA','Rear',3681);
insert into Cars Values('Lincoln','LS V6 Premium 4dr','Sedan','USA','Rear',3681);
insert into Cars Values('Lincoln','LS V8 Sport 4dr','Sedan','USA','Rear',3768);
insert into Cars Values('Lincoln','LS V8 Ultimate 4dr','Sedan','USA','Rear',3768);
insert into Cars Values('Lincoln','Town Car Signature 4dr','Sedan','USA','Rear',4369);
insert into Cars Values('Lincoln','Town Car Ultimate 4dr','Sedan','USA','Rear',4369);
insert into Cars Values('Lincoln','Town Car Ultimate L 4dr','Sedan','USA','Rear',4474);
insert into Cars Values('MINI','Cooper','Sedan','Europe','Front',2524);
insert into Cars Values('MINI','Cooper S','Sedan','Europe','Front',2678);
insert into Cars Values('Mazda','Tribute DX 2.0','SUV','Asia','All',3091);
insert into Cars Values('Mazda','Mazda3 i 4dr','Sedan','Asia','Front',2696);
insert into Cars Values('Mazda','Mazda3 s 4dr','Sedan','Asia','Front',2762);
insert into Cars Values('Mazda','Mazda6 i 4dr','Sedan','Asia','Front',3042);
insert into Cars Values('Mazda','MPV ES','Sedan','Asia','Front',3812);
insert into Cars Values('Mazda','MX-5 Miata convertible 2dr','Sports','Asia','Rear',2387);
insert into Cars Values('Mazda','MX-5 Miata LS convertible 2dr','Sports','Asia','Rear',2387);
insert into Cars Values('Mazda','RX-8 4dr automatic','Sports','Asia','Rear',3053);
insert into Cars Values('Mazda','RX-8 4dr manual','Sports','Asia','Rear',3029);
insert into Cars Values('Mazda','B2300 SX Regular Cab','Truck','Asia','Rear',2960);
insert into Cars Values('Mazda','B4000 SE Cab Plus','Truck','Asia','All',3571);
insert into Cars Values('Mercedes-Benz','G500','SUV','Europe','All',5423);
insert into Cars Values('Mercedes-Benz','ML500','SUV','Europe','All',4874);
insert into Cars Values('Mercedes-Benz','C230 Sport 2dr','Sedan','Europe','Rear',3250);
insert into Cars Values('Mercedes-Benz','C320 Sport 2dr','Sedan','Europe','Rear',3430);
insert into Cars Values('Mercedes-Benz','C240 4dr','Sedan','Europe','Rear',3360);
insert into Cars Values('Mercedes-Benz','C240 4dr','Sedan','Europe','All',3360);
insert into Cars Values('Mercedes-Benz','C320 Sport 4dr','Sedan','Europe','Rear',3430);
insert into Cars Values('Mercedes-Benz','C320 4dr','Sedan','Europe','Rear',3450);
insert into Cars Values('Mercedes-Benz','C320 4dr','Sedan','Europe','All',3450);
insert into Cars Values('Mercedes-Benz','C32 AMG 4dr','Sedan','Europe','Rear',3540);
insert into Cars Values('Mercedes-Benz','CL500 2dr','Sedan','Europe','Rear',4085);
insert into Cars Values('Mercedes-Benz','CL600 2dr','Sedan','Europe','Rear',4473);
insert into Cars Values('Mercedes-Benz','CLK320 coupe 2dr (convertible)','Sedan','Europe','Rear',3770);
insert into Cars Values('Mercedes-Benz','CLK500 coupe 2dr (convertible)','Sedan','Europe','Rear',3585);
insert into Cars Values('Mercedes-Benz','E320 4dr','Sedan','Europe','Rear',3635);
insert into Cars Values('Mercedes-Benz','E500 4dr','Sedan','Europe','Rear',3815);
insert into Cars Values('Mercedes-Benz','S430 4dr','Sedan','Europe','Rear',4160);
insert into Cars Values('Mercedes-Benz','S500 4dr','Sedan','Europe','All',4390);
insert into Cars Values('Mercedes-Benz','SL500 convertible 2dr','Sports','Europe','Rear',4065);
insert into Cars Values('Mercedes-Benz','SL55 AMG 2dr','Sports','Europe','Rear',4235);
insert into Cars Values('Mercedes-Benz','SL600 convertible 2dr','Sports','Europe','Rear',4429);
insert into Cars Values('Mercedes-Benz','SLK230 convertible 2dr','Sports','Europe','Rear',3055);
insert into Cars Values('Mercedes-Benz','SLK32 AMG 2dr','Sports','Europe','Rear',3220);
insert into Cars Values('Mercedes-Benz','C240','Wagon','Europe','Rear',3470);
insert into Cars Values('Mercedes-Benz','E320','Wagon','Europe','Rear',3966);
insert into Cars Values('Mercedes-Benz','E500','Wagon','Europe','All',4230);
insert into Cars Values('Mercury','Mountaineer','SUV','USA','Front',4374);
insert into Cars Values('Mercury','Sable GS 4dr','Sedan','USA','Front',3308);
insert into Cars Values('Mercury','Grand Marquis GS 4dr','Sedan','USA','Rear',4052);
insert into Cars Values('Mercury','Grand Marquis LS Premium 4dr','Sedan','USA','Rear',4052);
insert into Cars Values('Mercury','Sable LS Premium 4dr','Sedan','USA','Front',3315);
insert into Cars Values('Mercury','Grand Marquis LS Ultimate 4dr','Sedan','USA','Rear',4052);
insert into Cars Values('Mercury','Marauder 4dr','Sedan','USA','Rear',4195);
insert into Cars Values('Mercury','Monterey Luxury','Sedan','USA','Front',4340);
insert into Cars Values('Mercury','Sable GS','Wagon','USA','Front',3488);
insert into Cars Values('Mitsubishi','Endeavor XLS','SUV','Asia','All',4134);
insert into Cars Values('Mitsubishi','Montero XLS','SUV','Asia','All',4718);
insert into Cars Values('Mitsubishi','Outlander LS','SUV','Asia','Front',3240);
insert into Cars Values('Mitsubishi','Lancer ES 4dr','Sedan','Asia','Front',2656);
insert into Cars Values('Mitsubishi','Lancer LS 4dr','Sedan','Asia','Front',2795);
insert into Cars Values('Mitsubishi','Galant ES 2.4L 4dr','Sedan','Asia','Front',3351);
insert into Cars Values('Mitsubishi','Lancer OZ Rally 4dr auto','Sedan','Asia','Front',2744);
insert into Cars Values('Mitsubishi','Diamante LS 4dr','Sedan','Asia','Front',3549);
insert into Cars Values('Mitsubishi','Galant GTS 4dr','Sedan','Asia','Front',3649);
insert into Cars Values('Mitsubishi','Eclipse GTS 2dr','Sports','Asia','Front',3241);
insert into Cars Values('Mitsubishi','Eclipse Spyder GT convertible 2dr','Sports','Asia','Front',3296);
insert into Cars Values('Mitsubishi','Lancer Evolution 4dr','Sports','Asia','Front',3263);
insert into Cars Values('Mitsubishi','Lancer Sportback LS','Wagon','Asia','Front',3020);
insert into Cars Values('Nissan','Pathfinder Armada SE','SUV','Asia','Front',5013);
insert into Cars Values('Nissan','Pathfinder SE','SUV','Asia','Front',3871);
insert into Cars Values('Nissan','Xterra XE V6','SUV','Asia','Front',3760);
insert into Cars Values('Nissan','Sentra 1.8 4dr','Sedan','Asia','Front',2513);
insert into Cars Values('Nissan','Sentra 1.8 S 4dr','Sedan','Asia','Front',2581);
insert into Cars Values('Nissan','Altima S 4dr','Sedan','Asia','Front',3039);
insert into Cars Values('Nissan','Sentra SE-R 4dr','Sedan','Asia','Front',2761);
insert into Cars Values('Nissan','Altima SE 4dr','Sedan','Asia','Front',3197);
insert into Cars Values('Nissan','Maxima SE 4dr','Sedan','Asia','Front',3473);
insert into Cars Values('Nissan','Maxima SL 4dr','Sedan','Asia','Front',3476);
insert into Cars Values('Nissan','Quest S','Sedan','Asia','Front',4012);
insert into Cars Values('Nissan','Quest SE','Sedan','Asia','Front',4175);
insert into Cars Values('Nissan','350Z coupe 2dr','Sports','Asia','Rear',3188);
insert into Cars Values('Nissan','350Z Enthusiast convertible 2dr','Sports','Asia','Rear',3428);
insert into Cars Values('Nissan','Frontier King Cab XE V6','Truck','Asia','All',3932);
insert into Cars Values('Nissan','Titan King Cab XE','Truck','Asia','All',5287);
insert into Cars Values('Nissan','Murano SL','Wagon','Asia','Rear',3801);
insert into Cars Values('Oldsmobile','Alero GX 2dr','Sedan','USA','Front',2946);
insert into Cars Values('Oldsmobile','Alero GLS 2dr','Sedan','USA','Front',3085);
insert into Cars Values('Oldsmobile','Silhouette GL','Sedan','USA','Front',3948);
insert into Cars Values('Pontiac','Aztekt','SUV','USA','Front',3779);
insert into Cars Values('Pontiac','Sunfire 1SA 2dr','Sedan','USA','Front',2771);
insert into Cars Values('Pontiac','Grand Am GT 2dr','Sedan','USA','Front',3118);
insert into Cars Values('Pontiac','Grand Prix GT1 4dr','Sedan','USA','Front',3477);
insert into Cars Values('Pontiac','Sunfire 1SC 2dr','Sedan','USA','Front',2771);
insert into Cars Values('Pontiac','Grand Prix GT2 4dr','Sedan','USA','Front',3484);
insert into Cars Values('Pontiac','Bonneville GXP 4dr','Sedan','USA','Front',3790);
insert into Cars Values('Pontiac','Montana','Sedan','USA','Front',3803);
insert into Cars Values('Pontiac','Montana EWB','Sedan','USA','All',4431);
insert into Cars Values('Pontiac','GTO 2dr','Sports','USA','Rear',3725);
insert into Cars Values('Pontiac','Vibe','Wagon','USA','Rear',2701);
insert into Cars Values('Porsche','Cayenne S','SUV','Europe','All',4950);
insert into Cars Values('Porsche','911 Carrera convertible 2dr (coupe)','Sports','Europe','Rear',3135);
insert into Cars Values('Porsche','911 Carrera 4S coupe 2dr (convert)','Sports','Europe','All',3240);
insert into Cars Values('Porsche','911 Targa coupe 2dr','Sports','Europe','Rear',3119);
insert into Cars Values('Porsche','911 GT2 2dr','Sports','Europe','Rear',3131);
insert into Cars Values('Porsche','Boxster convertible 2dr','Sports','Europe','Rear',2811);
insert into Cars Values('Porsche','Boxster S convertible 2dr','Sports','Europe','Rear',2911);
insert into Cars Values('Saab','9-3 Arc Sport 4dr','Sedan','Europe','Front',3175);
insert into Cars Values('Saab','9-3 Aero 4dr','Sedan','Europe','Front',3175);
insert into Cars Values('Saab','9-5 Arc 4dr','Sedan','Europe','Front',3470);
insert into Cars Values('Saab','9-5 Aero 4dr','Sedan','Europe','Front',3470);
insert into Cars Values('Saab','9-3 Arc convertible 2dr','Sedan','Europe','Front',3480);
insert into Cars Values('Saab','9-3 Aero convertible 2dr','Sedan','Europe','Front',3700);
insert into Cars Values('Saab','9-5 Aero','Wagon','Europe','Front',3620);
insert into Cars Values('Saturn','VUE','SUV','USA','All',3381);
insert into Cars Values('Saturn','Ion1 4dr','Sedan','USA','Front',2692);
insert into Cars Values('Saturn','lon2 4dr','Sedan','USA','Front',2692);
insert into Cars Values('Saturn','lon3 4dr','Sedan','USA','Front',2692);
insert into Cars Values('Saturn','lon2 quad coupe 2dr','Sedan','USA','Front',2751);
insert into Cars Values('Saturn','lon3 quad coupe 2dr','Sedan','USA','Front',2751);
insert into Cars Values('Saturn','L300-2 4dr','Sedan','USA','Front',3197);
insert into Cars Values('Saturn','L300 2','Wagon','USA','Front',3109);
insert into Cars Values('Scion','xA 4dr hatch','Sedan','Asia','Front',2340);
insert into Cars Values('Scion','xB','Wagon','Asia','Front',2425);
insert into Cars Values('Subaru','Impreza 2.5 RS 4dr','Sedan','Asia','All',2965);
insert into Cars Values('Subaru','Legacy L 4dr','Sedan','Asia','All',3285);
insert into Cars Values('Subaru','Legacy GT 4dr','Sedan','Asia','All',3395);
insert into Cars Values('Subaru','Outback Limited Sedan 4dr','Sedan','Asia','All',3495);
insert into Cars Values('Subaru','Outback H6 4dr','Sedan','Asia','All',3610);
insert into Cars Values('Subaru','Outback H-6 VDC 4dr','Sedan','Asia','All',3630);
insert into Cars Values('Subaru','Impreza WRX 4dr','Sports','Asia','All',3085);
insert into Cars Values('Subaru','Impreza WRX STi 4dr','Sports','Asia','All',3263);
insert into Cars Values('Subaru','Baja','Truck','Asia','All',3485);
insert into Cars Values('Subaru','Forester X','Wagon','Asia','All',3090);
insert into Cars Values('Subaru','Outback','Wagon','Asia','All',3430);
insert into Cars Values('Suzuki','XL-7 EX','SUV','Asia','Front',3682);
insert into Cars Values('Suzuki','Vitara LX','SUV','Asia','All',3020);
insert into Cars Values('Suzuki','Aeno S 4dr','Sedan','Asia','Front',2676);
insert into Cars Values('Suzuki','Aerio LX 4dr','Sedan','Asia','Front',2676);
insert into Cars Values('Suzuki','Forenza S 4dr','Sedan','Asia','Front',2701);
insert into Cars Values('Suzuki','Forenza EX 4dr','Sedan','Asia','Front',2756);
insert into Cars Values('Suzuki','Verona LX 4dr','Sedan','Asia','Front',3380);
insert into Cars Values('Suzuki','Aerio SX','Wagon','Asia','All',2932);
insert into Cars Values('Toyota','Prius 4dr (gas/electric)','Hybrid','Asia','Front',2890);
insert into Cars Values('Toyota','Sequoia SR5','SUV','Asia','All',5270);
insert into Cars Values('Toyota','4Runner SR5 V6','SUV','Asia','Front',4035);
insert into Cars Values('Toyota','Highlander V6','SUV','Asia','All',3935);
insert into Cars Values('Toyota','Land Cruiser','SUV','Asia','All',5390);
insert into Cars Values('Toyota','RAV4','SUV','Asia','All',3119);
insert into Cars Values('Toyota','Corolla CE 4dr','Sedan','Asia','Front',2502);
insert into Cars Values('Toyota','Corolla S 4dr','Sedan','Asia','Front',2524);
insert into Cars Values('Toyota','Corolla LE 4dr','Sedan','Asia','Front',2524);
insert into Cars Values('Toyota','Echo 2dr manual','Sedan','Asia','Front',2035);
insert into Cars Values('Toyota','Echo 2dr auto','Sedan','Asia','Front',2085);
insert into Cars Values('Toyota','Echo 4dr','Sedan','Asia','Front',2055);
insert into Cars Values('Toyota','Camry LE 4dr','Sedan','Asia','Front',3086);
insert into Cars Values('Toyota','Camry LE V6 4dr','Sedan','Asia','Front',3296);
insert into Cars Values('Toyota','Camry Solara SE 2dr','Sedan','Asia','Front',3175);
insert into Cars Values('Toyota','Camry Solara SE V6 2dr','Sedan','Asia','Front',3417);
insert into Cars Values('Toyota','Avalon XL 4dr','Sedan','Asia','Front',3417);
insert into Cars Values('Toyota','Camry XLE V6 4dr','Sedan','Asia','Front',3362);
insert into Cars Values('Toyota','Camry Solara SLE V6 2dr','Sedan','Asia','Front',3439);
insert into Cars Values('Toyota','Avalon XLS 4dr','Sedan','Asia','Front',3439);
insert into Cars Values('Toyota','Sienna CE','Sedan','Asia','Front',4120);
insert into Cars Values('Toyota','Sienna XLE Limited','Sedan','Asia','Front',4165);
insert into Cars Values('Toyota','Celica GT-S 2dr','Sports','Asia','Front',2500);
insert into Cars Values('Toyota','MR2 Spyder convertible 2dr','Sports','Asia','Rear',2195);
insert into Cars Values('Toyota','Tacoma','Truck','Asia','Rear',2750);
insert into Cars Values('Toyota','Tundra Regular Cab V6','Truck','Asia','Rear',3925);
insert into Cars Values('Toyota','Tundra Access Cab V6 SR5','Truck','Asia','All',4435);
insert into Cars Values('Toyota','Matrix XR','Wagon','Asia','Front',2679);
insert into Cars Values('Volkswagen','Touareg V6','SUV','Europe','All',5086);
insert into Cars Values('Volkswagen','Golf GLS 4dr','Sedan','Europe','Front',2897);
insert into Cars Values('Volkswagen','GTI 1.8T 2dr hatch','Sedan','Europe','Front',2934);
insert into Cars Values('Volkswagen','Jetta GLS TDI 4dr','Sedan','Europe','Front',3003);
insert into Cars Values('Volkswagen','New Beetle GLS 1.8T 2dr','Sedan','Europe','Front',2820);
insert into Cars Values('Volkswagen','Jetta GLI VR6 4dr','Sedan','Europe','Front',3179);
insert into Cars Values('Volkswagen','New Beetle GLS convertible 2dr','Sedan','Europe','Front',3082);
insert into Cars Values('Volkswagen','Passat GLS 4dr','Sedan','Europe','Front',3241);
insert into Cars Values('Volkswagen','Passat GLX V6 4MOTION 4dr','Sedan','Europe','Front',3721);
insert into Cars Values('Volkswagen','Passat W8 4MOTION 4dr','Sedan','Europe','Front',3953);
insert into Cars Values('Volkswagen','Phaeton 4dr','Sedan','Europe','Front',5194);
insert into Cars Values('Volkswagen','Phaeton W12 4dr','Sedan','Europe','Front',5399);
insert into Cars Values('Volkswagen','Jetta GL','Wagon','Europe','Front',3034);
insert into Cars Values('Volkswagen','Passat GLS 1.8T','Wagon','Europe','Front',3338);
insert into Cars Values('Volkswagen','Passat W8','Wagon','Europe','Front',4067);
insert into Cars Values('Volvo','XC90 T6','SUV','Europe','All',4638);
insert into Cars Values('Volvo','S40 4dr','Sedan','Europe','Front',2767);
insert into Cars Values('Volvo','S60 2.5 4dr','Sedan','Europe','All',3903);
insert into Cars Values('Volvo','S60 T5 4dr','Sedan','Europe','Front',3766);
insert into Cars Values('Volvo','S60 R 4dr','Sedan','Europe','All',3571);
insert into Cars Values('Volvo','S80 2.9 4dr','Sedan','Europe','Front',3576);
insert into Cars Values('Volvo','S80 2.5T 4dr','Sedan','Europe','All',3691);
insert into Cars Values('Volvo','C70 LPT convertible 2dr','Sedan','Europe','Front',3450);
insert into Cars Values('Volvo','C70 HPT convertible 2dr','Sedan','Europe','Front',3450);
insert into Cars Values('Volvo','S80 T6 4dr','Sedan','Europe','Front',3653);
insert into Cars Values('Volvo','V40','Wagon','Europe','Front',2822);
insert into Cars Values('Volvo','XC70','Wagon','Europe','All',3823);
```

## Alter column datatype

```sql
MariaDB [TEST]> ALTER TABLE Cars MODIFY Lenght BIGINT;
Query OK, 428 rows affected (0.09 sec)
Records: 428  Duplicates: 0  Warnings: 0
```
## Checking the change

```sql
MariaDB [TEST]> SHOW CREATE TABLE Cars;
+-------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Table | Create Table                                                  |
+-------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Cars  | CREATE TABLE `Cars` (
  `Make` int(11) DEFAULT NULL,
  `Model` varchar(255) DEFAULT NULL,
  `Type` varchar(50) DEFAULT NULL,
  `Origin` varchar(50) DEFAULT NULL,
  `DriveTrain` varchar(50) DEFAULT NULL,
  `Lenght` bigint(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1 |
+-------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
1 row in set (0.00 sec)
```
> **Note:** We must be careful when changing the data type of the column, as we can change the structure of the data. For example:

## Alter a varchar column
```sql
MariaDB [TEST]> ALTER TABLE Cars MODIFY Make BIGINT;
Query OK, 428 rows affected (0.10 sec)
Records: 428  Duplicates: 0  Warnings: 0
```
```sql
MariaDB [TEST]> select * from Cars limit 10;
+------+-------------------------+--------+--------+------------+--------+
| Make | Model                   | Type   | Origin | DriveTrain | Lenght |
+------+-------------------------+--------+--------+------------+--------+
|    0 | MDX                     | SUV    | Asia   | All        |   4451 |
|    0 | RSX Type S 2dr          | Sedan  | Asia   | Front      |   2778 |
|    0 | TSX 4dr                 | Sedan  | Asia   | Front      |   3230 |
|    0 | TL 4dr                  | Sedan  | Asia   | Front      |   3575 |
|    0 | 3.5 RL 4dr              | Sedan  | Asia   | Front      |   3880 |
|    0 | 3.5 RL w/Navigation 4dr | Sedan  | Asia   | Front      |   3893 |
|    0 | NSX coupe 2dr manual S  | Sports | Asia   | Rear       |   3153 |
|    0 | A4 1.8T 4dr             | Sedan  | Europe | Front      |   3252 |
|    0 | A41.8T convertible 2dr  | Sedan  | Europe | Front      |   3638 |
|    0 | A4 3.0 4dr              | Sedan  | Europe | Front      |   3462 |
+------+-------------------------+--------+--------+------------+--------+
10 rows in set (0.00 sec)
```
```sql

MariaDB [TEST]> select count(*) as qtd
		       ,make
		       from Cars
			   group by
			   make
		       order by 1 desc;
+-----+---------------+
| qtd | make          |
+-----+---------------+
|  28 | Toyota        |
|  27 | Chevrolet     |
|  26 | Mercedes-Benz |
|  23 | Ford          |
|  20 | BMW           |
|  19 | Audi          |
|  17 | Honda         |
|  17 | Nissan        |
|  15 | Volkswagen    |
|  15 | Chrysler      |
|  13 | Mitsubishi    |
|  13 | Dodge         |
|  12 | Hyundai       |
|  12 | Volvo         |
|  12 | Jaguar        |
|  11 | Pontiac       |
|  11 | Kia           |
|  11 | Subaru        |
|  11 | Mazda         |
|  11 | Lexus         |
|   9 | Lincoln       |
|   9 | Mercury       |
|   9 | Buick         |
|   8 | Cadillac      |
|   8 | GMC           |
|   8 | Infiniti      |
|   8 | Suzuki        |
|   8 | Saturn        |
|   7 | Acura         |
|   7 | Porsche       |
|   7 | Saab          |
|   3 | Jeep          |
|   3 | Land Rover    |
|   3 | Oldsmobile    |
|   2 | Scion         |
|   2 | MINI          |
|   2 | Isuzu         |
|   1 | Hummer        |
+-----+---------------+
38 rows in set (0.00 sec)
```

# Creating a view from table
```sql
MariaDB [TEST]> CREATE VIEW IF NOT EXISTS vw_Cars AS SELECT * FROM Cars WHERE make = 'Volvo';
Query OK, 0 rows affected (0.01 sec)

MariaDB [TEST]> select * from vw_Cars;
+-------+-------------------------+-------+--------+------------+--------+
| Make  | Model                   | Type  | Origin | DriveTrain | Lenght |
+-------+-------------------------+-------+--------+------------+--------+
| Volvo | XC90 T6                 | SUV   | Europe | All        |   4638 |
| Volvo | S40 4dr                 | Sedan | Europe | Front      |   2767 |
| Volvo | S60 2.5 4dr             | Sedan | Europe | All        |   3903 |
| Volvo | S60 T5 4dr              | Sedan | Europe | Front      |   3766 |
| Volvo | S60 R 4dr               | Sedan | Europe | All        |   3571 |
| Volvo | S80 2.9 4dr             | Sedan | Europe | Front      |   3576 |
| Volvo | S80 2.5T 4dr            | Sedan | Europe | All        |   3691 |
| Volvo | C70 LPT convertible 2dr | Sedan | Europe | Front      |   3450 |
| Volvo | C70 HPT convertible 2dr | Sedan | Europe | Front      |   3450 |
| Volvo | S80 T6 4dr              | Sedan | Europe | Front      |   3653 |
| Volvo | V40                     | Wagon | Europe | Front      |   2822 |
| Volvo | XC70                    | Wagon | Europe | All        |   3823 |
+-------+-------------------------+-------+--------+------------+--------+
12 rows in set (0.00 sec)
```


# Deleting data from table

```sql
MariaDB [TEST]> DELETE FROM Cars;
Query OK, 428 rows affected (0.02 sec)
```


# Creation tables for show execution plan 


```sql
CREATE TABLE `Table1` (
  `ID` int(11) NOT NULL,
  KEY `ID` (`ID`)
);

CREATE TABLE `Table2` (
  `ID` int(11) NOT NULL,
  KEY `ID` (`ID`)
);

CREATE TABLE `Table3` (
  `ID` int(11) NOT NULL,
  PRIMARY KEY (`ID`)
);
```

#  Query analysis
```sql
MariaDB [TEST]> explain select T1.ID FROM Table1 T1 LEFT JOIN (SELECT T3.ID FROM Table3 T3 LEFT JOIN Table2 T2 ON T3.ID = T2.ID WHERE T2.ID IS NULL) T2 ON T1.ID=T2.ID WHERE T2.ID IS NULL;
+------+-------------+-------+--------+---------------+---------+---------+------------+------+--------------------------------------+
| id   | select_type | table | type   | possible_keys | key     | key_len | ref        | rows | Extra                                |
+------+-------------+-------+--------+---------------+---------+---------+------------+------+--------------------------------------+
|    1 | SIMPLE      | T1    | index  | NULL          | ID      | 4       | NULL       |    1 | Using index                          |
|    1 | SIMPLE      | T3    | eq_ref | PRIMARY       | PRIMARY | 4       | TEST.T1.ID |    1 | Using where; Using index; Not exists |
|    1 | SIMPLE      | T2    | ref    | ID            | ID      | 4       | TEST.T1.ID |    1 | Using where; Using index             |
+------+-------------+-------+--------+---------------+---------+---------+------------+------+--------------------------------------+
3 rows in set (0.00 sec)
```

## References
-  [MariaDB Tutorial For Beginners](https://www.youtube.com/watch?v=_AMj02sANpI)
- [Mariadb Documentation](https://mariadb.com/kb/en/documentation/)
- [Install Mariadb on Linux](https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04-pt)


