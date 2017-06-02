# CHANGELOG:

## [UNRELEASED] ~~[v.0.5.3]~~ / 2017-05-30

### Added
- **PUT** de customer; operationID: **updateCustomer**
- Objeto *update_customer*

### Fixed
- Request *customer
    - Parâmetro ~~*customerID*~~ *customerKey* no path da request
    - operationID: **getCustomer*
- Objeto *get_customer*
    - Campos adicionados:
        - store_name    
        - customer_address_region_name
        - customer_status_lojamobly_name
    - Campos retirados:
        - id_customer_status
        - fk_customer

### Changed
- Objeto *customer* => *get_customer*
~~- Nome da request alterado de **customer** para **getCustomer**  ~~~
- 2 objects de *Customer*, nem tudo que é da via **BOB** para **SugarCRM** deve ser enviado na via contrária
- *customerID* to **customerKey**

## [v0.5.2] / 2017-05-25
### Deleted
- customer ~~~Dividido em customer customer_address~~

### Added
- customer
- customer_address
- itemsRecommended
  - Devido a necessidade de fixar o total da recomendação em 3 foi criado esse array para armazenar os objetos
- Enum de *fk_store*

### Fixed
- Adicionado patterns e formatos em alguns campos
- *sms_subscriptionn* corrigido para *sms_subscription*

### Changed
- Fixado o total de itens em recomendação para 3
- Alterado nome do objeto de *itemRecommended* para *itemsRecomendation*
- *bithdate* para *birthday*

## [v0.5.1] / 2017-05-25
### Fixed
- Fix em itemEvaluation

### Changed
- Alterado nome de get/itemEvaluation para get/orderRebate
- Alterado nome das propriedades que eram de itemEvaluation para refletir como orderRebate
- Alterado rebate_value para rebate
- Alterado de resp_order_item para rebate_order_item

