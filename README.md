# Wikipedia

### Installation

Begin by installing this package through Composer.

```js
{
    "require": {
        "ekendra/wikipedia": "dev-master"
    }
}
```

### Usage

**Retrieve page extract**

```php
$wikipedia = new \Ekendra\Wikipedia\Wikipedia;

return $wikipedia->search("Rome")->getSentences(5);
```

**Same with QueryBuilder**

```php
$qb = new \Ekendra\Wikipedia\QueryBuilder;

$qb->setFormat("php");
$qb->setTitles("Nepal");
$qb->setExtractsSentences(3);
$qb->setExtractsPlainText(true);

$response = unserialize( $qb->fetch() );

$page = reset( $response["query"]["pages"] );

return $page["extract"];
```
