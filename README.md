# sip-overview

## PROTOCOLO SIP

Session Initiation Protocol (SIP) é um protocolo de sinalização utilizado para iniciar, manter e terminar sessões de comunicação multimídia, como chamadas de voz e vídeo, mensagens instantâneas e conferências, em redes IP. O SIP é um protocolo de aplicação, definido principalmente para a internet, e funciona de forma similar ao HTTP e SMTP, utilizando um formato de mensagens de texto simples e ASCII.

É um protocolo da camada 7, também conhecida como camada de aplicação, no modelo OSI (Open Systems Interconnection). A camada de aplicação é a mais alta das sete camadas do modelo OSI e é responsável por fornecer serviços de rede diretamente às aplicações de software.

Ele utiliza a infraestrutura da rede subjacente, como a camada de transporte (TCP/UDP), para transmitir suas mensagens e estabelecer comunicações multimídia.

**RFC 3261**

O RFC 3261 especifica o Session Initiation Protocol (SIP), que é um protocolo de sinalização utilizado para iniciar, manter e encerrar sessões multimídia, como chamadas de voz e vídeo, em redes IP. Ele define a sintaxe e semântica das mensagens SIP, os procedimentos para transmissão e processamento dessas mensagens, e as funções dos diferentes componentes de rede, como User Agents, Proxy Servers, Registrar Servers e Redirect Servers. SIP trabalha em conjunto com outros protocolos, como SDP (Session Description Protocol) e RTP (Real-time Transport Protocol), para fornecer uma solução completa de comunicação multimídia, sendo amplamente utilizado em aplicações como VoIP, videoconferências e mensagens instantâneas.

**USER AGENT (UA) NO SIP**

No contexto do SIP (Session Initiation Protocol), um User Agent (UA) é um componente fundamental que atua como uma entidade de rede capaz de iniciar e responder a solicitações de comunicação multimídia. Existem dois tipos principais de User Agents: o User Agent Client (UAC), que é responsável por iniciar as solicitações SIP, como quando um usuário faz uma chamada VoIP, e o User Agent Server (UAS), que responde a essas solicitações, processando e aceitando ou rejeitando chamadas recebidas. Cada dispositivo SIP, como um telefone IP, softphone ou gateway de voz, pode funcionar como ambos os tipos de UA, permitindo a comunicação bidirecional. Os UAs são responsáveis pela criação, modificação e término de sessões de comunicação, incluindo chamadas de voz e vídeo, utilizando o protocolo SIP para a troca de mensagens de sinalização.

## PROXY

No contexto do SIP (Session Initiation Protocol), um Proxy Server atua como um intermediário que facilita a comunicação entre dois ou mais User Agents (UAs). Ele recebe as solicitações SIP dos UAs e as roteia para o destino apropriado, seja outro UA ou outro servidor SIP. Além de roteamento, o Proxy Server pode realizar funções adicionais como autenticação e autorização de usuários, aplicação de políticas de roteamento, e gerenciamento de chamadas. Ele não processa a mídia (áudio ou vídeo) diretamente, apenas manipula as mensagens de controle de sessão, assegurando que a sinalização SIP chegue ao destino correto e que as sessões de comunicação possam ser estabelecidas, modificadas ou terminadas conforme necessário.

Sua atuação inclui:

- Roteamento: Direciona mensagens SIP para o destino apropriado, baseado no endereço SIP.

- Encaminhamento: Encaminha solicitações e respostas entre clientes e servidores SIP.

- Manipulação de Mensagens: Pode modificar ou adicionar informações aos cabeçalhos SIP para facilitar a comunicação.

Ele ajuda a gerenciar o tráfego SIP, otimizar o desempenho da rede e fornecer funções adicionais, como autenticação e controle de acesso.

## SIP REQUEST METHODS (Métodos de Requisição SIP)

RFC 3261 define seis métodos principais:

- INVITE: Inicia uma chamada ou sessão de comunicação.
- ACK: Confirma o recebimento de uma resposta final a um INVITE.
- BYE: Termina uma chamada ou sessão.
- CANCEL: Cancela uma solicitação pendente.
- REGISTER: Registra um UA (User Agent) com um servidor SIP.
- OPTIONS: Consulta as capacidades de um servidor ou UA.

