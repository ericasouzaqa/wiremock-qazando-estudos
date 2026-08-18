## Projeto de mock da QAZANDO

Esse projeto temos como exemplo uma api de carros.

Temos algumas situações mapeadas no nosso mock que ao registrar algumas massas em específico a gente consegue um determinado valor de resposta.

## Exemplos de massas abaixo:

- Cadastro de veículo: Se o cadastro de veículo for igual a um "fusca" no parâmetro "model". = O mock tem que responder 201
- Cadastro de veículo: Se o cadastro de veículof for igual a um "up tsi" no parâmetro "model" = O mock tem que responder 500

# Como subir o mock.

- baixar o projeto
- Acessar a pasta do projeto
- Rodar o seguinte comando para subir o mock: java -jar wiremock-standalone-3.9.1.jar

OBS: Precisa ter o java instalado em sua máquina na versão 11 pra cima.

## O que eu aprendi

Durante esse exercício, aprendi a utilizar o WireMock para criar mocks de uma API e simular diferentes comportamentos de acordo com os dados enviados nas requisições.

Também aprendi:

- Como executar o WireMock localmente utilizando um arquivo `.jar`.
- A importância de utilizar uma versão compatível do Java com o WireMock.
- Como verificar a versão do Java instalada na máquina.
- Como configurar uma porta específica para executar o WireMock.
- Como utilizar diferentes massas de teste para obter diferentes respostas da API.
- Como simular cenários de sucesso e erro utilizando diferentes códigos HTTP.
- Como utilizar o Git Bash para executar uma aplicação Java.
- Como clonar um projeto existente do GitHub.
- Como configurar um repositório original como `upstream`.
- Como configurar meu próprio repositório como `origin`.
- Como versionar minhas alterações utilizando Git.
