# Aprendizados — WireMock e Postman

Este documento reúne os principais conhecimentos aprendidos durante a prática do projeto de Mock da QAZANDO.

---

## 1. O que é o WireMock?

O WireMock é uma ferramenta utilizada para criar **mocks de APIs**.

De forma simples, um mock é uma simulação de uma API.

Neste projeto, o WireMock simula uma API de cadastro de veículos para que possamos realizar testes sem utilizar uma API real.

O fluxo funciona da seguinte forma:

**Postman → WireMock → Resposta configurada**

---

## 2. Como executar o WireMock

Para executar o projeto, é necessário ter o Java instalado.

Para verificar a versão do Java:

`java -version`

Neste projeto foi utilizado o Java 11.

Para iniciar o WireMock:

`java -jar wiremock-standalone-3.9.1.jar`

Por padrão, o WireMock utiliza a porta **8080**.

Caso a porta 8080 esteja ocupada ou apresente algum erro, podemos utilizar outra porta.

Neste projeto foi utilizada a porta **1010**:

`java -jar wiremock-standalone-3.9.1.jar --port=1010`

Após iniciar, o WireMock estará disponível em:

`http://localhost:1010`

---

## 3. Cenários praticados

O projeto possui uma API simulada de carros.

Os cenários são configurados no WireMock utilizando os arquivos de **mappings**.

### Buscar veículos

Método:

`GET`

Endpoint:

`/api/cars`

Resultado esperado:

`200`

### Cadastrar um Fusca

Método:

`POST`

Endpoint:

`/api/cars`

Quando o campo `model` é:

`fusca`

O WireMock retorna:

`201`

### Cadastrar um Up TSI

Método:

`POST`

Endpoint:

`/api/cars`

Quando o campo `model` é:

`up tsi`

O WireMock retorna:

`500`

Nesse cenário, o `500` é o resultado esperado porque esse comportamento foi configurado no mock.

---

## 4. Utilização do Postman

Utilizei o Postman para enviar as requisições para o WireMock.

A Collection utilizada neste projeto possui os seguintes cenários:

- busca veiculo
- criando veiculo
- criando veiculo - erro 500

---

## 5. Cadastro de veículo — cenário de sucesso

Requisição:

`POST http://localhost:1010/api/cars`

Body:

    {
        "brand": "Volkswagen",
        "model": "fusca",
        "year": 1965
    }

Resultado esperado:

`201`

---

## 6. Cadastro de veículo — cenário de erro

Requisição:

`POST http://localhost:1010/api/cars`

Body:

    {
        "brand": "Volkswagen",
        "model": "up tsi",
        "year": 2019
    }

Resultado esperado:

`500`

É importante entender que o `500` nesse caso não significa que o teste necessariamente falhou.

Como o cenário foi configurado para retornar `500`, devemos comparar o resultado esperado com o resultado recebido.

Exemplo:

**Esperado:** 500

**Recebido:** 500

**Resultado:** PASS

---

## 7. O que aprendi como QA

Durante essa prática, aprendi a:

- Utilizar um Mock para simular uma API;
- Executar o WireMock;
- Configurar a porta utilizada pelo WireMock;
- Entender o funcionamento básico dos mappings;
- Criar e executar requisições no Postman;
- Trabalhar com diferentes massas de teste;
- Trabalhar com cenários de sucesso e erro;
- Comparar o resultado esperado com o resultado recebido.

---

## 8. Conceitos de testes de performance

Durante os estudos também tive contato com alguns conceitos de testes de performance.

### Fixed

Mantém uma quantidade fixa de usuários ou requisições durante determinado período.

Exemplo:

**5 usuários realizando 5 requisições por segundo durante determinado período.**

### Ramp Up

Aumenta a quantidade de usuários ou requisições gradualmente.

Exemplo:

**10 → 20 → 50 → 100 usuários**

### Spike

Aumenta a quantidade de usuários ou requisições rapidamente.

Exemplo:

**10 → 500 usuários**

### Peak

Representa um momento de carga muito alta, próximo do maior volume esperado.

Esses conceitos fazem parte dos meus estudos iniciais sobre testes de performance.

---

## 9. Git e GitHub

Também pratiquei o uso do Git para versionar o projeto e enviar minhas alterações para o GitHub.

Alguns comandos utilizados:

### Verificar o status do projeto

`git status`

### Verificar os repositórios remotos

`git remote -v`

### Adicionar alterações

`git add .`

### Criar um commit

`git commit -m "mensagem do commit"`

### Enviar alterações para o GitHub

`git push`

Neste projeto utilizei:

- **origin** → meu repositório no GitHub
- **upstream** → repositório original da QAZANDO

---

## 10. Resumo do aprendizado

Com este projeto comecei a entender, na prática, como:

**WireMock → simula uma API**

**Postman → envia requisições**

**WireMock → retorna respostas configuradas**

**QA → compara o resultado esperado com o resultado recebido**

Essa prática me ajudou a ter um primeiro contato com testes de API utilizando Mock, WireMock e Postman.

---

## 11. Próximos passos

Como próximos passos nos meus estudos, pretendo continuar aprendendo sobre:

- Testes de API;
- Postman;
- Automação de testes;
- Testes de performance;
- Outros conceitos de QA.