Outros RFCs definem métodos adicionais:

- RFC 3265 (SUBSCRIBE/NOTIFY): Gerencia assinaturas e notificações de eventos.
- RFC 3515 (REFER): Solicita que o destinatário realize uma chamada ou operação.
- RFC 3262 (PRACK): Confirma recebimento de respostas provisórias.
- RFC 3903 (PUBLISH): Publica informações de presença para um servidor.
- RFC 6086 (MESSAGE): Envia mensagens instantâneas.
- RFC 3311 (UPDATE): Atualiza parâmetros de uma sessão já estabelecida.

## RESPONSES CODES SIP

No SIP (Session Initiation Protocol), os códigos de resposta são agrupados em categorias que indicam o status do pedido. Cada grupo de códigos fornece informações específicas sobre o processamento da solicitação. Aqui está um resumo dos principais códigos de resposta:

**1xx: Provisional (Provisório)**

Indicam que a solicitação foi recebida e está sendo processada, mas ainda não foi concluída.
- 100 Trying: O servidor está tentando processar a solicitação.
- 180 Ringing: O destinatário está sendo chamado.
- 183 Session Progress: Informação adicional sobre o progresso da sessão.

**2xx: Successful (Bem-sucedido)**

Indicam que a solicitação foi bem-sucedida.
- 200 OK: A solicitação foi bem-sucedida. Por exemplo, a chamada foi atendida.
- 202 Accepted: A solicitação foi aceita para processamento, mas a ação ainda não foi concluída.

**3xx: Redirection (Redirecionamento)**

Indicam que a solicitação deve ser redirecionada para outro local.
- 300 Multiple Choices: Várias opções de endereço estão disponíveis.
- 301 Moved Permanently: O recurso solicitado foi movido permanentemente para um novo local.
- 302 Moved Temporarily: O recurso solicitado foi movido temporariamente para um novo local.

**4xx: Client Error (Erro do Cliente)**

Indicam que houve um erro na solicitação do cliente.
- 400 Bad Request: A solicitação não pôde ser entendida devido a uma sintaxe incorreta.
- 401 Unauthorized: A solicitação requer autenticação do usuário.
- 403 Forbidden: O servidor entendeu a solicitação, mas se recusa a atendê-la.
- 404 Not Found: O servidor não encontrou o usuário solicitado.
- 407 Proxy Authentication Required: A solicitação requer autenticação com o proxy.

**5xx: Server Error (Erro do Servidor)**

Indicam que o servidor falhou ao tentar processar uma solicitação válida.
- 500 Internal Server Error: O servidor encontrou um erro interno ao processar a solicitação.
- 502 Bad Gateway: O servidor recebeu uma resposta inválida de um servidor upstream.
- 503 Service Unavailable: O servidor está temporariamente indisponível, geralmente devido a sobrecarga ou manutenção.
- 504 Server Time-out: O servidor upstream não respondeu a tempo.

**6xx: Global Failure (Falha Global)**

Indicam que a solicitação não pode ser completada em qualquer servidor.
- 600 Busy Everywhere: O usuário chamado está ocupado em todos os locais.
- 603 Decline: O usuário chamado recusa a chamada.
- 606 Not Acceptable: O recurso solicitado não é aceitável, geralmente devido a limitações de capacidade ou configuração do usuário.
Esses códigos de resposta fornecem informações detalhadas sobre o status e o resultado das solicitações SIP, permitindo que os agentes e servidores SIP lidem adequadamente com as diferentes situações que podem ocorrer durante a comunicação.

## THE SIP URI

Uma SIP URI (Uniform Resource Identifier) é utilizada para identificar um endpoint de comunicação no protocolo SIP (Session Initiation Protocol). A estrutura de uma SIP URI é semelhante a uma URL e inclui vários componentes que fornecem informações sobre o esquema, o usuário, o host, a porta e parâmetros adicionais. Aqui está uma breve explicação sobre cada componente:

Estrutura de uma SIP URI
`sip:user@host:port;parameters`

**Componentes:**

- Scheme (Esquema):

Indica o protocolo utilizado. Para SIP, o esquema é geralmente sip ou sips (para SIP seguro).

