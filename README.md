A custom module for [julio.com](https://julio.com) (Magento 2).  

## How to install
```
bin/magento maintenance:enable
rm -rf composer.lock
composer clear-cache
composer require julio.com/core:*
bin/magento setup:upgrade
bin/magento cache:enable
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US es_MX
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Mgs/claue \
	-f en_US es_MX
bin/magento maintenance:disable
```

## How to upgrade
```
bin/magento maintenance:enable
composer remove julio.com/core
rm -rf composer.lock
composer clear-cache
composer require julio.com/core:*
bin/magento setup:upgrade
bin/magento cache:enable
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US es_MX
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Mgs/claue \
	-f en_US es_MX
bin/magento maintenance:disable
```

If you have problems with these commands, please check the [detailed instruction](https://mage2.pro/t/263).