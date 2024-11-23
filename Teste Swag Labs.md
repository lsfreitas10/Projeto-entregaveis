# Testes - Swag Labs

### Funcionalidade: Login no Swag Labs

#### Cenário 1: Login bem-sucedido
- **Dado** que o usuário está na página de login  
- **Quando** ele faz login com "standard_user" e "secret_sauce"  
- **Então** ele deve ser redirecionado para a página inicial  
- **E** ver a lista de produtos  

#### Cenário 2: Login com nome de usuário incorreto
- **Dado** que o usuário está na página de login  
- **Quando** ele faz login com usuário inválido  
- **Então** ele deve ver uma mensagem de erro  

#### Cenário 3: Login com senha incorreta
- **Dado** que o usuário está na página de login  
- **Quando** ele faz login com a senha incorreta  
- **Então** ele deve ver uma mensagem de erro  

#### Cenário 4: Login com campos em branco
- **Dado** que o usuário está na página de login  
- **Quando** ele clica em "Login" sem preencher os campos  
- **Então** ele deve ver uma mensagem de erro  

### Funcionalidade: Navegação na Página Inicial

#### Cenário 5: Exibir lista de produtos após o login
- **Dado** que o usuário está logado  
- **Quando** ele acessa a página inicial  
- **Então** ele deve ver a lista de produtos  

#### Cenário 6: Exibir imagens e preços dos produtos
- **Dado** que o usuário está logado  
- **Quando** ele acessa a página inicial  
- **Então** ele deve ver imagens e preços dos produtos  

#### Cenário 7: Navegar entre páginas dos produtos
- **Dado** que o usuário está logado no Swag Labs e está na página inicial  
- **Quando** o usuário clica em um produto  
- **Então** ele deve ser redirecionado para a página do produto  

#### Cenário 8: Validar botão "voltar aos produtos"
- **Dado** que o usuário está na página de um produto específico  
- **Quando** o usuário clica no botão "voltar aos produtos"  
- **Então** ele deve ser redirecionado para a página inicial  
- **E** ver a lista de produtos  

#### Cenário 9: Validar o filtro de produtos em ordem alfabética crescente
- **Dado** que o usuário está logado no Swag Labs  
- **Quando** o usuário aplica o filtro "Nome (A ao Z)"  
- **Então** os produtos devem ser exibidos em ordem alfabética  

#### Cenário 10: Validar o filtro de produtos em ordem alfabética decrescente
- **Dado** que o usuário está logado no Swag Labs  
- **Quando** o usuário aplica o filtro "Nome (Z ao A)"  
- **Então** os produtos devem ser exibidos em ordem alfabética decrescente  

#### Cenário 11: Validar o filtro de produtos do preço mais barato ao mais caro
- **Dado** que o usuário está logado no Swag Labs  
- **Quando** o usuário aplica o filtro "Preço (mais barato ao mais caro)"  
- **Então** os produtos devem ser exibidos em ordem crescente de preço  

#### Cenário 12: Validar o filtro de produtos do preço mais caro ao mais barato
- **Dado** que o usuário está logado no Swag Labs  
- **Quando** o usuário aplica o filtro "Preço (mais caro ao mais barato)"  
- **Então** os produtos devem ser exibidos em ordem decrescente de preço  

#### Cenário 13: Validar funcionalidade do filtro de produtos 
- **Dado** que o usuário está logado no Swag Labs  
- **Quando** o usuário clica no filtro 
- **Então** as opções de filtros são apresentadas com sucesso

#### Cenário 14: Validar funcionalidade da opção All Items no menu 
- **Dado** que usuário está logado na Swag Labs
- **Quando**  usuário clica no menu
- **E** clica na opção All itens
- **Então** deve ser apresentado todos os itens da loja

#### Cenário 15: Validar funcionalidade da opção About no menu
- **Dado** que o usuário está logado no Swag Labs  
- **Quando** ele clica na opção About  
- **Então** ele é direcionado para a página sobre o Sauce Labs 

#### Cenário 16: Validar funcionalidade da opção Reset App State no menu
- **Dado**   que usuário está logado na Swag Labs
- **Quando**  usuário clica no menu
- **E** clica na opção Reset App State
- **Então** página deve ser resetada com sucesso

#### Cenário 17: Validar se Logout está sendo realizado com sucesso
- **Dado**   que usuário está logado na Swag Labs
- **Quando**  usuário clica no menu
- **E** clica na opção logout
- **Então** logout é realizado com sucesso