Exemplo: `sip:, sips:`

- User (Usuário):

Especifica o identificador do usuário ou a parte do endereço que identifica a pessoa ou serviço.

Exemplo: `sip:alice@...`

- Host:

Indica o domínio ou o endereço IP do servidor SIP que está gerenciando as comunicações.

Exemplo: `sip:alice@example.com`

- Port (Porta):

Especifica a porta do servidor SIP que deve ser utilizada. Se omitida, a porta padrão 5060 (para sip) ou 5061 (para sips) é usada.

Exemplo: `sip:alice@example.com:5060`

- Parameters (Parâmetros):

Adicionam informações adicionais ao URI, separados por ponto e vírgula (;). Alguns parâmetros comuns incluem:<br>
  transport (especifica o tipo de transporte, como UDP, TCP, TLS)<br>
  user (indica o tipo de usuário, como phone)
  
  Exemplo: `sip:alice@example.com;transport=udp`

**Exemplo Completo usando um Telefone como Parâmetro**

Vamos usar um número de telefone como parâmetro na SIP URI. O formato é o mesmo, mas o componente do usuário será um número de telefone e incluiremos o parâmetro user=phone.

```
sip:+1234567890@server.com:5060;transport=tcp;user=phone
```
```
Scheme: sip
User: +1234567890 (número de telefone no formato E.164)
Host: server.com
Port: 5060
Parameters:
transport=tcp (especifica que o transporte deve ser via TCP)
user=phone (indica que o identificador do usuário é um número de telefone)
```

## SIP HEADERS

Os cabeçalhos SIP são componentes importantes em mensagens SIP, fornecendo informações cruciais sobre o roteamento, a autenticação e a descrição da sessão. Cada cabeçalho é composto por um campo de nome e um valor, funcionando como atributos nomeados.

- Request-URI

Descrição: Endereço do recurso que está sendo solicitado. É o destino da mensagem SIP.

Exemplo: ```INVITE sip:usuario@dominio.com SIP/2.0```

- To

Descrição: Indica o destinatário da solicitação ou resposta SIP. Especifica para quem a mensagem é destinada.

Exemplo: ```To: <sip:usuario@dominio.com>```

- From

Descrição: Indica o remetente da solicitação ou resposta SIP. Especifica de onde a mensagem está vindo.

Exemplo: ```From: <sip:remetente@dominio.com>;tag=12345```

- Call-ID

Descrição: Identificador único da chamada, utilizado para agrupar todas as mensagens relacionadas a uma sessão.

Exemplo: ```Call-ID: a84b4c76e66710@pc33.example.com```

- CSeq

Descrição: Especifica o número de sequência do comando dentro de uma chamada e o método SIP utilizado.

Exemplo: ```CSeq: 314159 INVITE```

- Max-Forwards

Descrição: Define o número máximo de saltos que a mensagem pode fazer através dos proxies antes de ser descartada.

Exemplo: ```Max-Forwards: 70```

- Via

Descrição: Rastreia o caminho que a mensagem percorreu até o destino. Inclui informações sobre os proxies pelos quais a mensagem passou.

Exemplo: ```Via: SIP/2.0/UDP pc33.example.com;branch=z9hG4bK776asdhds```

- Contact

Descrição: Fornece um endereço de contato onde o remetente pode ser contatado para a próxima transação.

Exemplo: ```Contact: <sip:remetente@host.dominio.com>```

- Alert-Info

Descrição: Indica um tom ou música a ser tocada para alertar o usuário sobre a chamada.

Exemplo: ```Alert-Info: <http://dominio.com/alert-info>```

- Allow

Descrição: Lista os métodos SIP permitidos pela entidade.

Exemplo: ```Allow: INVITE, ACK, CANCEL, OPTIONS, BYE```

- Authorization

Descrição: Contém as credenciais de autenticação do usuário.

Exemplo: ```Authorization: Digest username="usuario", realm="dominio.com"```

- Call-Info

Descrição: Fornece informações adicionais sobre a chamada.

Exemplo: ```Call-Info: <http://dominio.com/call-info>```

- Content-Disposition

Descrição: Indica como o corpo da mensagem deve ser tratado.

