# Template CheckSSL Days Valid

Template for monitoring and alert before a SSL certificate for a given site is about to expire.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development, testing and production purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to run the scripts and commands. (Consult the documentation of your system to install dependencies if is not already installed on in your system.)

```
sed
openssl
```

### Installing

Clone the repository to your machine, and enter in it. After, create a "scripts" folder in your zabbix-agent configuration folder. Example: (Default in linux: /etc/zabbix/. Change accordingly with your OS default.)

```
mkdir /etc/zabbix/scripts
```

Then, copy the script to te folder. Example:

```
cp ./Template_CheckSSL_Days_Valid/scripts/checkssl.sh /etc/zabbix/scripts/
```
Copy the userparameters file to the zabbix_agentd.d folder. Example:

```
cp ./Template_CheckSSL_Days_Valid/userparameter_checkssl_days_valid.conf /etc/zabbix/zabbix_agentd.d/
```
Restart the zabbix-agent in your system. Example: (Debian like systems.) 

```
/etc/init.d/zabbix-agent restart
```

After that, import the template file "Template_CheckSSL_Days_Valid.xml" in your zabbix server frontend, and see your recent data coming.


## Details about Deployment

The Zabbix template has 1 item in the userparameter file. Details about below:
// userparameter_checkssl_days_valid.conf
* checkssl[dns] - Return the days that left to SSL Certificate expire.

The template and item need to be configured in the host that will do the test in the respective site. I tested using the Zabbix agent in Zabbix Server host itself. The template has 4 triggers, that 
beginning alert for the expire when left 90, 60, 30, 14 and 7 days.


## Built With

* [Zabbix 4.2](https://www.zabbix.com/documentation/4.2/manual) - The IT monitoring tool 
* [OpenSSL](https://github.com/openssl/openssl/) - OpenSSL is a robust, commercial-grade, full-featured Open Source Toolkit for the Transport Layer Security (TLS) protocol formerly known as the Secure Sockets Layer (SSL) protocol.

## Authors

* **Caio Jorge** -  [Cacohh](https://github.com/Cacohh/)