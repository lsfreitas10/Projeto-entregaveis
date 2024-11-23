# Teste API

## 1. Gerar token com credenciais válidas
- **Dado** que eu tenho credenciais válidas  
- **Quando** eu envio uma requisição POST para "/auth"  
- **Então** a resposta deve ter status 200  
- **E** o corpo deve conter o campo "token"  

## 2. Gerar token com credenciais inválidas (Falhou)
- **Dado** que eu tenho credenciais inválidas  
- **Quando** eu envio uma requisição POST para "/auth"  
- **Então** a resposta deve ter status 401  
- **E** a mensagem de erro deve ser "Credenciais inválidas"  

## 3. Buscar reservas por nome e sobrenome
- **Dado** que estou autenticado com token válido  
- **Quando** eu envio uma requisição GET para "/booking" com filtro de "nome" e "sobrenome"  
- **Então** a resposta deve ter status 200  
- **E** o corpo deve conter reservas filtradas  

## 4. Buscar reserva por ID
- **Dado** que estou autenticado com token válido  
- **Quando** eu envio uma requisição GET para "/booking/{id}"  
- **Então** a resposta deve ter status 200  
- **E** o corpo deve conter a reserva com o ID especificado  

## 5. Criar uma reserva com dados válidos
- **Dado** que estou autenticado com token válido  
- **Quando** eu envio uma requisição POST para "/booking" com dados válidos  
- **Então** a resposta deve ter status 200  
- **E** o corpo deve conter os dados da reserva criada  

## 6. Criar uma reserva com dados inválidos (Falhou)
- **Dado** que estou autenticado com token válido  
- **Quando** eu envio uma requisição POST para "/booking" com dados inválidos  
- **Então** a resposta deve ter status 400  
- **E** o corpo deve conter erro indicando dados inválidos  

## 7. Atualizar informações da reserva
- **Dado** que estou autenticado com token válido  
- **E** eu tenho uma reserva com o ID  
- **Quando** eu envio uma requisição PUT para "/booking/{id}" com novos dados  
- **Então** a resposta deve ter status 200  
- **E** o corpo deve conter os dados atualizados  

## 8. Atualizar nome e sobrenome
- **Dado** que estou autenticado com token válido  
- **E** eu tenho uma reserva com o ID {id}  
- **Quando** eu envio uma requisição PUT para "/booking/{id}" com novo nome e sobrenome  
- **Então** a resposta deve ter status 200  
- **E** o corpo deve conter o novo nome e sobrenome  

## 9. Deletar uma reserva (Falhou)
- **Dado** que estou autenticado com token válido  
- **E** eu tenho uma reserva com o ID {id}  
- **Quando** eu envio uma requisição DELETE para "/booking/{id}"  
- **Então** a resposta deve ter status 200  
- **E** o corpo deve conter a mensagem "Reserva deletada"  

---

# Tabela de Resultados dos Testes

| **ID** | **Nome do Teste**                            | **Resultado** | **Link da Evidência**   |
|--------|----------------------------------------------|---------------|--------------------------|
| 1      | Gerar token com credenciais válidas          | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1iDQB_tzhkcijVwbjP0o0YUuubpnGiSbq/view?usp=sharing)           |
| 2      | Gerar token com credenciais inválidas        | ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1fkD_r1mnSAufLSbCJcCryFHUSjP8NOHE/view?usp=sharing)           |
| 3      | Buscar reservas por nome e sobrenome         | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1E2vovDqoDeo0_1_A9GUirTO3nZC9SjO7/view?usp=drive_link)           |
| 4      | Buscar reserva por ID                        | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1SZ3iF1BQXgzyJl_nd8RpzxTTPP_YjyS7/view?usp=sharing)           |
| 5      | Criar uma reserva com dados válidos          | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1V7L5EcmnvKHpaBARuKSiwzm6VPf50v5W/view?usp=sharing)           |
| 6      | Criar uma reserva com dados inválidos        | ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1VLLznbSufEi3C9j-3BsMIztcd4wRnbBC/view?usp=sharing)           |
| 7      | Atualizar informações da reserva             | ✅ Passou      | [Evidência](https://drive.google.com/file/d/1q2Z3T1HdQgYo0fLJbUJe00XBIHTM1GsM/view?usp=sharing)           |
| 8      | Atualizar nome e sobrenome                   | ✅ Passou      | [Evidência](https://drive.google.com/file/d/12SYMv4-g08FlqPJcOB3Ikz5qwAPYstOu/view?usp=sharing)           |
| 9      | Deletar uma reserva                          | ❌ Falhou      | [Evidência](https://drive.google.com/file/d/1tcve1rNhLiFWsATZkEoY6nr8VSAxC6FR/view?usp=sharing)           |

---

Arquivo Json com testes [Evidência](https://drive.google.com/file/d/1BBpPocOiT5SOXWN38doPJJUGux_o6z0R/view?usp=sharing)

---

## Lista de Bugs Encontrados

1. **Erro credenciais inválidas na geração de token**: após colocar credenciais inválidas é apresentado 200, mesmo a mensagem sendo bad credentials
2. **Erro ao criar reserva com dados inválidos**: Ao inserir caracteres especiais no campo nome e uma data inexistente ao criar uma reserva, a resposta retornada é 200 ao invés de 400.
3. **Erro ao deletar reserva**: Após deletar uma reserva, a resposta retornada é 201 (Created) ao invés de 200 (OK).

---

## Análise de Riscos

**1. Gerar token com credenciais inválidas retorna 200**
- **Risco**: Pode levar a interpretações erradas por clientes ou sistemas que consomem a API. Eles podem acreditar que o login foi bem-sucedido, mesmo que o token seja inválido.
**2. Criar uma reserva com dados inválidos retorna 200**
- **Risco**: Aceitar dados inválidos compromete a integridade do banco de dados e pode causar falhas em outros sistemas dependentes.
**3. Deletar uma reserva retorna 201 (Created)**
- **Risco**: O código de status incorreto pode confundir os consumidores da API, levando-os a tentar repetidamente realizar um processo que deveria ser simples e eficiente.