Exemplo: ```Content-Disposition: session```

- Content-Length

Descrição: Especifica o tamanho do corpo da mensagem em bytes.

Exemplo: ```Content-Length: 142```

- Content-Type

Descrição: Indica o tipo de mídia do corpo da mensagem.

Exemplo: ```Content-Type: application/sdp```

- Min-Expires

Descrição: Define o tempo mínimo para a expiração da mensagem.

Exemplo: ```Min-Expires: 3600```

- Record-Route

Descrição: Indica os proxies que devem ser usados nas respostas.

Exemplo: ```Record-Route: <sip:proxy1.dominio.com>```

- Require

Descrição: Indica as extensões SIP necessárias para processar a solicitação.

Exemplo: ```Require: 100rel```

- Route

Descrição: Especifica o caminho que a mensagem deve seguir através dos proxies.

Exemplo: ```Route: <sip:proxy1.dominio.com>```

- Supported

Descrição: Lista as extensões SIP suportadas pela entidade.

Exemplo: ```Supported: timer, 100rel```

- User-Agent

Descrição: Fornece informações sobre o software cliente utilizado para enviar a mensagem.

Exemplo: ```User-Agent: Softphone/1.0```

- WWW-Authenticate

Descrição: Desafio de autenticação enviado pelo servidor para o cliente.

Exemplo: ```WWW-Authenticate: Digest realm="dominio.com", qop="auth"```

Exemplo de Mensagem SIP INVITE com Cabeçalhos:

```
INVITE sip:usuario@dominio.com SIP/2.0
Via: SIP/2.0/UDP pc33.example.com;branch=z9hG4bK776asdhds
Max-Forwards: 70
To: <sip:usuario@dominio.com>
From: <sip:remetente@dominio.com>;tag=12345
Call-ID: a84b4c76e66710@pc33.example.com
CSeq: 314159 INVITE
Contact: <sip:remetente@host.dominio.com>
Content-Type: application/sdp
Content-Length: 142

v=0
o=remetente 2890844526 2890844526 IN IP4 pc33.example.com
s=-
c=IN IP4 pc33.example.com
t=0 0
m=audio 49170 RTP/AVP 0
a=rtpmap:0 PCMU/8000
```

Compact Headers (Cabeçalhos Compactos)

Os cabeçalhos SIP podem ser usados em suas formas compactas para reduzir o tamanho da mensagem. Aqui estão alguns exemplos:

Cabeçalho           | Abreviação
------------------- | -----------------
To                  | t
From                | f
Call-ID             | i
Contact             | m
Content-Length      | l
Content-Type        | c
CSeq                | C
Via                 | v

Exemplo Compacto

```
INVITE sip:usuario@dominio.com SIP/2.0
v: SIP/2.0/UDP pc33.example.com;branch=z9hG4bK776asdhds
m: <sip:remetente@host.dominio.com>
t: <sip:usuario@dominio.com>
f: <sip:remetente@dominio.com>;tag=12345
i: a84b4c76e66710@pc33.example.com
C: 314159 INVITE
l: 142
c: application/sdp
```

## SDP - SESSION DESCRIPTION PROTOCOL

O Session Description Protocol (SDP), definido pela RFC 4566, é um protocolo utilizado em conjunto com o SIP (Session Initiation Protocol) para descrever os detalhes de uma sessão de comunicação multimídia. Enquanto o SIP é responsável por estabelecer, modificar e encerrar sessões, o SDP fornece as informações necessárias para configurar corretamente essas sessões. O SDP descreve aspectos como os tipos de mídia envolvidos, codecs suportados, endereços IP e portas a serem usadas, assegurando que todas as partes envolvidas na comunicação entendam como trocar dados de forma eficiente.

Principais Componentes do SDP:

v= (versão): Especifica a versão do protocolo SDP.<br>
Exemplo: ```v=0```

o= (origem): Identifica o criador da sessão e algumas informações sobre a sessão.<br>
Exemplo: ```o=jdoe 2890844526 2890842807 IN IP4 192.0.2.1```

s= (nome da sessão): Descreve o nome da sessão.<br>
Exemplo: ```s=Example Session```

