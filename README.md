# Ex6_DbCompatibility

Magento 2 module that extends the list of database version patterns Magento
recognizes as supported, via `Magento\Framework\DB\Adapter\SqlVersionProvider`.

By default, Magento's core version check does not recognize MariaDB 11.x (or
newer MySQL 8 releases) as supported, which can trigger a false
"unsupported database" warning. This module patches the accepted version
patterns to include:

- MySQL 8.x
- MySQL 5.7.x
- MariaDB 10.2 - 10.11
- MariaDB 11.x

## Installation

Copy the `Ex6/DbCompatibility` directory into your Magento installation's
`app/code/` directory, then run:

```
bin/magento module:enable Ex6_DbCompatibility
bin/magento setup:upgrade
```

## Structure

```
Ex6/DbCompatibility/
├── etc/
│   ├── di.xml        # Registers supported DB version patterns
│   └── module.xml    # Module declaration
└── registration.php  # Module registration
```
