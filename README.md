Cloudflare API
==================

Yii2 Component for CloudFlare api v4.0. https://www.cloudflare.com/

Minimum requirements: Yii2, Curl

Installation via Composer:

`composer require biozahard/yii2-cloudflare-api`


Configuring in config.php:

```php
'components' => [
//...
        'cloudflare' => [
            'class'         => 'biozahard\cloudflare\CloudflareApi',
            'apiurl'   => 'https://api.cloudflare.com/client/v4/',
            'authkey'       => '5gds0kfdsc024ndsofsj049jisdofjsd034jw',
            'authemail'     => 'admin@mail.com',
            'sites'         => [
                'mysite.com',
                'thebest-country.ua',
                'anotheronesite.biz',
            ],
        ],
//...
]
```

After this configuring you can use: `\Yii::$app->cloudflare`

So, let's see some examples:

1. Purge all cloudflare cache:
```
//get the CloudFlare api component
$cf = \Yii::$app->cloudflare;

//purge cache for specific website:
$cf->purgeCache('thebest-country.ua');

//Clear the cache for the first site from the specified list:
$cf->purgeCache();
```


***

License: LGPL v3 or later
