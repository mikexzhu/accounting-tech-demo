#Phalcon + MongoDB#
##Phalcon installation##
Install phalcon on the server by adding the library to the php extension folder and add it to php.ini, depending on your version of php.
Currently: https://docs.phalconphp.com/bs/3.2/installation
##MongoDB installation##
Install mongoDB by following the instructions provided by MongoDB
Currently: https://docs.mongodb.com/manual/installation/
Install the MongoDB php driver, get it from http://pecl.php.net/package/mongo and put it in the extension folder and add it to php.ini
##Linking Phalcon with MongoDB##
// Set up the database service
$di->set(
    'mongo',
    function () {
        $mongo = new MongoClient();

        return $mongo->selectDB('accounting');
    },
    true
);

$di->set('collectionManager', function(){
    return new Phalcon\Mvc\Collection\Manager();
}, true);
