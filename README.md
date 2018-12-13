Esse repositório é um fork [Piggy Metrics](https://github.com/sqshq/PiggyMetrics), uma aplicação de referência que demonstra a adoção de uma arquitetura de microserviços usando o framework Spring Cloud e Docker

# Desafio:

Construir uma pipeline utilizando o [Jenkins](https://jenkins.io/) com ao menos os seguintes steps:

* build:maven
* test:maven
* package:docker
* deploy:docker

**Quer surpreender no desafio?**
 * adicione um stage para análisar a qualidade do código fonte
 * adicione um stage para publicar os artefatos (jar e docker) em um repositório
 * faça a implantação dos containers de forma que eles escalem individualmente

**O que gostaríamos de observar na demonstração:**
 * O pipeline executado quando uma alteração de código é feita, garantindo a integridade e qualidade das aplicações
 * Se algum teste unitário estiver falhando, o pipeline deve interromper a sua execução
 * O processo de implantação na infraestrutura selecionada
 * Recomendações que você tenha sobre a aplicação e sobre o processo seletivo


# Referências
* [Maven](https://maven.apache.org)
* [Docker](https://www.docker.com)
* [Jenkins](https://jenkins.io)
* [Spring Cloud](http://spring.io/projects/spring-cloud)
