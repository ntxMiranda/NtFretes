
# NT Frete — Calculadora de Frete e Lucro para Motoristas

## 1. Visão geral

O **NT Frete** é um site desenvolvido para ajudar motoristas e transportadores a calcular os custos de uma viagem e descobrir quanto poderão lucrar com um frete.

A plataforma tem como objetivo simplificar esse processo. O usuário informa o local de destino e o sistema calcula automaticamente a distância da rota, estima os custos com pedágios e combustível e apresenta o custo total da viagem.

Com essas informações, o motorista consegue avaliar se o frete compensa financeiramente antes de aceitar o serviço.

## 2. Objetivo do projeto

Desenvolver uma plataforma simples, intuitiva e eficiente que permita aos motoristas calcular os custos de transporte e estimar o lucro de cada viagem.

O NT Frete busca facilitar a tomada de decisões, oferecendo informações importantes para que o motorista saiba quanto gastará e quanto poderá ganhar.

## 3. Como funciona

1. **Informar o destino:** o usuário digita o endereço ou a cidade de destino.
2. **Definir a origem:** o sistema utiliza a localização de origem configurada pelo usuário ou solicita que ele informe o ponto de partida.
3. **Calcular a distância:** o sistema consulta um serviço de mapas para identificar a distância rodoviária entre a origem e o destino.
4. **Calcular os pedágios:** a plataforma consulta os valores dos pedágios encontrados na rota, quando houver dados disponíveis.
5. **Calcular o combustível:** o sistema estima o gasto com combustível de acordo com a distância, o consumo médio do veículo e o preço por litro.
6. **Calcular os custos operacionais:** o sistema considera o custo por quilômetro rodado e outras despesas configuradas.
7. **Apresentar o resultado:** o site mostra o custo total estimado da viagem e o lucro previsto para o motorista.

A proposta é automatizar o máximo possível do processo, evitando que o motorista precise realizar cálculos manualmente.

## 4. Funcionalidades principais

### 4.1. Cálculo automático da distância

O NT Frete utiliza um serviço de mapas para calcular a distância rodoviária entre a origem e o destino.

A distância será apresentada em quilômetros, considerando a rota selecionada pelo sistema.

### 4.2. Cálculo de pedágios

O sistema identifica os pedágios existentes na rota e calcula o custo total estimado.

Quando os valores não estiverem disponíveis na fonte de dados, o site deverá informar essa limitação e permitir o preenchimento manual.

### 4.3. Cálculo de combustível

O custo de combustível será calculado automaticamente com base na distância, no consumo médio do veículo e no preço do combustível.

**Fórmula:**

`Custo de combustível = (Distância em km / Consumo em km/l) × Preço por litro`

Exemplo:

- Distância: 300 km
- Consumo médio: 3 km/l
- Preço do diesel: R$ 6,00/l

Custo estimado de combustível: R$ 600,00.

### 4.4. Cálculo do custo por quilômetro

O sistema permite considerar o custo por quilômetro rodado, incluindo despesas como:

- Manutenção do veículo.
- Desgaste dos pneus.
- Troca de óleo.
- Depreciação do veículo.
- Outras despesas operacionais.

O motorista poderá configurar esse valor conforme o tipo de veículo utilizado.

Para evitar que o combustível seja contabilizado duas vezes, o sistema deverá diferenciar o custo por quilômetro que já inclui combustível daquele que considera somente as demais despesas operacionais.

### 4.5. Cálculo do lucro estimado

O NT Frete calcula o lucro estimado subtraindo os custos totais do valor recebido pelo frete.

**Fórmula:**

`Lucro estimado = Valor do frete - Custos totais da viagem`

Os custos poderão incluir combustível, pedágios e despesas operacionais.

Para realizar esse cálculo, o usuário deverá informar o valor que receberá pelo frete. Esse valor poderá ser salvo ou preenchido a cada nova simulação.

### 4.6. Resumo financeiro da viagem

Após realizar o cálculo, o site apresentará:

- Distância total da viagem.
- Custo estimado dos pedágios.
- Gasto estimado com combustível.
- Outros custos operacionais.
- Custo total estimado.
- Valor recebido pelo frete.
- Lucro estimado em reais.
- Margem estimada de lucro em porcentagem.

## 5. Interface do usuário

O site deverá possuir uma interface moderna, organizada e responsiva, funcionando tanto em computadores quanto em celulares.

A tela principal deverá apresentar:

- Campo para informar o destino.
- Campo de origem, com possibilidade de salvar um endereço padrão.
- Campo para informar o valor do frete.
- Configurações do veículo e do consumo médio.
- Botão para calcular o frete.
- Mapa com a rota, quando disponível.
- Painel com os custos e o lucro estimado.

