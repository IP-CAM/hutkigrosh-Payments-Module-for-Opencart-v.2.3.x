## Module for integration with CMS OpenCart 2.3.x

This module provides interaction between the online store based on CMS Opencart version 2.3.x and the payment service hutkigrosh.by
  * Integration module for version [OpenCart 1.5.x] (https://github.com/esasby/hutkigrosh-opencart1.5-module)
  * Integration module for version [OpenCart 2.1.x] (https://github.com/esasby/hutkigrosh-opencart2.1-module)
  * Integration module for version [OpenCart 2.2.x] (https://github.com/esasby/hutkigrosh-opencart2.2-module)
  * Integration module for version [OpenCart 3.0.x] (https://github.com/esasby/hutkigrosh-opencart3.0-module)

### Requirements ###
1. PHP 5.6 and higher
1. Curl library

### Installation Instructions:
1. Create a backup of your store and database
1. Install the module [opencart23-hutkigrosh-payment-module.ocmod.zip] (https://github.com/esasby/hutkigrosh-opencart2.3-module/blob/master/opencart23-hutkigrosh-payment-module.ocmod. zip) using _Modules_ -> _Installing Extensions_
1. Opposite the module HutkiGrosh, click "Install"

## Setup Instructions
1. Go to plugin settings via __Modules -> Payments__
1. Opposite the HutkiGrosh module, click "Change".
1. Specify the required parameters
    * Login online store - login in the HutkiGrosh system.
    * Online store password - password in the HutkiGrosh system.
    * Unique identifier of the ERIP service - ID of the ERIP service
    * Service code - service code in the ERIP tree. Used when generating QR code
    * Sandbox - putting the module into test mode. In this mode, invoices are issued to the test system wwww.trial.hgrosh.by
    * Email notification - enable notification of the client by email upon successful invoicing (performed by the Hutkigrosh gateway)
    * Sms notification - enable informing the client by SMS upon successful invoicing (performed by the Hutkigrosh gateway)
    * Path in the ERIP tree - the path for paying the invoice in the ERIP tree, which will be shown to the client after placing an order (for example, Payments> Store> Orders)
    * Account expiration date - how long the account will be available in ERIP for payment
    * Status when invoicing - what status to set the order upon successful invoicing in ERIP (identifier of the existing status from Store> Settings> Statuses)
    * Status upon successful payment of the invoice - what status to set the order upon successful payment of the invoice (identifier of the existing status)
    * Status when invoice payment is canceled - what is the status to set for the order when invoice payment is canceled (identifier of the existing status)
    * Status in case of an invoice payment error - what status to issue an order in case of an invoice error (identifier of the existing status)
    * Section "Instructions" - if enabled, then on the final screen the client will have access to step-by-step instructions on how to pay an invoice to the ERIP
    * QR-code section - if enabled, the client will be able to pay the bill by QR code on the final screen
    * Alfaclick section - if enabled, a button for invoicing in Alfaclick will be displayed to the client on the final screen
    * Webpay section - if enabled, the final screen will display the button for paying the bill by card (go to Webpay)
    * Successful billing text - the text displayed to the customer after successful billing. May contain html. In the text, it is permissible to refer to variables @order_id, @order_number, @order_total, @order_currency, @order_fullname, @order_phone, @order_address
1. Save your changes.

### Attention!
* To automatically update the status of the order (after the client has paid the invoice issued to the ERIP), you must inform the technical support service of the "Hutki Grosh" service with the address of the processor:
    ``,
    http://mydomen.my/index.php?route=extension/payment/hutkigrosh/notify
    ``,
* The module keeps a log file along the path _site_root / upload / system / library / esas / vendor / esas / hutkigrosh-api-php / logs / hutkigrosh.log_
To ensure ** security **, you need to make sure that the _AllowOverride All_ directive for the root folder is enabled in the http server settings.

### Test data
To set up payment in test mode
 * use the data to connect to the test system obtained during registration in HutkiGrosh
 * enable the "Sandbox" mode in the module settings
 * to emulate the payment by the client of the invoice, use the personal account of the [test system] (https://trial.hgrosh.by) (menu _ ERIP payment test_)

_Developed and tested with OpenCart v.2.3.0.2