c= (informações de conexão): Fornece os detalhes de conexão, como o endereço IP.<br>
Exemplo: ```c=IN IP4 192.0.2.1```

t= (tempo): Especifica o tempo de início e fim da sessão.<br>
Exemplo: ```t=0 0```

m= (mídia): Define o tipo de mídia, como áudio ou vídeo, e os detalhes da porta e protocolo.<br>
Exemplo: ```m=audio 49170 RTP/AVP 0```

a= (atributos): Fornece informações adicionais, como codecs suportados.<br>
Exemplo: ```a=rtpmap:0 PCMU/8000```

**Função no SIP**

Quando uma chamada SIP é estabelecida, as partes envolvidas trocam mensagens SIP que contêm descrições SDP. Essas descrições incluem detalhes sobre os tipos de mídia suportados, codecs, endereços IP e portas a serem usadas, garantindo que ambos os lados da comunicação entendam como trocar dados de forma eficiente.

Resumidamente, o SDP é essencial para que as partes de uma sessão SIP possam configurar corretamente os parâmetros técnicos da comunicação multimídia, garantindo compatibilidade e qualidade na transmissão de dados.

## SIP AUTHENTICATION

A autenticação SIP é descrita na RFC 2617 e segue um processo específico para garantir a segurança nas comunicações. Veja como funciona:

1 - Solicitação Inicial: Um cliente SIP, como um telefone VoIP, envia uma solicitação SIP (por exemplo, INVITE) para iniciar uma chamada.

2 - Desafio de Autenticação: Se o servidor SIP precisa autenticar o cliente, ele responde com um código 401 Unauthorized (para autenticação de cliente) ou 407 Proxy Authentication Required (para autenticação de proxy). A resposta inclui um cabeçalho WWW-Authenticate ou Proxy-Authenticate, que contém um desafio, geralmente um nonce (um número único usado apenas uma vez) e outros parâmetros necessários para gerar a resposta autenticada.

Exemplo de resposta do servidor:

```
SIP/2.0 401 Unauthorized
WWW-Authenticate: Digest realm="example.com", qop="auth", nonce="dcd1c2c3d4e5f6g7h8i9j0"
```
3 - Envio de Credenciais: O cliente, ao receber o desafio, gera uma resposta usando suas credenciais (usuário e senha). Ele cria um cabeçalho Authorization ou Proxy-Authorization que inclui um hash da senha, combinado com o nonce fornecido e outras informações especificadas no desafio.

Exemplo de resposta do cliente:

```
INVITE sip:bob@biloxi.com SIP/2.0
Authorization: Digest username="alice", realm="example.com", 
                 nonce="dcd1c2c3d4e5f6g7h8i9j0", 
                 uri="sip:bob@biloxi.com", 
                 response="e6d9b5e3c7a4f8a9b9c6e8a3b2c1d4e5"
```

4 - Validação: O servidor SIP verifica as credenciais enviadas. Se a resposta do cliente for válida, a solicitação original é processada e o cliente é autenticado. Se as credenciais estiverem incorretas, o servidor pode repetir o desafio ou rejeitar a solicitação.

Esse processo de autenticação, descrito na RFC 2617, utiliza o mecanismo Digest Authentication para garantir que as credenciais do usuário sejam transmitidas de forma segura e protegida contra interceptação.


## REGISTRATION

O processo de registro SIP funciona da seguinte forma:

1 - Solicitação de Registro: O cliente SIP envia uma solicitação REGISTER para o servidor SIP. Esta solicitação inclui o endereço SIP do cliente e o endereço onde ele pode ser contatado.

Exemplo:
```
REGISTER sip:dominio.com SIP/2.0
Via: SIP/2.0/UDP 192.0.2.1:5060;branch=z9hG4bK776asdhds
To: <sip:usuario@dominio.com>
From: <sip:usuario@dominio.com>;tag=12345
Call-ID: a84b4c76e66710@192.0.2.1
CSeq: 1 REGISTER
Contact: <sip:usuario@192.0.2.1:5060>
Content-Length: 0
```
2 - Resposta de Registro: O servidor SIP responde com um código de status 200 OK se o registro for bem-sucedido. O servidor então mantém as informações de onde o cliente pode ser encontrado.