A interface deverá priorizar a simplicidade, permitindo que o motorista obtenha as informações de que precisa sem navegar por várias páginas.

## 6. Exemplo de cálculo

Considere uma viagem hipotética com os seguintes valores:

| Descrição | Valor |
|---|---:|
| Distância | 300 km |
| Valor do frete | R$ 1.200,00 |
| Combustível | R$ 600,00 |
| Pedágios | R$ 80,00 |
| Outros custos operacionais | R$ 150,00 |
| **Custo total estimado** | **R$ 830,00** |
| **Lucro estimado** | **R$ 370,00** |

Nesse exemplo, o motorista teria um lucro estimado de R$ 370,00 antes de eventuais despesas não incluídas no cálculo.

Os valores são ilustrativos e servem apenas para demonstrar o funcionamento do sistema.


## 7. Tecnologias e arquitetura

O NT Frete será desenvolvido utilizando Java no back-end, responsável pelas regras de negócio, cálculos financeiros e integração com serviços externos.

### Tecnologias principais

- **HTML:** estrutura das páginas do site.
- **CSS:** estilização e responsividade da interface.
- **Java:** linguagem principal do back-end, responsável pelo processamento das informações e pelos cálculos de frete.
- **Spring Boot:** framework Java para criação da aplicação web e disponibilização de APIs REST.
- **Spring Web:** criação dos endpoints responsáveis por receber as solicitações do usuário e retornar os resultados.
- **Spring Data JPA:** integração com o banco de dados para armazenar usuários, veículos, configurações e histórico de fretes.
- **PostgreSQL:** banco de dados para persistência das informações.
- **API de mapas e rotas:** obtenção da distância rodoviária entre origem e destino.
- **API ou fonte de dados de pedágios:** consulta das tarifas existentes ao longo da rota.

### Responsabilidades do back-end

O Java será responsável por:

- Receber a origem e o destino informados pelo usuário.
- Consultar serviços externos para obter a distância e os dados da rota.
- Calcular os custos estimados de combustível e pedágios.
- Calcular o custo operacional por quilômetro.
- Somar os custos totais da viagem.
- Calcular o lucro estimado com base no valor do frete.
- Armazenar e consultar o histórico de cálculos, caso essa funcionalidade seja implementada.
- Validar os dados recebidos e tratar erros durante as consultas às APIs externas.

### Funcionamento da aplicação

1. O usuário informa o destino e o valor do frete na interface.
2. A aplicação envia os dados para o back-end Java.
3. O Java consulta a API de mapas e os dados de pedágio disponíveis.
4. O sistema realiza os cálculos de distância, combustível e custos operacionais.
5. O back-end calcula o lucro estimado e organiza os resultados.
6. A aplicação retorna os valores para serem apresentados ao usuário.

O front-end poderá utilizar HTML e CSS com páginas renderizadas pelo servidor usando Thymeleaf, evitando a necessidade de JavaScript para a lógica principal da aplicação.

Os cálculos e as regras de negócio permanecerão no Java, facilitando a manutenção, os testes e a evolução do sistema.

## 8. Requisitos importantes

- Calcular a distância rodoviária automaticamente.
- Estimar os custos da viagem com base nos dados disponíveis.
- Validar os valores informados pelo usuário.
- Apresentar os custos de forma separada e transparente.
- Permitir a personalização dos dados do veículo.
- Informar quando os valores forem estimados ou estiverem indisponíveis.
- Evitar a duplicação de despesas nos cálculos.
- Garantir uma boa experiência em dispositivos móveis.
- Proteger os dados pessoais e os locais salvos pelo usuário.

## 9. Melhorias futuras

O NT Frete poderá receber novas funcionalidades, como:

- Histórico de cálculos de frete.
- Cadastro de vários veículos.
- Comparação entre rotas alternativas.
- Cálculo de ida e volta.
- Estimativa de custos de retorno sem carga.
- Inclusão de despesas com alimentação e hospedagem.
- Relatórios de lucro por período.
- Exportação dos resultados em PDF.
- Cadastro de motoristas e transportadoras.
- Sugestão de valor mínimo de frete para atingir uma margem de lucro desejada.

## 10. Resultado esperado

O **NT Frete** pretende ser uma ferramenta prática para motoristas que desejam calcular os custos de transporte e avaliar a rentabilidade de suas viagens.

Ao informar o destino e o valor do frete, utilizando as configurações do veículo previamente cadastradas, o usuário poderá visualizar uma estimativa da distância, dos pedágios, do combustível, dos custos operacionais e do lucro.

O objetivo final é tornar o cálculo de frete mais rápido, transparente e acessível, ajudando o motorista a tomar decisões financeiras mais conscientes.