#### Cenário 18: Adicionar produto ao carrinho
- **Dado** que o usuário está logado no Swag Labs
- **Quando** o usuário adiciona um produto ao carrinho 
- **Então** o carrinho deve conter 1 item

#### Cenário 19: Adicionar múltiplos produtos ao carrinho
- **Dado**  que o usuário está logado no Swag Labs
- **Quando** o usuário adiciona multiplos produtos ao carrinho
- **Então** o carrinho deve conter todos itens que foram adicionados

#### Cenário 20: Remover produto do carrinho
- **Dado**   que o usuário adicionou um produto ao carrinho
- **Quando**  o usuário remove o produto
- **Então** o itém some do carrinho

#### Cenário 21: Verificar total de preço no carrinho
- **Dado**  que o usuário adicionou alguns produtos ao carrinho 
- **Quando** o usuário verifica o total no carrinho 
- **Então** o total deve refletir a soma dos preços dos produtos

#### Cenário 22: Navegar para a página de checkout a partir do carrinho
- **Dado**  que o usuário tem produtos no carrinho 
- **Quando** o usuário clica em "checkout" 
- **Então** o usuário deve ser redirecionado para a página de checkout

#### Cenário 23: Preencher os campos corretamente e clicar em "Continuar"
- **Dado** que o usuário está na etapa 1 do checkout  
- **Quando** o usuário preenche os campos "Nome", "Sobrenome" e "Código Postal" com informações válidas  
- **E** o usuário clica no botão "Continuar"
- **Então** o usuário deve ser redirecionado para a próxima etapa do checkout

#### Cenário 24: Deixar um campo vazio e tentar clicar em "Continuar"
- **Dado** que o usuário está na etapa 1 do checkout  
- **Quando** o usuário deixa um campo obrigatório vazio (Nome, Sobrenome ou Código Postal) 
- **E** o usuário clica no botão "Continuar"
- **Então** uma mensagem de erro deve ser exibida informando que todos os campos são obrigatórios

#### Cenário 25: Preencher os campos corretamente e clicar em "Cancelar"
- **Dado** que o usuário está na etapa 1 do checkout
- **Quando** o usuário preenche os campos "Nome", "Sobrenome" e "Código Postal" com informações válidas 
- **E** o usuário clica no botão "Cancelar"
- **Então** o usuário deve ser redirecionado de volta à página anterior ou à página inicial

#### Cenário 26: Preencher os campos com dados inválidos e clicar em "Continuar"
- **Dado**  que o usuário está na etapa 1 do checkout 
- **Quando**  o usuário preenche os campos "Nome", "Sobrenome" e "Código Postal" com informações inválidas
- **E** o usuário clica no botão "Continuar"
- **Então** uma mensagem de erro deve ser exibida informando que os campos estão preenchidos de maneira incorreta

#### Cenário 27: Validar finalizar uma compra sem nenhum produto
- **Dado** que usuário não adiciona nem um item no carrinho
- **Quando** ele tenta finalizar o pedido 
- **Então** pedido não pode ser finalizado

#### Cenário 28: Verificar resumo da compra e finalizar a compra
- **Dado** que o usuário está na etapa 2 do checkout  
- **Quando** o usuário visualiza o resumo dos itens, o preço total e as taxas
- **E** o usuário clica no botão "Finalizar" 
- **Então** o usuário deve ser redirecionado para a página de confirmação de compra

#### Cenário 29: Verificar resumo da compra e cancelar a compra
- **Dado** que o usuário está na etapa 2 do checkout
- **Quando** o usuário visualiza o resumo dos itens, o preço total e as taxas 
- **E** o usuário clica no botão "Cancelar" 
- **Então** o usuário deve ser redirecionado de volta à página de produtos ou ao carrinho 

#### Cenário 30: Compra realizada com sucesso e botão para voltar à tela inicial
- **Dado** que o usuário finalizou a compra com sucesso  
- **Quando** a tela de confirmação de compra for exibida 
- **Então** a mensagem de sucesso deve ser exibida
- **E** o botão "Voltar para a tela inicial" deve estar visível

#### Cenário 31: Validar se botão "Voltar para a tela inicial" redireciona o usuário corretamente
- **Dado** que o usuário completou a compra com sucesso  
- **Quando** o usuário clica no botão "Voltar para a tela inicial" 
- **Então** o usuário deve ser redirecionado para a página inicial da loja

