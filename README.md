# pathfind
Find a path up in the structure, based on contents.

```php
<?php

// entry-point/index.php

require dirname( __FILE__ ) . DIRECTORY_SEPARATOR . 'bootstrap.php';

$pathFind = $pathFind->withPath( parse_url( $_SERVER[ 'REQUEST_URI' ], PHP_URL_PATH ) );

$pathFind = $pathFind->withContains( [ 'header.php' ] );
require $pathFind . DS . 'header.php';

// your app

$pathFind = $pathFind->withContains( [ 'footer.php' ] );
require $pathFind . DS . 'footer.php';
```

```php
<?php

// bootstrap.php, this is loaded before pathFind is used in the index file

require_once dirname( __FILE__ ) . DIRECTORY_SEPARATOR . 'PathFind.php';

$pathFind = new PathFind;
$pathFind->pathFind( __FILE__, [ 'public_html' ] ) . DS . 'main' . DS . 'lib.php';
```
