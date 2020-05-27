---
group: cloud-guide
title: Error message reference for ece-tools
---

{% assign errors = site.data.cloud-error-messages %}

This {{site.data.var.ct}} error message reference provides information to resolve errors that occur during the {{site.data.var.ece}} deployment process.

Error messages are categorized by deployment stage–build, deploy, and post-deploy. Each section provides a list of associated errors with the following information for each error:

-  **Error code**:  The Magento-assigned identifier for the error message
-  **Step**:  Indicates the step in the deployment scenario where the error can occur. If the _Step_ column is blank, the error is a general error that can occur in multiple steps, or during pre-processing operations. See [Scenario-based deployment]({{site.baseurl}}/cloud/deploy/scenario-based-deployment.html).
-  **Error description**: A short phrase that summarizes the cause of the error
-  **Suggested action**: Provides guidance to troubleshoot and resolve the error

## Build stage

| Error code | Build step | Error description | Suggested action |
| --- | --- | --- | -- |
| 2 | | File `./app/etc/env.php` is not writable | {{site.data.cloud-error-messages.ENV_PHP_IS_NOT_WRITABLE}}|
| 3 | | Configuration isn't defined in schema.yaml | {{site.data.cloud-error-messages.CONFIG_NOT_DEFINED}}|
| 4 | | Failed to parse .magento.env.yaml | {{site.data.cloud-error-messages.CONFIG_PARSE_FAILED}}|
| 5 | | Unable to read .magento.env.yaml | {{site.data.cloud-error-messages.CONFIG_UNABLE_TO_READ}}|
| 6 | | Unable to read .schema.yaml | |
| 7 | refresh-modules | File `./app/etc/config.php` is not writable |{{site.data.cloud-error-messages.CONFIG_PHP_IS_NOT_WRITABLE}} |
| 8 | validate-config | Unable to read composer.json |{{site.data.cloud-error-messages.CANT_READ_COMPOSER_JSON}} |
| 9 | validate-config | Composer.json missed required autoload section | {{site.data.cloud-error-messages.COMPOSER_MISSED_REQUIRED_AUTOLOAD}} |
| 10 | validate-config | The file `.magento.env.yaml` contains an option which isn't declared in the schema, or has an invalid value or stage | {{site.data.cloud-error-messages.WRONG_CONFIGURATION_MAGENTO_ENV_YAML}}|
| 11 | refresh-modules | Command `/bin/magento module:enable --all` failed | {{site.data.cloud-error-messages.CLOUD_LOG_VERBOSE_ACTION}} |
| 12 | apply-patches | Patch applying failed | |
| 13 | set-report-dir-nesting-level | Can't write to the file /pub/errors/local.xml | |
| 14 | copy-sample-data | Failed to copy sample data files | |
| 15 | compile-di | Command `/bin/magento setup:di:compile` failed | |
| 16 | dump-autoload | Command `composer dump-autoload` failed | {{site.data.cloud-error-messages.COMPOSER_DUMP_AUTOLOAD_FAILED}} |
| 17 | run-baler | The command to run `Baler` for Javascript bundling failed | {{site.data.cloud-error-messages.BALER_NOT_FOUND}} |
| 18 | compress-static-content | Required utility wasn't found (timeout, bash) | {{site.data.cloud-error-messages.UTILITY_NOT_FOUND}} |
| 19 | deploy-static-content | Command `/bin/magento setup:static-content:deploy` failed | {{site.data.cloud-error-messages.CLOUD_LOG_VERBOSE_ACTION}} |
| 20 | compress-static-content | Static content compression failed | {{site.data.cloud-error-messages.CHECK_CLOUD_LOG_ACTION}} |
| 21 | backup-data: static-content | Failed to copy static content into the `init` directory | {{site.data.cloud-error-messages.CHECK_CLOUD_LOG_ACTION}} |
| 22 | backup-data: writable-dirs | Failed to copy some writable directories into the `init` directory | {{site.data.cloud-error-messages.WRITABLE_DIRECTORY_COPYING_FAILED}} |
| 23 | | Unable to create a logger object | |
| 24 | backup-data: static-content | Failed to clean the `./init/pub/static/` directory | {{ site.data.cloud-error-messages.CLEAN_INIT_PUB_STATIC_FAILED}} |
| 25 | | Cannot find the Composer package | {{site.data.cloud-error-messages.COMPOSER_PACKAGE_NOT_FOUND}} |

## Deploy stage

