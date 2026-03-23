# PostBoost PHP SDK

Official PHP client for the [PostBoost API](https://postboost.co/docs/api).

## Install

```bash
composer require postboost/php-sdk
```

| | |
|---|---|
| **Packagist** | [packagist.org/packages/postboost/php-sdk](https://packagist.org/packages/postboost/php-sdk) |
| **GitHub** | [postboost-co/postboost-php](https://github.com/postboost-co/postboost-php) |
| **Docs** | [postboost.co/docs/api](https://postboost.co/docs/api) |
| **Version** | v1.1.0 |

## Quick start

```php
use PostBoost\Client\Api\PostsApi;
use PostBoost\Client\Configuration;

$config = Configuration::getDefaultConfiguration()
    ->setAccessToken('YOUR_API_TOKEN');

$api = new PostsApi(new \GuzzleHttp\Client(), $config);
$posts = $api->listPosts('YOUR_WORKSPACE_UUID');
foreach ($posts as $post) {
    echo $post->getUuid() . PHP_EOL;
}
```

## License

MIT
