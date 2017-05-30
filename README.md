# CHANGELOG:

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