Exemplo:
```
SIP/2.0 200 OK
Via: SIP/2.0/UDP 192.0.2.1:5060;branch=z9hG4bK776asdhds
To: <sip:usuario@dominio.com>;tag=12345
From: <sip:usuario@dominio.com>;tag=12345
Call-ID: a84b4c76e66710@192.0.2.1
CSeq: 1 REGISTER
Contact: <sip:usuario@192.0.2.1:5060>
Content-Length: 0
```
3 - Atualizações de Registro: O cliente deve enviar periodicamente novas solicitações REGISTER para renovar seu registro e garantir que seu status esteja sempre atualizado no servidor SIP.

Exemplo:
```
REGISTER sip:dominio.com SIP/2.0
Via: SIP/2.0/UDP 192.0.2.1:5060;branch=z9hG4bK777asdhds
To: <sip:usuario@dominio.com>
From: <sip:usuario@dominio.com>;tag=12345
Call-ID: a84b4c76e66710@192.0.2.1
CSeq: 2 REGISTER
Contact: <sip:usuario@192.0.2.1:5060>
Expires: 3600
Content-Length: 0
```
4 - Cancelamento de Registro: Quando o cliente não precisa mais estar registrado ou está saindo, ele pode enviar uma solicitação REGISTER com um cabeçalho Expires definido como 0 para remover seu registro.

Exemplo:
```
REGISTER sip:dominio.com SIP/2.0
Via: SIP/2.0/UDP 192.0.2.1:5060;branch=z9hG4bK778asdhds
To: <sip:usuario@dominio.com>
From: <sip:usuario@dominio.com>;tag=12345
Call-ID: a84b4c76e66710@192.0.2.1
CSeq: 3 REGISTER
Contact: <sip:usuario@192.0.2.1:5060>
Expires: 0
Content-Length: 0
```
Essas etapas permitem que o servidor SIP saiba onde o cliente está localizado e possa rotear chamadas e mensagens corretamente

## THE PROBLEM WITH NAT

O SIP enfrenta os seguintes desafios com NAT (Network Address Translation):

1 - Endereços IP Privados: Clientes SIP em redes privadas não têm endereços IP públicos, o que dificulta a comunicação direta com servidores SIP externos.

2 - Alteração de Endereço e Porta: NAT pode alterar os endereços IP e portas, causando problemas na correspondência das informações de sessão SIP.

3 - Problemas com Traversal: O tráfego SIP pode ser bloqueado ou redirecionado inadequadamente por NAT, exigindo técnicas adicionais para atravessar NATs, como STUN (Session Traversal Utilities for NAT), TURN (Traversal Using Relays around NAT) e ICE (Interactive Connectivity Establishment).

Esses desafios são abordados por técnicas e protocolos especializados para garantir a comunicação SIP através de NATs.

## OVERVIEW OF REAL TIME PROTOCOL

O Real-Time Protocol (RTP) é um protocolo de rede utilizado para transmitir dados em tempo real, como áudio e vídeo, sobre redes IP. Aqui está um panorama geral do RTP:

1 - Objetivo: O RTP é projetado para fornecer transporte para dados de mídia em tempo real, garantindo que a transmissão de áudio e vídeo ocorra de forma eficiente e com baixa latência.

2 - Estrutura: RTP é geralmente usado em conjunto com o RTCP (Real-Time Control Protocol). Enquanto o RTP cuida da transmissão de dados de mídia, o RTCP monitora a qualidade da transmissão e fornece informações sobre o desempenho da rede.

3 - Transmissão: RTP transmite dados em pacotes e é capaz de lidar com a perda de pacotes e a variação na largura de banda, o que é essencial para a comunicação em tempo real.

4 - Sequenciamento e Sincronização: RTP inclui mecanismos para sequenciar pacotes e sincronizar fluxos de mídia, o que ajuda a reconstruir a ordem e a sincronização correta dos dados recebidos.

5 - Uso: RTP é amplamente utilizado em aplicações de voz sobre IP (VoIP), videoconferências e streaming de mídia.

Em resumo, o RTP é fundamental para garantir que a transmissão de dados de mídia em tempo real seja eficiente e sincronizada, proporcionando uma experiência de comunicação fluida e de alta qualidade.










