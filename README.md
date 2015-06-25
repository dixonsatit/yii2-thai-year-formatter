ThaiYearFormatter
=================
Convert Year to Thai Buddhist Era 

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist dixonsatit/yii2-thai-year-formatter "*"
```

or add

```
"dixonsatit/yii2-thai-year-formatter": "*"
```

to the require section of your `composer.json` file.

Config
------

```
//'language'=>'th', // เปิดใช้งานภาษาไทยหากต้องการเป็นค่า default
'components' => [
	//...
    'formatter'=>[
        'class'=>'dixonsatit\thaiYearFormatter\ThaiYearFormatter',
    ],
]
```

Usage
-----

เรียกใช้งานผ่าน component `formatter`


```php
$time = time();

// asDate
Yii::$app->formatter->locale = 'en-US';
echo Yii::$app->formatter->asDate($time, 'short')."<br>";
echo Yii::$app->formatter->asDate($time, 'medium')."<br>";
echo Yii::$app->formatter->asDate($time, 'long')."<br>";
echo Yii::$app->formatter->asDate($time, 'full')."<br>";

Yii::$app->formatter->locale = 'th';
echo Yii::$app->formatter->asDate($time, 'short')."<br>";
echo Yii::$app->formatter->asDate($time, 'medium')."<br>";
echo Yii::$app->formatter->asDate($time, 'long')."<br>";
echo Yii::$app->formatter->asDate($time, 'full')."<br>";

// asDateTime
Yii::$app->formatter->locale = 'en-US';
echo Yii::$app->formatter->asDateTime($time, 'short')."<br>";
echo Yii::$app->formatter->asDateTime($time, 'medium')."<br>";
echo Yii::$app->formatter->asDateTime($time, 'long')."<br>";
echo Yii::$app->formatter->asDateTime($time, 'full')."<br>";

Yii::$app->formatter->locale = 'th';
echo Yii::$app->formatter->asDateTime($time, 'short')."<br>";
echo Yii::$app->formatter->asDateTime($time, 'medium')."<br>";
echo Yii::$app->formatter->asDateTime($time, 'long')."<br>";
echo Yii::$app->formatter->asDateTime($time, 'full')."<br>";

```

Preview

```
6/25/15
Jun 25, 2015
June 25, 2015
Thursday, June 25, 2015

25/6/2558
25 มิ.ย. 2558
25 มิถุนายน 2558
วันอาทิตย์ที่ 25 มิถุนายน ค.ศ. 2558


6/25/15 9:57 AM
Jun 25, 2015 9:57:18 AM
June 25, 2015 9:57:18 AM GMT+07:00
Thursday, June 25, 2015 9:57:18 AM Indochina Time

25/6/2558, 9:57
25 มิ.ย. 2558, 9:57:18
25 มิถุนายน 2558, 9 นาฬิกา 57 นาที 18 วินาที GMT+07:00
วันอาทิตย์ที่ 25 มิถุนายน ค.ศ. 2558, 9 นาฬิกา 57 นาที 18 วินาที GMT+07:00
```

