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
//'language'=>'th', //  uncomment  if you want set default language to th
'components' => [
	//...
    'formatter'=>[
        'class'=>'dixonsatit\thaiYearFormatter\ThaiYearFormatter',
    ],
]
```

Usage
-----

Once the extension is installed, simply use it in your code by  :


```php
$time = time();

Yii::$app->formatter->locale = 'en-US';
echo Yii::$app->formatter->asDate($time, 'short')."<br>";
echo Yii::$app->formatter->asDate($time, 'medium')."<br>";
echo Yii::$app->formatter->asDate($time, 'long')."<br>";
echo Yii::$app->formatter->asDate($time, 'full')."<br>";
echo '<hr>';
echo Yii::$app->formatter->locale = 'th';
echo Yii::$app->formatter->asDate($time, 'short')."<br>";
echo Yii::$app->formatter->asDate($time, 'medium')."<br>";
echo Yii::$app->formatter->asDate($time, 'long')."<br>";
echo Yii::$app->formatter->asDate($time, 'full')."<br>";

```

