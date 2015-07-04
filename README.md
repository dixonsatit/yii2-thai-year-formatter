ThaiYearFormatter
=================
แปลงค่าวันที่ เป็นปีภาษาไทย

การติดตั้ง
------------

```
composer require --prefer-dist dixonsatit/yii2-thai-year-formatter "0.9.6"
```

หรือเพิ่มที่ ไฟล์ composer.json ในส่วน require

```
"dixonsatit/yii2-thai-year-formatter": "0.9.6"
```
หลังจากนั้น รันคำสั่ง `composer update`

Config
------

```
//'language'=>'th_TH', // เปิดใช้งานภาษาไทยหากต้องการเป็นค่า default
'components' => [
	//...
    'thaiFormatter'=>[
        'class'=>'dixonsatit\thaiYearFormatter\ThaiYearFormatter',
    ],
]
```

Usage
-----

เรียกใช้งานผ่าน component `formatter`


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

```

Preview

```

25/6/2558
25 มิ.ย. 2558
25 มิถุนายน 2558
วันอาทิตย์ที่ 25 มิถุนายน ค.ศ. 2558

25/6/2558, 9:57
25 มิ.ย. 2558, 9:57:18
25 มิถุนายน 2558, 9 นาฬิกา 57 นาที 18 วินาที GMT+07:00
วันอาทิตย์ที่ 25 มิถุนายน พ.ศ. 2558, 9 นาฬิกา 57 นาที 18 วินาที GMT+07:00
```
