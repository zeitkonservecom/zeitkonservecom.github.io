```
Im Installtool, oder auf der Seite direkt folgender Fehler in Typo3 7.6:

    ---
    Detected Fatal Error
    Class 'GeorgRinger\News\Utility\EmConfiguration' not found in /var/www/dev/htdocs/typo3conf/ext/news/ext_localconf.php on line 6
    ---


In der index.php steht:

<     $classLoader = require __DIR__ . '/../vendor/autoload.php';
<     (new \TYPO3\CMS\Backend\Http\Application($classLoader))->run();

typo3temp/autoloader und dementsprechend class map ist leer

Bedeutet: Es wurde (noch) kein class-map-cache aufgebaut.
Lösung: Cache leeren, Startseite aufrufen, Backend aufrufen, Cache leeren
```
