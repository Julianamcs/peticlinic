# peticlinic

Exemplo de aplicativo Spring PetClinic Status da versão
Compreendendo o aplicativo Spring Petclinic com alguns diagramas
Veja a apresentação aqui

Executando petclinic localmente
Petclinic é um aplicativo Spring Boot construído usando Maven . Você pode construir um arquivo jar e executá-lo a partir da linha de comando:

git clone https://github.com/spring-projects/spring-petclinic.git
cd spring-petclinic
./mvnw package
java -jar target/*.jar
Você pode então acessar petclinic aqui: http: // localhost: 8080 /

petclinic-screenshot

Ou você pode executá-lo diretamente do Maven usando o plugin Spring Boot Maven. Se você fizer isso, ele pegará as mudanças que você fizer no projeto imediatamente (as mudanças nos arquivos-fonte Java também requerem uma compilação - a maioria das pessoas usa um IDE para isso):

./mvnw spring-boot:run
Caso você encontre um bug / melhoria sugerida para Spring Petclinic
Nosso rastreador de problemas está disponível aqui: https://github.com/spring-projects/spring-petclinic/issues

Configuração de banco de dados
Em sua configuração padrão, Petclinic usa um banco de dados na memória (H2) que é preenchido na inicialização com dados. O console h2 é exposto automaticamente em http://localhost:8080/h2-console e é possível inspecionar o conteúdo do banco de dados usando a jdbc:h2:mem:testdburl.

Uma configuração semelhante é fornecida para o MySql, caso uma configuração persistente de banco de dados seja necessária. Observe que sempre que o tipo de banco de dados é alterado, o aplicativo precisa ser executado com um perfil diferente: spring.profiles.active=mysqlpara MySql.

Você pode iniciar o MySql localmente com qualquer instalador que funcione para o seu sistema operacional ou com o docker:

docker run -e MYSQL_USER=petclinic -e MYSQL_PASSWORD=petclinic -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=petclinic -p 3306:3306 mysql:5.7.8
Mais documentação é fornecida aqui .

Trabalhando com Petclinic em seu IDE
Pré-requisitos
Os seguintes itens devem ser instalados em seu sistema:

Java 8 ou mais recente.
ferramenta de linha de comando git ( https://help.github.com/articles/set-up-git )
Seu IDE preferido
Eclipse com o plugin m2e. Nota: quando m2e está disponível, há um ícone m2 na Help -> Aboutcaixa de diálogo. Se m2e não estiver lá, basta seguir o processo de instalação aqui: https://www.eclipse.org/m2e/
Conjunto de ferramentas Spring (STS)
IntelliJ IDEA
Código VS
Passos:
Na linha de comando

git clone https://github.com/spring-projects/spring-petclinic.git
Dentro do Eclipse ou STS

File -> Import -> Maven -> Existing Maven project
Em seguida, construa na linha de comando ./mvnw generate-resourcesou usando o iniciador Eclipse (clique com o botão direito no projeto e Run As -> Maven install) para gerar o css. Execute o método principal do aplicativo clicando com o botão direito sobre ele e escolhendo Run As -> Java Application.

Por dentro do IntelliJ IDEA No menu principal, escolha  File -> Opene selecione o Petclinic pom.xml . Clique no Openbotão.

Os arquivos CSS são gerados a partir da construção do Maven. Você pode construí-los na linha de comando ./mvnw generate-resourcesou então clicar com o botão direito no spring-petclinicprojeto Maven -> Generates sources and Update Folders.

Uma configuração de execução chamada PetClinicApplicationdeve ter sido criada para você se você estiver usando uma versão recente do Ultimate. Caso contrário, execute o aplicativo clicando com o botão direito na PetClinicApplicationclasse principal e escolhendo Run 'PetClinicApplication'.

Navegue até Petclinic

Visite http: // localhost: 8080 em seu navegador.

Procurando algo em particular?
Configuração Spring Boot	Arquivos de classe ou propriedade Java
A classe principal	PetClinicApplication
Arquivos de propriedades	application.properties
Cache	CacheConfiguration
Filiais e garfos interessantes da Spring Petclinic
O branch "principal" do Spring Petclinic no GitHub org do spring-projects é a implementação "canônica", atualmente baseada no Spring Boot e Thymeleaf. Existem alguns garfos em uma GitHub org spring-petclinic especial . Se você tem um interesse especial em uma pilha de tecnologia diferente que poderia ser usada para implementar a Pet Clinic, junte-se à comunidade lá.

Interação com outros projetos de código aberto
Uma das melhores partes de trabalhar no aplicativo Spring Petclinic é que temos a oportunidade de trabalhar em contato direto com muitos projetos de código aberto. Encontramos alguns bugs / sugestões de melhorias em vários tópicos, como Spring, Spring Data, Bean Validation e até Eclipse! Em muitos casos, eles foram corrigidos / implementados em apenas alguns dias. Aqui está uma lista deles:

Nome	Questão
Spring JDBC: simplificar o uso de NamedParameterJdbcTemplate	SPR-10256 e SPR-10257
Bean Validation / Hibernate Validator: simplifica as dependências do Maven e compatibilidade com versões anteriores	HV-790 e HV-792
Spring Data: fornece mais flexibilidade ao trabalhar com consultas JPQL	DATAJPA-292
Contribuindo
O rastreador de problemas é o canal preferido para relatórios de bugs, solicitações de recursos e envio de solicitações pull.

Para solicitações pull, as preferências do editor estão disponíveis na configuração do editor para facilitar o uso em editores de texto comuns. Leia mais e baixe plug-ins em https://editorconfig.org . Caso ainda não o tenha feito, preencha e envie o Contrato de Licença de Contribuidor .

Licença
O aplicativo de amostra Spring PetClinic é lançado sob a versão 2.0 da Licença Apache .
