## Servidor STOMP Spring Boot

Este documento fornece informações sobre um servidor STOMP (Simple Text Oriented Messaging Protocol) implementado com Spring Boot e Java 23.

### Visão Geral

O projeto implementa um servidor STOMP, permitindo a comunicação bidirecional em tempo real entre clientes e o servidor. O Spring Boot simplifica a configuração e o gerenciamento do servidor.

### Tecnologias Utilizadas

* **Spring Boot:** Framework para desenvolvimento rápido de aplicações Java baseadas em microsserviços.
* **Spring WebSockets:** Módulo Spring Boot que fornece suporte para desenvolvimento de aplicações WebSocket e STOMP.

### Dependências

* `spring-boot-starter-websocket`: Inclui bibliotecas necessárias para implementar o servidor WebSocket e STOMP.
* `lombok` (opcional): Biblioteca para reduzir código boilerplate (opcional, requer configuração adicional no IDE).

### Construindo e Executando

**Pré-requisitos:**

* JDK 17 ou superior
* Maven 3 ou superior

1. **Clone o repositório:** Clone este repositório para sua máquina local.
2. **Instale as dependências:** Execute `mvn clean install` no diretório do projeto para baixar as dependências.
3. **Execute o servidor:** Execute a classe principal do Spring Boot (geralmente `com.autonomous.SpringStompServerApplication`) usando `java -jar target/spring-stomp-server-1.0-SNAPSHOT.jar` (substitua o nome do JAR pelo gerado durante a construção).

### Conectando um Cliente STOMP

* Utilize uma biblioteca JavaScript como SockJS para se conectar ao servidor e enviar/receber mensagens via STOMP.
* O endpoint para conexão depende da sua implementação, mas geralmente segue o formato `ws://localhost:<porta>/<caminho>`.

**Exemplo de cliente JavaScript:**

```javascript
var socket = new SockJS('/your-websocket-endpoint');
var stompClient = Stomp.over(socket);
stompClient.connect({}, function (frame) {
    console.log('Connected: ' + frame);
    // Assine a tópicos e envie/receba mensagens
});
```

**Substitua `/your-websocket-endpoint` pelo endpoint real do seu servidor.**

### Personalização

* **Manuseio de mensagens:** Crie controladores para tratar mensagens recebidas dos clientes e enviar respostas via STOMP.
* **Destinos de Mensagens:** Configure destinos (tópicos e filas) para roteamento e broadcast de mensagens.
* **Segurança:** Implemente autenticação e autorização para proteger seu servidor.

### Considerações

* Este é um exemplo básico de servidor STOMP.
* Para aplicações de alta carga, considere otimizar o servidor e utilizar um broker de mensagens dedicado.
* Explore os recursos oficiais do Spring para aprender sobre funcionalidades e configurações avançadas.

### Contribuições

Contribuições são bem-vindas! Siga as orientações do Git e envie um pull request.
