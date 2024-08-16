
# Docker compose for the shops Mondu has plugins for


### Supported shops
- Shopware5
- Shopware6
- JTL store 5
- Magento 2
- Woocommerce ( wordpress )
- Oxid
### TODO

- Oxid

### Use guide

#### Requirements

- Docker
- docker-compose

#### Tested on
Macos 14.1, apple silicone, Docker version 25.0.2, Docker Compose version v2.24.3-desktop.1

#### Setup

First of all, make sure that port 80 is not used by any process on your machine.

Clone the repository and run this command at the root directory.

    docker-compose up

After it finished run the following command at the root directory.

    ./commands/install

After it finishes add following lines to your /etc/hosts

    127.0.0.1 magento.local
    127.0.0.1 shopware5.local
    127.0.0.1 shopware6.local
    127.0.0.1 jtl5.local
    127.0.0.1 woocommerce.local
    127.0.0.1 oxid.local

Navigate to any shop and finish the setup. (make sure to use http not https)

Also there is phpmyadmin included, so you can access the database using http://localhost:8081/ URL
#### Note
Plugins currently do not come pre-installed

#### TODO

Support all the shops
Pre-install plugins and pre-configure shops