| Error code | Deploy step | Error description | Suggested action |
| --- | --- | --- | -- |
| 101 | pre-deploy: cache | Incorrect cache configuration (missing port or host) | {{site.data.cloud-error-messages.WRONG_CACHE_CONFIGURATION}} |
| 102 | | File `./app/etc/env.php` is not writable | {{site.data.cloud-error-messages.ENV_PHP_IS_NOT_WRITABLE}} |
| 103 | | Configuration isn't defined in the `schema.yaml` file  | |
| 104 | | Failed to parse the `.magento.env.yaml` file | {{site.data.cloud-error-messages.CONFIG_NOT_DEFINED}} |
| 105 | | Unable to read the `.magento.env.yaml` file | {{site.data.cloud-error-messages.CONFIG_UNABLE_TO_READ}} |
| 106 | | Unable to read the `.schema.yaml` file | |
| 107 | pre-deploy: clean-redis-cache | Failed to clean the Redis cache | {{site.data.cloud-error-messages.
REDIS_CACHE_CLEAN_FAILED}} |
| 108 | pre-deploy: set-production-mode | Command `/bin/magento maintenance:enable` failed | {{site.data.cloud-error-messages.CLOUD_LOG_VERBOSE_ACTION}} |
| 109 | validate-config | Incorrect database configuration | {{site.data.cloud-error-messages.WRONG_CONFIGURATION_DB}} |
| 110 | validate-config | Incorrect session configuration | {{site.data.cloud-error-messages.WRONG_CONFIGURATION_SESSION}} |
| 111 | validate-config | Incorrect search configuration | {{site.data.cloud-error-messages.WRONG_CONFIGURATION_SEARCH}} |
| 112 | validate-config | Incorrect resource configuration | {{site.data.cloud-error-messages.WRONG_CONFIGURATION_RESOURCE}} |
| 113 | validate-config:elasticsuite-integrity | ElasticSuite is installed, but the ElasticSearch service is not available | {{site.data.cloud-error-messages.ELASTIC_SUITE_WITHOUT_ES}} |
| 114 | validate-config:elasticsuite-integrity | ElasticSuite is installed, but another search engine is used | {{site.data.cloud-error-messages.ELASTIC_SUITE_WRONG_ENGINE}} |
| 115 |  | Database query execution failed | |
| 116 | install-update: setup | Command `/bin/magento setup:install` failed | {{site.data.cloud-error-messages.INSTALL_UPGRADE_ACTION}} |
| 117 | install-update: config-import | Command `app:config:import` failed | {{site.data.cloud-error-messages.INSTALL_UPGRADE_ACTION}} |
| 118 |  | Required utility wasn't found (timeout, bash) | {{site.data.cloud-error-messages.UTILITY_NOT_FOUND}} |
| 119 | install-update: deploy-static-content | Command `/bin/magento setup:static-content:deploy` failed | {{site.data.cloud-error-messages.CLOUD_LOG_VERBOSE_ACTION}} |
| 120 | compress-static-content | Static content compression failed | {{site.data.cloud-error-messages.CHECK_CLOUD_LOG_ACTION}} |
| 121 | deploy-static-content:generate | Cannot update the deployed version | {{site.data.cloud-error-messages.SCD_UNABLE_UPDATE_VERSION}} |
| 122 | clean-static-content | Failed to clean static content files | |
| 123 | install-update: split-db | Command `/bin/magento setup:db-schema:split` failed | {{site.data.cloud-error-messages.CLOUD_LOG_VERBOSE_ACTION}} |
| 124 | clean-view-preprocessed | Failed to clean the `var/view_preprocessed` folder | {{site.data.cloud-error-messages.VIEW_PREPROCESSED_CLEAN_FAILED}} |
| 125 | install-update: reset-password | Failed to update the `/var/credentials_email.txt` file | {{site.data.cloud-error-messages.FILE_CREDENTIALS_EMAIL_NOT_WRITABLE}} |
| 126 | install-update: update | Command `/bin/magento setup:upgrade` failed | |
| 127 | clean-cache | Command `/bin/magento cache:flush` failed | {{site.data.cloud-error-messages.CLOUD_LOG_VERBOSE_ACTION}} |
| 128 | disable-maintenance-mode | Command `/bin/magento maintenance:disable` failed | |
| 129 | install-update: reset-password | Enable to read reset password template | |

## Post-deploy stage

| Error code | Post-deploy step | Error description | Suggested action |
| --- | --- | --- | -- |
| 201 | is-deploy-failed | Deploy stage failed | |
| 202 |  | The `./app/etc/env.php` file is not writable | {{site.data.cloud-error-messages.ENV_PHP_IS_NOT_WRITABLE}} |
| 203 |  | Configuration isn't defined in the `schema.yaml` file | {{site.data.cloud-error-messages.CONFIG_NOT_DEFINED}} |
| 204 |  | Failed to parse the `.magento.env.yaml` file | |
| 205 |  | Unable to read the `.magento.env.yaml` file | {{site.data.cloud-error-messages.CONFIG_UNABLE_TO_READ}} |
| 206 |  | Unable to read the `.schema.yaml` file | |
| 207 | warm-up | Failed to warm-up some pages | |
| 208 | time-to-firs-byte | Failed to test time to first byte (TTFB) | |
| 227 | clean-cache | Command `/bin/magento cache:flush` failed | {{site.data.cloud-error-messages.CLOUD_LOG_VERBOSE_ACTION}} |

<!--Link definitions-->

[Scenario-based deployment]: {{site.baseurl}}/cloud/deploy/scenario-based-deployment.html