#### Cenário 32: Validar a responsividade das telas em dispositivos móveis
- **Dado** que o usuário está utilizando um dispositivo mobile  
- **Quando** o usuário navega e realiza os fluxos no aplicativo
- **Então** as telas devem ajustar-se corretamente, mantendo a funcionalidade e a usabilidade esperadas."



---
## Tabela de Resultados dos Testes

| **ID** | **Nome do Teste**                                               | **Resultado** | **Link da Evidência**       |
|--------|----------------------------------------------------------------|---------------|-----------------------------|
| 1      | Login bem-sucedido                                             | ✅ Passou      | [Evidência](https://drive.google.com/file/d/16mcCkmh7yEyXI8b22KfsWruRsUmKmBtq/view?usp=sharing)              |
| 2      | Login com nome de usuário incorreto                            | ✅ Passou      | [Evidência](https://drive.google.com/file/d/16mcCkmh7yEyXI8b22KfsWruRsUmKmBtq/view?usp=sharing)              |
| 3      | Login com senha incorreta                                      | ✅ Passou      | [Evidência](https://drive.google.com/file/d/16mcCkmh7yEyXI8b22KfsWruRsUmKmBtq/view?usp=sharing)              |
| 4      | Login com campos em branco                                     | ✅ Passou      | [Evidência](https://drive.google.com/file/d/16mcCkmh7yEyXI8b22KfsWruRsUmKmBtq/view?usp=sharing)              |
| 5      | Exibir lista de produtos após o login                          | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1j2DMPRYSrWE9A2T3NpqTewMl88UV2pGg/view?usp=sharing)              |
| 6      | Exibir imagens e preços dos produtos                           | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1j2DMPRYSrWE9A2T3NpqTewMl88UV2pGg/view?usp=sharing)              |
| 7      | Navegar entre páginas dos produtos                             | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1j2DMPRYSrWE9A2T3NpqTewMl88UV2pGg/view?usp=sharing)              |
| 8      | Validar botão "voltar aos produtos"                            | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1j2DMPRYSrWE9A2T3NpqTewMl88UV2pGg/view?usp=sharing)              |
| 9      | Validar o filtro de produtos em ordem alfabética crescente     | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1rPipQgJlgJm0o6IOmsIbIauVcXzg-nF-/view?usp=sharing)              |
| 10     | Validar o filtro de produtos em ordem alfabética decrescente   | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1rPipQgJlgJm0o6IOmsIbIauVcXzg-nF-/view?usp=sharing)              |
| 11     | Validar o filtro de produtos do preço mais barato ao mais caro | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1rPipQgJlgJm0o6IOmsIbIauVcXzg-nF-/view?usp=sharing)              |
| 12     | Validar o filtro de produtos do preço mais caro ao mais barato | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1rPipQgJlgJm0o6IOmsIbIauVcXzg-nF-/view?usp=sharing)              |
| 13     | Validar funcionalidade do filtro de produtos                   | ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1rPipQgJlgJm0o6IOmsIbIauVcXzg-nF-/view?usp=sharing)              |
| 14     | Validar funcionalidade da opção All Items no menu              | ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1cLTtkE6Th5qZucfRhnfSptCVTS1UVNLh/view?usp=sharing)              |
| 15     | Validar funcionalidade da opção About no menu                  | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1cLTtkE6Th5qZucfRhnfSptCVTS1UVNLh/view?usp=sharing)              |
| 16     | Validar funcionalidade da opção Reset App State no menu        | ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1cLTtkE6Th5qZucfRhnfSptCVTS1UVNLh/view?usp=sharing)              |
| 17     | Validar se Logout está sendo realizado com sucesso             | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1qj6d8UuTMKEdH9Vhnl8to4bA5I136dl-/view?usp=sharing)              |
| 18     | Adicionar produto ao carrinho                                  | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1Vv-ilOkVOqIAwy32G3nfPL3eTpCYUwlx/view?usp=sharing)              |
| 19     | Adicionar múltiplos produtos ao carrinho                       | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1Vv-ilOkVOqIAwy32G3nfPL3eTpCYUwlx/view?usp=sharing)              |
| 20     | Remover produto do carrinho                                    | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1Vv-ilOkVOqIAwy32G3nfPL3eTpCYUwlx/view?usp=sharing)              |
| 21     | Verificar total de preço no carrinho                           | ✅ Passou      | [Evidência](https://drive.google.com/file/d/17UM9y3U8YxU2nNfTX06gcm3l8nj_LHz8/view?usp=sharing)              |
| 22     | Navegar para a página de checkout a partir do carrinho         | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1UnIILaoPTH6Sjn4dpjy3N2pDSmFfuZK_/view?usp=sharing)              |
| 23     | Preencher os campos corretamente e clicar em "Continuar"       | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1UnIILaoPTH6Sjn4dpjy3N2pDSmFfuZK_/view?usp=sharing)              |
| 24     | Deixar um campo vazio e tentar clicar em "Continuar"           | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1CZaUCg7U_pvNbRSQx4dmdhkAFnFHY1QN/view?usp=sharing)              |
| 25     | Preencher os campos corretamente e clicar em "Cancelar"        | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1KU6X78MhrX5_6XItpSnsp33p9g8kP6qt/view?usp=sharing)              |
| 26     | Preencher os campos com dados inválidos e clicar em "Continuar"| ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1QnI19fNFRFJ3Po5SyOL5vw86eggW4a11/view?usp=sharing)              |
| 27     | Validar finalizar uma compra sem nenhum produto                | ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1EqooRT2z2q2-bPDqTcOG8RnhFzcVCsIx/view?usp=sharing)              |
| 28     | Verificar resumo da compra e finalizar a compra                | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1UnIILaoPTH6Sjn4dpjy3N2pDSmFfuZK_/view?usp=sharing)              |
| 29     | Verificar resumo da compra e cancelar a compra                 | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1LrpH5yKMT7w4e2vZnp_f_XXzFVVz3iTK/view?usp=sharing)              |
| 30     | Compra realizada com sucesso e botão para voltar à tela inicial| ✅ Passou      | [Evidência](https://drive.google.com/file/d/1UnIILaoPTH6Sjn4dpjy3N2pDSmFfuZK_/view?usp=sharing)              |
| 31     | Validar se botão "Voltar para a tela inicial" funciona         | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1UnIILaoPTH6Sjn4dpjy3N2pDSmFfuZK_/view?usp=sharing)              |
| 32     | Validar a responsividade das telas em dispositivos móveis      | ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1msbMaCb8Wv-O134x2s9fVI1UsXLvtN0Z/view?usp=sharing)              |
---

