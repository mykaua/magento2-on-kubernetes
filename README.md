# magento2-on-kubernetes
magento2 on kubernetes


Version magento 2.3

Copy from https://github.com/KiweeEu/magento2-on-kubernetes

k8s secure has to be added 


bin/magento module:status
bin/magento module:enable --all


Deploy static has to be run on build.

Two commands:
bin/magento setup:di:compile
bin/magento setup:static-content:deploy -f


```bin/magento setup:di:compile``` - completes successfully.
```bin/magento setup:static-content:deploy -f``` -  has the issues.

The issues, like:
```
Compilation from source /var/www/html/vendor/magento/module-usps/view/frontend/web/js/model/shipping-rates-validation-rules.js failed
DomainException: The default website isn't defined. Set the website and try again
```
It means, the modules require url, maybe, database.

Documentation:

https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/static-view/static-view-file-deployment.html

