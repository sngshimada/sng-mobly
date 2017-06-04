## Campos retirados
- id_customer:
- fk_store:
- store_name:
- tax_identification:
- company_tax_identification:
- created_at

Pontos de discussão:

Se consideramos o CPF/CNPJ como a chave única para comunicação entre os sitemas, não podemos liberar esse campo para edição e consequentemente o mesmo tambpem não deveria ser enviado na atualização do customer.

Data de criação; não será atualizada

Busca e atualização de customer, chave principal CPF e CNPJ

## Campos de Sugar -> Bob
- type, qual é 1 e qual é 2
- is_confirmed?
- customer_address_region_name; vai precisar de um dropdown com o que existe cadastrado no BOB
- sms_subscription, 0 = Não e 1 = Sim?
- enable_oneclickbuy
-  

## Address

###  BOB -> Sugar
- fk_country_name
- esse campo para trazer o nome e não um número
- confirmar, qual o 0 e 1 de is_default_billing e is_default_shipping

### Sugar -> BOB
- created_at uma lógica simples de se não existir no banco usar o updated_at como data de criação

###  consulta customer

- crm consulta
- crm envia o cpf/cnpj
- bob busca na base o cpf/cnpj
    - 1 - bob retorna
        - dados do customer + endereços
    - 2 - bob retorna dados do customer

###  consulta endereço

- crm consulta
- crm envia o cpf/cnpj
- bob busca na base o cliente
- bob pega o id -> x
- bob busca na base de endereços todos com fk_customer = x
- bob retorna lista de endereços