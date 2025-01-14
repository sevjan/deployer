<!-- DO NOT EDIT THIS FILE! -->
<!-- Instead edit contrib/ispmanager.php -->
<!-- Then run bin/docgen -->

# Ispmanager Recipe

[Source](/contrib/ispmanager.php)



This recipe for work with ISPManager Lite panel by API.


## Configuration
### ispmanager_owner
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L10)



```php title="Default value"
'www-root'
```


### ispmanager_doc_root
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L11)



```php title="Default value"
'/var/www/' . get('ispmanager_owner') . '/data/'
```


### ispmanager
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L14)

ISPManager default configuration

```php title="Default value"
[
    'api' => [
        'dsn' => 'https://root:password@localhost:1500/ispmgr',
        'secure' => true,
    ],
    'createDomain' => NULL,
    'updateDomain' => NULL,
    'deleteDomain' => NULL,
    'createDatabase' => NULL,
    'deleteDatabase' => NULL,
    'phpSelect' => NULL,
    'createAlias' => NULL,
    'deleteAlias' => NULL,
]
```


### vhost
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L30)

Vhost default configuration

```php title="Default value"
[
    'name' => '{{domain}}',
    'php_enable' => 'on',
    'aliases' => 'www.{{domain}}',
    'home' => 'www/{{domain}}',
    'owner' => get('ispmanager_owner'),
    'email' => 'webmaster@{{domain}}',
    'charset' => 'off',
    'dirindex' => 'index.php uploaded.html',
    'ssi' => 'on',
    'php' => 'on',
    'php_mode' => 'php_mode_mod',
    'basedir' => 'on',
    'php_apache_version' => 'native',
    'cgi' => 'off',
    'log_access' => 'on',
    'log_error' => 'on',
]
```


### ispmanager_session
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L50)

Storage



### ispmanager_databases
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L51)



```php title="Default value"
[
    'servers' => [],
    'hosts' => [],
    'dblist' => [],
]
```


### ispmanager_domains
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L57)





### ispmanager_phplist
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L58)





### ispmanager_aliaslist
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L59)






## Tasks

### ispmanager:init
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L62)

Installs ispmanager.




### ispmanager:db-server-list
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L85)

Takes database servers list.




### ispmanager:db-list
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L122)

Takes databases list.




### ispmanager:domain-list
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L144)

Takes domain list.




### ispmanager:db-create
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L160)

Creates new database.




### ispmanager:db-delete
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L230)

Deletes database.




### ispmanager:domain-create
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L281)

Creates new domain.




### ispmanager:get-php-list
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L327)

Gets allowed PHP modes and versions.




### ispmanager:print-php-list
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L373)

Prints allowed PHP modes and versions.




### ispmanager:domain-php-select
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L411)

Switches PHP version for domain.




### ispmanager:domain-alias-create
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L480)

Creates new domain alias.




### ispmanager:domain-alias-delete
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L549)

Deletes domain alias.




### ispmanager:domain-delete
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L617)

Deletes domain.




### ispmanager:process
[Source](https://github.com/deployphp/deployer/blob/master/contrib/ispmanager.php#L664)

Auto task processing.