## Lista de Bugs Encontrados

1. **Erro na funcionalidade da seta de filtros**: Ao clicar na seta para alternar os filtros, as opções de filtro não são exibidas como esperado. Apenas ao clicar diretamente no nome do filtro, as opções aparecem.
2. **Erro na opção "All Items" do menu**: Ao clicar na opção "All Items" no menu, o menu permanece visível e a página não é atualizada com todos os itens.
3. **Erro no "Reset App State"**: Após clicar em "Reset App State", os itens no carrinho são excluídos, mas o botão de "Remove" continua visível para os produtos que não estão mais no carrinho.
4. **Erro na finalização da compra sem produtos no carrinho**: O sistema permite que a compra seja finalizada mesmo sem produtos no carrinho.
5. **Erro ao preenche campos obrigatórios com dados inválidos**:Durante a etapa 1 do checkout, ao preencher os campos obrigatórios com dados inválidos, o sistema permite que a compra seja finalizada normalmente, sem apresentar um erro de validação.
6. **Erro de responsividade**: Na tela inicial, os preços dos produtos apresentam um espaço grande entre a foto do item e o valor exibido.

---

## Sugestões de Melhorias de UX/UI

1. **Adicionar opção de aumentar ou diminuir unidades dos itens no carrinho**: Facilita a experiência do usuário e melhora o fluxo de compra.
2. **Botão de Checkout desabilitado quando o carrinho estiver vazio**: Impede que o usuário tente finalizar uma compra sem itens no carrinho.
3. **Adicionar validações adicionais para dados inválidos**: Por exemplo, restringir o campo "Nome" para aceitar apenas letras e o campo "Código Postal" para aceitar apenas números. Isso pode evitar confusão e erros de preenchimento.

---

## Análise de Riscos

- **Risco 1**: A funcionalidade de filtros não responde corretamente, o que pode prejudicar a experiência do usuário ao tentar ordenar os produtos.
- **Risco 2**: A falta de validação nos campos do checkout pode levar a problemas de finalização de compras com dados inválidos.
- **Risco 3**: A finalização de compra sem produtos no carrinho pode gerar frustração no usuário, além de impactar a credibilidade da aplicação.



