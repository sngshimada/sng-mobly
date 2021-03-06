# CHANGELOG:

## UNRELEASED ~~[v.0.8.0] / 2017-07-04~~

### Added
- tag: searches
- operações:
    - **getCustomerFiltered**
    - **getSaleOrderFiltered**

## [v.0.7.2] / 2017-06-12

### Added
- *coleta_orderItens*

### Deleted
- *itens_simulados

### Changed
- *coleta_novas_datas*
    - relacionado *coleta_orderItens*
- *post_coleta_nova_data*
    - relacionado *coleta_orderItens*
- *cancela_coleta*
    - relacionado *coleta_orderItens*
- *itens_a_coletar*
    -  Refatorado 

## [v.0.7.1] / 2017-06-04

### Added
- Criada tag *rebate*, adicionada nas requests específicas

### Fixed
- Adicionado "usuario_crm" em postAprovacaoColeta

### Changed
- Busca por produtos
    - Sem parâmetro no path, somente na query
    - Parâmetro indicando o tipo de resposta esperada
- postSimulaColeta - items_evaluation_response
    - retirado *ocorrencia_crm* da response
    - retirado *message* da response 
- *solicita_response*
    - adicionado *queue_id*
- *aprovacao_coleta*
    - adicionado *queue_id*  
    - adicionado *numero_volumes_coletar*
- ~~*coleta_nova_data*~~
    - ~~adicionado *queue_id*~~
- *order_evaluated*
    - adicionado *usuario_crm*
- *rebate_order_items* 
    - *order_items_evaluation*

## [v.0.7.0] / 2017-06-04

### Added

- Adicionado objetos
    - items_evaluation
    - order_items_evaluation
    - items_evaluation_response
    - datas_coleta
    - evaluated_item_reccomendation
    - itens_a_coletar
    - aprovacao_coleta
- Adicionado request
    - postSimulaColeta
    - postSolicitaColeta
    - postAprovacaoColeta
- Adicionada tag
    - reversa  


## [v.0.6.0] / 2017-06-04

### Added
- Tags *asyncronous*,*syncronous*,*product*
- Adicionada as tags novas nas requests
- Adicionado objeto *addresses* 
- Adicionado chave de indentificação da fila em:
    - *update_customer_address*
    - *update_customer* 
    - *get_customer* [tbd]
    - *get_customer_address* [tbd]
- **Adicionado objeto** ***product***
- **Adiconada request** ****getProductSKU****

### Changed
- No retorno pode vir mais de um endereço por cliente, alterado o objeto *get_customer_address*
- Marcado como deprecated:
    - updateCustomer
    - updateCustomerAddress
        - update será feito por fila 
    - getCustomer
    - getCustomerAddress
        - busca já existe, passará por planning novamente, se for aprovado pode ser reutilizada essas requests 
    

## [v.0.5.4] / 2017-06-02

### Added
- Objeto *update_customer_address*
- ~~Request *updateCustomerAddress*~~
    - Marcado como deprecated, suprimir a mensagem de erro e guardar o objeto 

### Deleted
- Retirado ~~suppressed~~ de *update_customer*
    - fk_customer_address_region
    - fk_customer_status_lojamobly
    - fk_customer_status
- Retirado ~~suppressed~~ de *update_customer_address* [validar]
    - fk_customer
    - fk_country
    - fk_customer_address_region
    - created_at
    - id_customer_address_region
    - customer_address_fk_country

### Fixed
- Adicionado os campos em *update_customer*

### Changed
- *updateCustomer* marcada como Deprecated, a atualização será por fila e não terá uma request
- Requests com tag de *customerID* atualizados o parâmetro para *customerKey*
- Adicionado campo *code_address*~~definir nome e formato~~ em *get_customer_address*
- *customer_address* alterado para *get_customer_address*


## [v.0.5.3] / 2017-05-30

### Added
- **PUT** de customer; operationID: **updateCustomer**
- Objeto *update_customer*

### Fixed
- Request *customer*
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
~~Nome da request alterado de **customer** para **getCustomer**~~
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