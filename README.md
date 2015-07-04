ThaiYearFormatter
=================
แปลงค่าวันที่ เป็นปีภาษาไทย สำหรับ Yii framework (Yii 2)

>  ThaiYearFormatter จำเป็นต้องเปิดการใช้งาน  php extension intl  ใน php.ini

เปิดไฟล์ php.ini แล้วเปิดใช้งาน ดังนี้
```
extension=php_intl.dll

[intl]
intl.default_locale =th_TH.UTF-8
; This directive allows you to produce PHP errors when some error
; happens within intl functions. The value is the level of the error produced.
; Default is 0, which does not produce any errors.
;intl.error_level = E_WARNING
```

หากยังไม่มีให้ติดตั้งที่ server [ดูที่นี่](http://php.net/manual/en/intl.installation.php)

------------
[ที่มา  http://stackoverflow.com/questions/3191664/list-of-all-locales-and-their-short-codes](http://stackoverflow.com/questions/3191664/list-of-all-locales-and-their-short-codes)

การติดตั้ง
------

```
composer require --prefer-dist dixonsatit/yii2-thai-year-formatter "0.9.6"
```

หรือเพิ่มที่ ไฟล์ composer.json ในส่วน require

```
"dixonsatit/yii2-thai-year-formatter": "0.9.6"
```
หลังจากนั้น รันคำสั่ง `composer update`

การตั้งค่า
------

```
'language'=>'th_TH', // เปิดใช้งานภาษาไทย
'components' => [
	//...
    'thaiFormatter'=>[
        'class'=>'dixonsatit\thaiYearFormatter\ThaiYearFormatter',
    ],
]
```

การเรียกใช้งาน
-----

เรียกใช้งานผ่าน component `thaiFormatter`


```php
$time = time();
//$time = '2015-06-03 13:25:17';
echo Yii::$app->thaiFormatter->asDate($time, 'short')."<br>";
echo Yii::$app->thaiFormatter->asDate($time, 'medium')."<br>";
echo Yii::$app->thaiFormatter->asDate($time, 'long')."<br>";
echo Yii::$app->thaiFormatter->asDate($time, 'full')."<br>";

echo Yii::$app->thaiFormatter->asDateTime($time, 'short')."<br>";
echo Yii::$app->thaiFormatter->asDateTime($time, 'medium')."<br>";
echo Yii::$app->thaiFormatter->asDateTime($time, 'long')."<br>";
echo Yii::$app->thaiFormatter->asDateTime($time, 'full')."<br>";

echo Yii::$app->thaiFormatter->asDate($time, 'php:Y-m-d');
echo Yii::$app->thaiFormatter->asDateTime($time, 'php:Y-m-d H:i:s');

```

> ดู php date format ได้ที่นี่ [php date format](http://php.net/manual/en/function.date.php)

แสดงผล
-----

```
25/6/2558
25 มิ.ย. 2558
25 มิถุนายน 2558
วันอาทิตย์ที่ 25 มิถุนายน พ.ศ. 2558

25/6/2558, 9:57
25 มิ.ย. 2558, 9:57:18
25 มิถุนายน 2558, 9 นาฬิกา 57 นาที 18 วินาที GMT+07:00
วันอาทิตย์ที่ 25 มิถุนายน พ.ศ. 2558, 9 นาฬิกา 57 นาที 18 วินาที GMT+07:00

2015-06-24
2015-06-24 05:32:54
```
