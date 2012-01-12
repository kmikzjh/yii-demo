# BOXFILE SAMPLE #

    web1:
      php_extensions:
        - dom
        - pdo
        - pdo_sqlite
        - pdo_mysql
        - apc
        - mcrypt
        - soap
        - gd
        - freetype
      document_root: /demos/blog
      shared_writable_dirs:
        - /demos/blog/protected/runtime
        - /demos/blog/assets


# DATABASE CONNECTION EXAMPLE #
We suggest configuring your application to use different database settings depending on the environment it's running in. You'll be using some precreated environment variables if you use this method.

You'll need to create an [environment variable](http://help.pagodabox.com/customer/portal/articles/175470) to specify the platform. We recommend PLATFORM = PAGODABOX.



    if (isset($_SERVER['PLATFORM']) && $_SERVER['PLATFORM'] == 'PAGODABOX'){
        'db'=>array(
            'connectionString' => 'mysql:host=tunnel.pagodabox.com;mysql:port=3306;dbname=sharolyn',
            'emulatePrepare' => true,
            'username' => 'oma',
            'password' => 'q57aLFtZ',
            'charset' => 'utf8',
            'tablePrefix' => 'tbl_',
            ),
         }
    else {
        'db'=>array(
            'connectionString' => 'mysql:host=localhost;dbname=blog',
            'emulatePrepare' => true,
            'username' => 'root',
            'password' => '',
            'charset' => 'utf8',
            'tablePrefix' => 'tbl_',
            ),
    }