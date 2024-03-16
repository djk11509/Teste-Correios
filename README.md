1.	O que é o Correios Web Services?
2.	Cadastrar usuário pessoa jurídica.
3.	Gerar código de acesso da API.
4.	Utilizando as API's.
o	A. Código de acesso da API e o gerador de token
o	B. Gerando o token
o	C. Realizando os primeiros testes
o	D. Outros códigos de retorno do servidor.
5.	Preparando o ambiente no Postman.
o	A. Criando uma coleção
o	B. Criando a requisição
o	C. Conhecendo a tela
o	D. Realizando a primeira requisição pelo POSTMAN
1 - O que é o Correios Web Services?
Correios Web Services – CWS fornece uma plataforma de serviços web, permitindo acesso, por integração, aos dados que podem auxiliar o cliente dos Correios em funcionalidades que visa agregar mais valor ao seu produto ou serviço e com dados mais assertivos, a exemplo dos dados de endereçamento. O CWS é direcionado ao cliente dos Correios que deseja desenvolver soluções customizadas em Tecnologia da Informação – TI.
O acesso as funcionalidades, se dará por API (Aplication Programming Interface ou Interface de programação de aplicações). O cliente com contrato poderá ter acesso a API consideradas abertas ou restritas mediante autorização.
O Protocolo de comunicação utilizado é por meio do Hyper Text Transfer Protocol – HTTP, responsável pela transferência de dados. Como meio de comunicação utilizando REST ou SOAP e retornando como respostas dados JSON ou XML, oferecendo assim a extensibilidade e a interoperabilidade entre as diversas aplicações, podendo ser executadas nas mais variadas plataformas e frameworks.
A exemplo do REST, será fornecida uma url base e os verbos HTTP vão indicar qual ação está sendo requisitada pelo cliente.
O acesso ao CWS é feito pelo link: https://cws.correios.com.br. Apesar da existência do ambiente de homologação, para a realização de testes, o acesso as funcionalidades será realizada através de orientações, login e senha específicos para a funcionalidade.
O acesso ao CWS é através do perfil criado no Meu Correios, link de acesso: https://meucorreios.correios.com.br.
2 - Cadastrar usuário pessoa jurídica.
Para realizar o cadastro no Meu Correios. Acessar o link: https://meucorreios.correios.com.br será direcionado a tela abaixo. Clicar na opção “Fazer cadastro” e seguir os passos para realizar o cadastro. Lembrando que o acesso as API's pode ser restrito a clientes de contrato.
 
Voltar
3 - Gerar código de acesso da API.
Após realizar o cadastro no Meu Correios, deve acessar, o endereço dos Correios Web Services: https://cws.correios.com.br. Ao acessar o link a página abaixo será exibida:
 
1.	Representado pelas três linhas horizontais (botão de hambúrguer), permite abrir o menu lateral no qual permite acessar as opções: Documentação, Gestão de acesso a API e Ajuda;
2.	Menu de acesso ao perfil e Sair do ambiente;
3.	Dashboard ou tela de acesso as API(s).
Para gerar o código de acesso a(s) API(s), deve acessar o menu lateral (abrir pelo botão de hambúrguer) e clicar na opção (1) Gestão de acesso a APIs; (2) Informe a senha utilizada no portal Meu Correios (3) Clique no botão para gerar ou regerar o código de acesso.
 
(4) Dado que o cliente já possua um código de acesso, o sistema exibirá uma mensagem de confirmação antes de emitir o novo (5) Clique em "Sim" para prosseguir.
 
(6) O código de acesso gerado será exibido como na imagem abaixo. Copie e guarde para utilizar na geração do token
 
Voltar
4 - Utilizando as API's.
A tela principal do CWS, é semelhante à figura abaixo:
 
O CWS permite realizar os primeiros testes após a emissão do código de acesso a(s) API(s).
A tela permite gerar a chave de acesso (token) (1); Para conhecer as API(s) que são acessíveis, ao clicar na barra de pesquisa (2), abre a lista de APIs; e (3) a documentação da API.
 
A. O código de acesso a(s) API(s) e o gerador de token
•	É necessário emitir o código de acesso para que seja possível gerar o token;
•	O gerador de token, ou chave de acesso, no qual permite gerar uma chave criptografada com dados válidos que autoriza o acesso aos dados da API e com prazo de validade.
Recursos que ainda estão em SOAP, utilizam somente as credenciais da API, o portal CWS não simula as requisições em SOAP, para isso, deve utilizar uma aplicação semelhante ao SOAPui. E para utilizar a tecnologia REST, deve utilizar as credenciais da API para gerar o token, e utilizar o token para realizar as requisições mais seguras.
B. Gerando o token
Clicar na opção “Credenciais”, como mostra a figura abaixo:
 
Vai abrir a janela para inserir os dados necessários para incluir os dados de autenticação, que é o código de acesso da API (1) e dados do contrato (2) que é o código do cartão de postagem.
Preenchido basta gerar o token (3), para obter a chave criptografada (4). Ao gerar a chave, basta fechar a tela, e a chave gerada poderá ser utilizada em outras funcionalidades no qual terá acesso.
 
C. Realizando os primeiros testes
A aba “Api Manager – Token (5)”, está liberada o acesso a todos os usuários, afinal esta API é a que irá permitir a criação da chave criptografada.
O nome Token é a API com o objetivo de gerar a chave criptografada e (5) é o código da API.
Na imagem a seguir, mostra que a tela tem esse padrão: o título (1) com o link da documentação (JSON), as requisições verbais (2) e o schemas (3) com a finalidade semelhante a um dicionário de dados.
 
No item (2), ao clicar no verbo POST, abre uma tela no qual permitirá a realização de testes no portal do CWS, sem a necessidade de instalação de outros softwares.
 
Ao clicar no botão “Try it out”, permite executar a requisição.
 
Ao clicar em “Execute” (1), é realizada a requisição em Curl e Request URL (2) é a representação da requisição e a resposta do servidor (3) com o retorno Code 201 e o detalhe do Response body.
Como o código de resposta foi 201, requisição realizada com sucesso, teremos um retorno da chave criptografada para uso em uma API. Além disso há também os dados referente ao Meu Correios do requisitante conforme preenchido na tela de credenciais.
É no corpo da resposta que o desenvolvedor poderá aplicar a mesma chave para outras requisições porque sua vigência é de 24h. Além disso, verificar a quais sistemas o usuário com o perfil PJ, possui na lista de códigos de API e em qual ambiente está utilizando para fazer as requisições.
Corpo da Resposta ou Response body:
 
O intervalo de vigência desta chave é do dia 23/06/2021 às 22:06:22 até o dia seguinte 24/06/2021 às 22:06:06, sendo que após este horário deverá gerar uma nova chave de acesso.
Caso o usuário saia dessa tela, será necessário informar novamente as credenciais de acesso para testar a API
D. Outros códigos de retorno do servidor.
Um exemplo, é simular o acesso sem digitar a senha do componente:
 
Ao clicar em “Execute” (1), já houve o retorno de “Senha não foi informada” (2).
Como houve o erro de senha não informada, podemos ver que na tela já aparece o código 401 – não autorizado.
Caso receba um erro 50x – erro no servidor, será listado o erro conforme demonstrado na figura abaixo:
 
Explorando o final da página da aba do Token, encontraremos o Grupo Schemas, onde poderá visualizar as propriedades:
 
Voltar
5 - Preparando o ambiente no Postman
Para iniciar os testes, sem uma ferramenta no qual consiga salvar o que foi desenvolvido (requisições), poderá gerar retrabalho. Para isso, neste manual, utilizaremos a ferramenta Postman que permite realizar a execução dos testes e o mais importante, salvar o trabalho (requisições).
O download da ferramenta é no site https://www.postman.com ou poderá ser utilizado pelo navegador Google Chrome, acrescentando a extensão do Postman. Caso, já tenha outra ferramenta no qual permita definir o verbo para URL, não há problemas.
 
Esclarecemos que utilizaremos esta ferramenta, por facilitar a homologação das API(s), e não será uma aula sobre a ferramenta Postman.
A. Criando uma coleção
A coleção permite que agrupe as API(s) que serão utilizadas no decorrer do manual. Exemplo: Geração de Token, Geração de Pré-Postagem, Geração de rótulo, etc. Clique no “+” e aparecerá uma coleção “New Collection”.
 
Clique no “New Collection” e do lado direto clique no lápis ícone ao lado direito do nome.
Escreva o nome da coleção como “Geração de Token”.
 
B. Criando a requisição
Para criar uma requisição, após a criação de uma coleção, poderá clicar em “Add a request”.
 
Ao lado direito abre uma aba no qual poderá renomear para “Gerar token para o cartão de postagem”
 
C. Conhecendo a tela
1.	Abas de navegação;
2.	Nome da requisição e a qual coleção pertence;
3.	Verbo e a url base;
4.	Informações que podem ser adicionadas por parâmetros, dados de autorização, cabeçalho da requisição, corpo da requisição;
5.	Botão Send, se pressionar a seta para baixo, poderá enviar e fazer o download do resultado;
6.	Resposta da requisição.
 
D. Realizando a primeira requisição pelo POSTMAN
É necessário utilizar as informações que estão na funcionalidade Documentação, para preencher os campos desta requisição.
Relembrando, nos passos anteriores vimos:
•	Acesso aos componentes: Login e senha de acesso aos componentes;
•	Endereço de requisição;
•	Verbo utilizado na requisição;
•	O corpo da requisição.
No endereço de requisição e no verbo ficará assim:
 
No login e senha, clique na aba (1) Authorization, selecione em Type (2) “Basic Auth” e (3) preencha os dados de login e o código de acesso:
 
Próximo passo é enviar os dados do cartão de postagem, clique em (1) Body, (2) raw, (3) JSON e (4) informe o número do cartão de postagem.
 
A pressionar o botão Send termos a resposta semelhante a apresentada abaixo:
 

Documentação de integração

 ######################################################################################################################################################

 DINEG/SUCAN/DEDIG
Documentação de integração
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 2
Sumário
TABELA EVOLUTIVA.......................................................................................................................... 4
1. GLOSSÁRIO................................................................................................................................ 5
2. INTRODUÇÃO............................................................................................................................. 7
3. CONHECENDO O AMBIENTE CORREIOS API........................................................................ 8
4. PRÉ-REQUISITOS PARA UTILIZAR O CORREIOS API .......................................................... 9
5. ACESSO AS APIS. ..................................................................................................................... 9
A. REALIZANDO O PRIMEIRO TESTE EM HOMOLOGAÇÃO .................................................................. 10
6. CARACTERÍSTICAS DA API ................................................................................................... 15
7. APIS DOS CORREIOS.............................................................................................................. 16
8. PREPARANDO O AMBIENTE NO POSTMAN ........................................................................ 17
B. CRIANDO UMA COLEÇÃO........................................................................................................... 18
C. CRIANDO A REQUISIÇÃO ........................................................................................................... 19
D. CONHECENDO A TELA............................................................................................................... 20
E. REALIZANDO A PRIMEIRA REQUISIÇÃO PELO POSTMAN ............................................................... 21
9. API CEP..................................................................................................................................... 23
10. DICA DE IMPORTAÇÃO DA DOCUMENTAÇÃO DA API PARA O POSTMAN .................... 26
11. COMO UTILIZAR O MESMO TOKEN PARA VÁRIOS RECURSOS....................................... 30
12. API AGÊNCIA............................................................................................................................ 31
13. API PREÇO E API PRAZO ....................................................................................................... 34
F. API PRAZO.............................................................................................................................. 34
G. API PREÇO ............................................................................................................................. 37
14. API RASTRO............................................................................................................................. 42
15. API DE PRÉ-POSTAGEM DOS CORREIOS............................................................................ 45
H. PRÉ-POSTAGEM ...................................................................................................................... 47
I. EMITINDO/REEMITINDO O RÓTULO DE ENDEREÇAMENTO DO OBJETO........................................... 49
J. SOLICITAÇÃO DE FAIXAS DE ETIQUETAS..................................................................................... 50
K. EMITINDO A DECLARAÇÃO DE CONTEÚDO .................................................................................. 52
L. EMITINDO O AVISO DE RECEBIMENTO (AR) ............................................................................... 53
M. CONSULTANDO OBJETOS POSTADOS E PRÉ-POSTADOS .............................................................. 54
N. CANCELAMENTO DE UMA PRÉPOSTAGEM ................................................................................... 54
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 3
O. POSTAGEM EM LOTE PARA OBJETOS SIMPLES OU SEM O NÚMERO DE RASTREAMENTO. UTILIZADO
PARA POSTAGENS DE CARTAS SIMPLES. .......................................................................................................... 55
a) Gerando o Lote ................................................................................................................. 55
b) Consultando o Lote ........................................................................................................... 56
P. GERANDO O RÓTULO DE PRÉ-POSTAGENS................................................................................. 57
16. API PEDIDO INFORMAÇÃO (FALE CONOSCO).................................................................... 58
17. CONSIDERAÇÕES FINAIS ...................................................................................................... 70
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 4
Tabela Evolutiva
Data Melhoria Versão
18/03/2022 Criação 1.0
14/06/2023 Revisão e inclusão da Pré Postagem API 2.0
23/08/2023 Corretivas 2.1
08/09/2023 Inclusão da API FaleConosco 2.2
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 5
1. Glossário
Para facilitar o entendimento, listamos abaixo um pequeno glossário com os
principais termos relacionados à este material.
Termo Descrição
API Application Programming Interfaces
Autenticação Processo de verificação de uma identidade digital do usuário, ou
seja, para assegurar que o usuário é realmente aquele quem diz ser.
Autorização Processo para verificar quais são os privilégios concedidos, para
utilizar uma aplicação.
Aviso de
recebimento
É o serviço adicional que, por meio do preenchimento de formulário
próprio, permite comprovar, junto ao remetente, a entrega do objeto.
Cartão de
postagem
Cartão que identifica um usuário como cliente de contrato dos
Correios.
Código do
serviço
Código dos serviços contratados pelo cliente junto aos Correios. Os
códigos de serviços contratados constam do contrato comercial que
o cliente firmou com os Correios.
Contrato
Comercial
Instrumento que o cliente firma com os Correios para a prestação de
serviços de encomendas, mensagens, marketing direto e outros.
Declaração de
conteúdo
Declaração que deve acompanhar o objeto entregue aos Correios e
que não estão sujeitos a tributação.
Expiração Processo de cancelamento de uma pré-postagem quando a
postagem não é efetuada no prazo determinado. Atualmente esse
prazo é de 7 dias corridos.
HTTPS Hypertext Transfer Protocol Secure
Meu Correios Mecanismo de autenticação e autorização para acesso aos serviços
que os Correios disponibilizam via internet.
Pré-postagem Processo de separação, embalagem e rotulagem de um objeto,
pacote ou envelope, para entrega aos Correios.
REST Representational State Transfer
Rótulo de Etiqueta de identificação e endereçamento do objeto. Pode ou não
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 6
endereçamento ter o número do registro do objeto.
Senha de
componente
Senha definida pelo usuário dos Correios que permite a um usuário
utilizar os componentes disponibilizados pelos Correios.
Token – Api
Manager
Sistema gerador de tokens para acesso de APIs. Gera uma string
codificada com a finalidade de garantir a segurança de quem está
usando a API e evitar fraudes.
Diretório
Nacional de
Endereços - DNE
Base de endereçamento dos Correios.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 7
2. Introdução
Este material foi desenvolvido para contribuir no planejamento e integração com os
Correios do Brasil em qualquer plataforma desejada pelo cliente.
Para quem deseja integrar com os Correios, deve utilizar o Correios API, que é uma
plataforma que contém um catálogo de API´s desenvolvidas em REST e utilizam o protocolo
HTTPS. Ou seja, será fornecida uma url base para cada API e com os verbos HTTP, como:
GET, POST, PUT, DELETE, entre outros, vão indicar qual ação está sendo requisitada pelo
cliente.
As APIs permitem acesso as informações sobre:
 Dados de agências;
 Endereçamento;
 Disponibilidade de serviço;
 Dados de prazo de entrega;
 Dados de preço do serviço;
 Dados de rastreamento, e;
 Criação de pré-postagem.
É importante ressaltar que para utilizar o Correios API é necessário ter um contrato
com os Correios. Uma vez que os acessos as APIs estão relacionadas ao cadastro de APIs
restritas no contrato/cartão de postagem.
Por fim a acesso ao Correios API é um dos benefícios da política comercial dos
Correios.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 8
3. Conhecendo o ambiente Correios API
O acesso as APIs, deve ser realizada pelo catálogo do Correios API. No catálogo o
cliente poderá testar e acompanhar as mudanças quando houver. O catálogo está
disponível no ambiente de Homologação e Produção:
 Homologação: https://cwshom.correios.com.br/
 Produção: https://cws.correios.com.br/
Conhecendo a tela do Correios Web Services:
1. Nome do cliente, lista de opções para acessar Meu Correios, sair do ambiente e
outras configurações;
2. Botão hambúrguer, abre o menu lateral e permitirá acessar a documentação e
gestão de acesso a componentes;
3. Barra de pesquisa e botão para gerar credenciais, a barra de pesquisa mostra uma
lista de componentes no qual possui acesso. Já o botão Credenciais permite gerar
o token ou “passe” para fazer as tentativas de requisições pelo site;
4. Aba do componente, o conteúdo de cada barra mostra o nome da API, versão e um
link com o api-docs. Logo abaixo do título, ou do grupo, mostra o verbo da requisição.
A clicar no verbo “POST”, abre um local no qual permite a realização de testes pelo
navegador utilizando a funcionalidade “Try-it out”.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 9
4. Pré-requisitos para utilizar o Correios API
 Ter um cadastro válido no Meu Correios;
 Para acessar a API, utiliza-se uma senha definida para o componente, para criar a
senha deve-se acessar o Correios API;
 Ter contrato ativo de prestação de serviços de encomendas ou mensagens com os
Correios;
 Empresas que fornecem soluções em TI no segmento de logística.
5. Acesso as APIs.
As APIs dos Correios, possuem regras de acesso, sendo:
 API Pública: onde todos enxergam a API;
 API Restrita: o acesso é realizado a partir do cadastro do serviço no cartão de
postagem.
Para visualizar as APIs liberadas no seu perfil, basta clicar na barra de pesquisa e
visualizar o que está disponível.
A exemplo da API CEP, ela não está visível na lista por ser uma
API restrita, ou seja, requer o cadastro do serviço no cartão de
postagem.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 10
Para que APIs Restritas fiquem visíveis, deve-se incluir os dados em:
1. Credenciais Usuário,
2. Senha,
3. Cartão de postagem,
4. Gerar Token e
5. Fechar.
Veja que agora aparecem as APIs:
 Agência;
 Endereço – CEP v3;
 Prazo;
 Preço;
 Rastro
 Pré-Postagem.
A. Realizando o primeiro teste em homologação
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 11
Para o primeiro teste, será com a geração do Token, API sem restrição e necessária
na geração de uma string codificada com os dados de autenticação e autorização para
informar as APIs dos Correios.
Ao clicar no “POST”, aparecerá o sub-item Parameters e para habilitar o ambiente
basta clicar no botão “Try it out”
Após clicar no botão a tela permitirá digitar o cartão de postagem (1) e clique em
execute.
Ao executar, teremos a resposta do servidor, basta rolar a página para baixo até o
sub-item Responses.
No item 1: Curl Comandos utilizados ou script de comandos, dentre ele está o verbo
da requisição, neste caso “POST”;
No item 2: URL de requisição;
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 12
No item 3: Code 201 – Created, onde o Corpo do retorno contém o retorno em JSON.
No corpo da requisição do token, teremos: ambiente, id, perfil, dados de contrato,
validade do token e o token.
Ponto importante a ser observado, é com relação ao tempo de validade do
token.
Veja o retorno da requisição de exemplo:
Dados relacionados
ao cartão de
postagem
{
 "ambiente": "HOMOLOGACAO",
 "id": "xxxxxxxxxx",
 "perfil": "PJ",
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 13
 "cnpj": "00000000000101",
 "cartaoPostagem": {
 "numero": "00xxxxxxx7",
 "contrato": "99xxxxxxxx",
 "dr": 10,
 "api": [
 93,
 36,
 83
 ]
 },
 "api": [
 93,
 36,
 54,
 87
 ],
Validade do Token "emissao": "20XX-03-18T10:26:51",
 "expiraEm": "20XX-03-19T10:26:51",
Token eyJhbGciOiJSUzUxMiJ9.......
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 14
Explorando o final da página da aba do Token, encontraremos o Grupo Schemas,
onde poderá visualizar as propriedades,
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 15
6. Características da API
As APIs dos Correios foram desenvolvidas com a tecnologia REST, além de padrão
de mercado, permite escolher ou adotar qual a linguagem de programação poderá utilizar,
tais como: ASP, .Net, Java, PHP, Ruby, Python, entre outras.
Entre outras características, os atributos que mais se destacam na API são:
 Ausência de aplicativos proprietários: Para utilizar a API não há necessidade de
instalação de um ambiente específico.
 Simplicidade: o protocolo utilizado é puramente o HTTPS.
 Credenciais: o tratamento das credenciais do cliente trafega em ambiente seguro.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 16
7. APIs dos Correios
A API dos Correios é uma arquitetura orientada a microsserviços permitindo
desenvolver sistemas que sejam mais flexíveis, escaláveis e com manutenção mais
simples.

Como o volume de requisições poderá variar de 1 ou centenas de requisições, para
obter uma resposta rápida do servidor dos Correios estamos adotando duas formas de
requisição: a forma síncrona e a forma assíncrona.
A diferença entre síncrono e assíncrono:
 Uma requisição síncrona, deve aguardar a finalização do processamento e
somente poderá realizar uma nova solicitação após a resposta da requisição, esta
ação, pode dar a sensação de congelamento da requisição.
 Uma requisição assíncrona, o cliente envia uma requisição e recebe dados que
permitem a consulta do status de processamento. Isso permite realizar novas
requisições assíncronas, sem a necessidade de aguardar o fim do
processamento das outras requisições. Ao fim poderá requisitar a coleta dos
dados que foram processados.
Correios
API
Busca CEP Rastreamento
de Objetos Preço e Prazo Busca Agência Pré-Postagem
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 17
8. Preparando o ambiente no Postman
Para iniciar os testes, sem uma ferramenta no qual consiga salvar o que foi
desenvolvido, poderá gerar retrabalho. Para isso, neste manual, utilizaremos a ferramenta
Postman que permite realizar a execução dos testes e o mais importante salvar o trabalho.
Além do download da ferramenta, poderá utilizar uma extensão pelo navegador
Google Chrome, acrescentando a extensão do Postman. Existem outras ferramentas, tal
como o Insomnia, utilize a ferramenta de sua preferência.
Esclarecemos que a adoção do Postman é apenas para fins didáticos,
considerando que ela facilita o entendimento dos passos para acesso as APIs
disponibilizadas pelos Correios.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 18
B. Criando uma coleção
A coleção permite que separe as APIs que será utilizada no decorrer do manual,
poderá ser usado para separação do processo. Tal como: Geração de Token,
Geração de Pré-Postagem, Geração de rótulo, etc. Clique no “+” e aparecerá uma
coleção escrito “New Collection”.
Clique no “New Collection” e do lado direto clique no lápis ícone ao lado direito
do nome.
Escreva o nome da coleção como “Geração de Token”.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 19
C. Criando a requisição
Para criar uma requisição, após a criação de uma coleção, poderá clicar em “Add
a request”.
Ao lado direito abre uma aba no qual poderá renomear para “Gerar token para o
cartão de postagem”
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 20
Gerar token para o cartão de postagem
D. Conhecendo a tela
Item 1: abas de navegação;
Item 2: Nome da requisição e a qual coleção pertence;
Item 3: Verbo e a url base;
Item 4: informações que podem ser adicionadas por parâmetros, dados de
autorização, cabeçalho da requisição, corpo da requisição.
Item 5: botão Send, se pressionar a seta para baixo, poderá enviar e fazer o
download do resultado;
Item 6: resposta da requisição.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 21
E. Realizando a primeira requisição pelo Postman
É necessário utilizar as informações que estão no Correios API, para
preencher os campos desta requisição:
Relembrando, nos passos anteriores vimos:
 Acesso aos componentes: Login e senha de acesso aos componentes;
 Endereço de requisição;
 Verbo utilizado na requisição;
 O corpo da requisição.
Para este primeiro exemplo, a imagem a seguir, mostra o (1) endereço
principal que será utilizado, (2) o verbo e (3) endereço da requisição.
Desta forma o endereço que será utilizado na requisição é a junção do
endereço principal (1) e o endereço da requisição (3). Exemplo:
https://apihom.correios.com.br/token/v1/autentica/cartaopostagem.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 22
No endereço de requisição e no verbo ficará assim:
No login e senha, clique na aba (1) Authorization, selecione em Type (2) “Basic
Auth” e (3) preencha os dados de login e senha:
Próximo passo é enviar os dados do cartão de postagem, clique em (1) Body,
(2) raw, (3) JSON e (4) copie o JSON do site Correios Web Services de
homologação.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 23
Clique em “Send” e veja o retorno:
Com base nesse passo a passo, poderá ser replicado a qualquer API.
9. API CEP
O CEP (Código de Endereçamento Postal) é um conjunto numérico constituído de
oito algarismos, que orienta e acelera o encaminhamento, o tratamento e a distribuição de
objetos de correspondência, por meio da sua atribuição a localidades, logradouros,
unidades dos Correios, serviços, órgãos públicos, empresas e edifícios. (Para saber mais:
Tudo sobre CEP)
Sobre a documentação existente no Correios API, é que os testes poderão ser
realizados na própria documentação:
Ou pelo Postman:
Neste exemplo, será utilizado o método que requer o valor para consultar o endereço
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 24
de um CEP.
A url base é: 'https://apihom.correios.com.br/cep/ ' e que segundo a documentação
será um GET : “/v1/endereços/{cep}”.
Observação: Por padrão o CEP é formado por 8 dígitos numéricos, mas para alguns
endereços utilizamos o 0 (zero) a esquerda, exemplo: 01001001.
Para a requisição:
curl --location --
request GET 'https://apihom.correios.com.br/cep/v1/enderecos/01001001' \
--header 'Accept: application/json' \
--
header 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9.eyJhbWJpZW50ZSI6IkhPTU9MT0dBQ
0FPIiwiaWQiOiI1MzQ2ODQ0MDAwMDEzNCIsInBmbCI6IlBKIiwiY25waiI6IjUzNDY4NDQwMDAwMTM0I
iwiY2FydGFvLXBvc3RhZ2VtIjp7Im51bWVybyI6IjAwNzYzNjI2MzkiLCJjb250cmF0byI6Ijk5MTI0M
jAyOTIiLCJkciI6MTAsImFwaSI6WzQxLDc2LDM0LDM2LDM1LDg3LDgzLDI2XX0sImlwIjoiMTAuOC42N
C42MSwxMC4zOC4wLjAsMTAuOC42NC42MSIsImlhdCI6MTY0NzY5MzkzOSwiaXNzIjoidG9rZW4tc2Vyd
mljZSIsImV4cCI6MTY0Nzc4MDMzOSwianRpIjoiN2ZmNTA0MGUtOWVjMS00NTAyLThjNGUtYzM5Yzk3O
WY0OTNjIn0...
Teremos a resposta:
{
 "cep": "01001001",
 "uf": "SP",
 "localidade": "São Paulo",
 "logradouro": "Praça da Sé",
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 25
 "tipoLogradouro": "Praça",
 "nomeLogradouro": "da Sé",
 "complemento": "- lado par",
 "abreviatura": "Pç da Sé",
 "bairro": "Sé",
 "numeroLocalidade": 96681,
 "tipoCEP": 2,
 "cepUnidadeOperacional": "01032970",
 "lado": "P",
 "numeroInicial": 0,
 "numeroFinal": 998
}
Em caso de exceção, há o retorno http 400 do servidor, tal como os seguintes
exemplos:
Em caso de CEP Inexistente:
Em caso de digitar fora do padrão:
Neste exemplo foi usado o CEP: 01001-001, com o hífen. Porém o retorno informa
a quantidade de caracteres e o formato de exemplo.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 26
10. Dica de importação da documentação da API para o Postman
O postman permite importar a documentação da API. Com essa importação é criada
uma coleção trazendo todos os recursos existentes naquele momento da importação.
Para isso, no ambiente do CWS dos Correios, aproveitando a API CEP como
exemplo, copie o link da documentação, como mostra a imagem:
No postman, clique na opção APIs (1) e clique em Import (2):
Cole o endereço da documentação da API, conforme pedido pelo postman:
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 27
Clique em Import:
Retorne ao Collections:
Ao final, foi importado, todos os recursos da documentação. No entanto, deve-se
atentar a alguns detalhes para dar continuidade no uso desta importação.
Ao clicar em um recurso (1), na url (2), aparece entre chaves duplas um termo
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 28
chamado baseUrl, no postman é definida assim a variável e ao passar o mouse sobre a
variável, aparece o conteúdo desta baseUrl.
Para achar a variável, deve-se consultar o conteúdo da pasta principal CEP v3, nesta
pasta, na próxima imagem, mostra como alterar o conteúdo da variável. No entanto, a
alteração não é indicada, apenas caso necessite de realizar alguma alteração do endereço
da requisição.
Na pasta principal CEP v3 (1), aparece ao lado direito algumas abas dentre elas a
aba Variables (2), ao clicar nesta aba, irá aparecer a variável (3) baseUrl.
Como há possibilidade de existir mais de um ambiente para a mesma API, é indicado
o uso da funcionalidade de ambiente (environments), este recurso permite que utilize a
mesma variável para os ambientes de homologação e produção.
Fazendo um overview, de como criar um ambiente, basta entrar na aba
Environments (1), ao clicar no (+) gera um novo ambiente (2), coloque na coluna Variable
a variável que será utilizada “baseUrl” e em Initial value coloque o endereço base, neste
caso “https://apihom.correios.com.br/cep”, atribua um nome (4) “CEP Homologacao” e
salve (5).
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 29
Crie um ambiente para o ambiente de produção da API CEP:
Ao criar os dois ambientes, retorne a coleções. No canto superior direito, existe uma
lista de ambientes, neste caso, por default é “No Environment”, ao listar quais ambientes
irá aparecer os dois ambientes:
Retornando a um recurso, selecione no ambiente CEP Homologação (1) e veja o
conteúdo da variável (2).
Mudando somente o ambiente para produção (1), repare o conteúdo da variável (2)
mudou a requisição para produção.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 30
Com isso, o postman poderá alternar nos ambientes homologação e produção, não
necessitando alteração da variável local da pasta CEP v3. A partir deste ponto, basta
importar o link de documentação de cada API.
11. Como utilizar o mesmo token para vários recursos
Ao importar a documentação da API Token, será possível criar o ambiente para
homologação e produção, aproveite a dica anterior para gerar esses dois ambientes. No
entanto, como utilizar dentro da API que deseja gerar os testes apenas um token e utilizar
em todos recursos existentes na mesma pasta.
A pasta CEP v3, como exemplo a imagem a seguir, mostra selecionando a pasta (1),
a direita escolher a aba Authorization (2), escolher em Type a opção Bearer Token (3) e
colar o token gerado pela API Token. Ao colar, deve salvar antes de sair da aba.
Já no recurso, não é necessário colar o token, uma vez que o recurso busca o token
que foi definido na pasta principal. Em Type já está definido “Inherit auth from parent”.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 31
12. API Agência
A API Busca Agência tem a funcionalidade de mostrar as agências por localidade.
Há pesquisa por unidades e localidades.
Para utilizar a consulta das unidades, é necessário recuperar os dados de tipos de
unidades e status.
Para a API Agência a base url: “https://apihom.correios.com.br/agencia”, e para o
exemplo será utilizado um GET: “/v1/unidades” com parâmetros.
Exemplo da requisição:
curl --location --
request GET 'https://apihom.correios.com.br/agencia/v1/unidades?status=2&status=
5&codigoTipoUnidade=09&codigoTipoUnidade=12&codigoTipoUnidade=43&codigoTipoUnida
de=46&codigoTipoUnidade=24&codigoTipoUnidade=25&codigoTipoUnidade=27&codigoTipoU
nidade=16&codigoTipoUnidade=18&codigoTipoUnidade=20&codigoTipoUnidade=21&codigoT
ipoUnidade=24&codigoTipoUnidade=25&municipio=Sao Paulo&bairro=CENTRO&uf=SP&page=
0&size=50' \
--header 'Accept: application/json' \
--
header 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9.eyJhbWJpZW50ZSI6IkhPTU9MT0dBQ
0FPIiwiaWQiOiI1MzQ2ODQ0MDAwMDEzNCIsInBmbCI6IlBKIiwiY25waiI6IjUzNDY4NDQwMDAwMTM0I
iwiY2FydGFvLXBvc3RhZ2VtIjp7Im51bWVybyI6IjAwNzYzNjI2MzkiLCJjb250cmF0byI6Ijk5MTI0M
jAyOTIiLCJkciI6MTAsImFwaSI6WzQxLDc2LDM0LDM2LDM1LDg3LDgzLDI2XX0sImlwIjoiMTAuOC42N
C42MSwxMC4zOC4wLjAsMTAuOC42NC42MSIsImlhdCI6MTY0NzY5MzkzOSwiaXNzIjoidG9rZW4tc2Vyd
mljZSIsImV4cCI6MTY0Nzc4MDMzOSwianRpIjoiN2ZmNTA0MGUtOWVjMS00NTAyLThjNGUtYzM5Yzk3O
WY0OTNjIn0...
Com o retorno:
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 32
{
 "itens": [
 {
 "id": "00024419",
 "codigoAntigo": "72300019",
 "codigoCadastroGeral": 16439,
 "nome": "AC CENTRAL DE SAO PAULO",
 "ativa": true,
 "status": "2",
 "descStatus": "INSTALADO",
 "tipo": "A",
 "tipoUnidade": {
 "codigo": "09",
 "descricao": "AGENCIA CORREIO",
 "sigla": "AC -TCO"
 },
 "emails": [
 "spmacacp@correios.com.br"
 ],
 "endereco": {
 "cep": "01031970",
 "uf": "SP",
 "localidade": "SAO PAULO",
 "municipio": "SAO PAULO",
 "logradouro": "PRACA DO CORREIO",
 "bairro": "CENTRO",
 "numero": "SN",
 "codigoIbge": "3550308",
 "regiao": "SDE",
 "longitude": "-46.636301",
 "latitude": "-23.544201",
 "fuso": "UTC-03:00",
 "fusoVerao": "UTC-03:00"
 },
 "horarios": {
 "funcionamento": "SEGUNDA À SEXTA",
 "iniExpediente": "09:00",
 "fimExpediente": "18:00",
 "limitePostagemSemana": "17:35"
 },
 "codigoSro": [
 "01009972"
 ],
 "dhAlteracao": "2021-03-16T01:01:22.27"
 },...],
 "page": {
 "size": 50,
 "totalElements": 7209,
 "totalPages": 145,
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 33
 "number": 0
 }
}
Nesta pesquisa de exemplo, o atributo size informa quantos elementos por página,
foi colocado na requisição um size= 50 ou seja 50 elementos por página, totalizando 145
páginas. Caso a mesma consulta for realizada para informar o conteúdo das demais
páginas, basta informar no atributo page o valor de 0..144, se mantiver o size=50.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 34
13. API Preço e API Prazo
A busca do preço e prazo, estão separadas, para atender ao conceito de
microsserviços. Desta forma, são duas páginas no catálogo do Correios API.
F. API Prazo
Para a base url: https://apihom.correios.com.br/prazo/ utilizando o GET:
/v1/nacional/{coproduto}
Temos o seguinte retorno:
{
 "coProduto": "03220",
 "prazoEntrega": 1,
 "dataMaxima": "2022-03-22T23:58:00",
 "entregaDomiciliar": "S",
 "entregaSabado": "N"
}
curl --location --
request GET 'https://apihom.correios.com.br/prazo/v1/nacional/03220?cepO
rigem=70002900&cepDestino=05311900' \
--header 'Accept: application/json' \
--
header 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9.eyJhbWJpZW50ZSI6IkhPT
U9MT0dBQ0FPIiwiaWQiOiI1MzQ2ODQ0MDAwMDEzNCIsInBmbCI6IlBKIiwiY25waiI6IjUzN
DY4NDQwMDAwMTM0IiwiY2FydGFvLXBvc3RhZ2VtIjp7Im51bWVybyI6IjAwNzYzNjI2MzkiL
CJjb250cmF0byI6Ijk5MTI0MjAyOTIiLCJkciI6MTAsImFwaSI6WzQxLDc2LDM0LDM2LDM1L
Dg3LDgzLDI2XX0sImlwIjoiMTAuOC42NC42MSwxMC4zOC4wLjAsMTAuOC42NC42MSIsImlhd
CI6MTY0NzY5MzkzOSwiaXNzIjoidG9rZW4tc2VydmljZSIsImV4cCI6MTY0Nzc4MDMzOSwia
nRpIjoiN2ZmNTA0MGUtOWVjMS00NTAyLThjNGUtYzM5Yzk3OWY0OTNjIn0....
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 35
Utilizando o Postman:
Para a base url: https://apihom.correios.com.br/prazo/ utilizando o POST:
/v1/nacional
curl --location --
request POST 'https://apihom.correios.com.br/prazo/v1/nacional' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
header 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9.eyJhbWJpZW50ZSI6IkhPTU9MT0dB
Q0FPIiwiBvc3RhZ2VtIjp7Im51bWVybyI6IjAwNzYzNjI2MzkiLCJjb250cmF0byI6Ij... \
--data-raw '{
 "idLote": "1",
 "parametrosPrazo": [
 {
 "cepDestino": "70002900",
 "cepOrigem": "05311900",
 "coProduto": "04162",
 "nuRequisicao": "1",
 "dtEvento": "18/03/2022"
 },
 {
 "cepDestino": "70002900",
 "cepOrigem": "05311900",
 "coProduto": "04669",
 "nuRequisicao": "2",
 "dtEvento": "18/03/2022"
 }
 ]
}'
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 36
Para obter o seguinte retorno:
[
 {
 "coProduto": "04162",
 "nuRequisicao": "1",
 "prazoEntrega": 1,
 "dataMaxima": "2022-03-21T23:58:00",
 "entregaDomiciliar": "S",
 "entregaSabado": "N"
 },
 {
 "coProduto": "04669",
 "nuRequisicao": "2",
 "prazoEntrega": 5,
 "dataMaxima": "2022-03-25T23:58:00",
 "entregaDomiciliar": "S",
 "entregaSabado": "N"
 }
]
Utilizando o Postman
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 37
G. API Preço
Para a base url: https://apihom.correios.com.br/preco utiliza-se o GET:
/v1/nacional/{codigoServico}
Para a requisição:
curl --location --
request GET 'https://apihom.correios.com.br/preco/v1/nacional/03220?cepDestino=7
1930000&cepOrigem=70902000&psObjeto=300&tpObjeto=2&comprimento=20&largura=20&alt
ura=20&servicosAdicionais=019&servicosAdicionais=001&vlDeclarado=200' \
--header 'Accept: application/json' \
--
header 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9.eyJhbWJpZW50ZSI6IkhPTU9MT0dBQ
0FPIiwiaWQiOiI1MzQ2ODQ0MDAwMDEzNCIsInBmbCI6IlBKIiwiY25waiI6IjUzNDY4NDQwMDAwMTM0I
iwiY2FydGFvLXBvc3RhZ2VtIjp7Im51bWVybyI6IjAwNzYzNjI2MzkiLCJjb250cmF0byI6Ijk5MTI0M
jAyOTIiLCJkciI6MTAsImFwaSI6WzQxLDc2LDM0LDM2LDM1LDg3LDgzLDI2XX0sImlwIjoiMTAuOC42N
C42MSwxMC4zOC4wLjAsMTAuOC42NC42MSIsImlhdCI6MTY0NzY5MzkzOSwiaXNzIjoidG9rZW4tc2Vyd
mljZSIsImV4cCI6MTY0Nzc4MDMzOSwianRpIjoiN2ZmNTA0MGUtOWVjMS00NTAyLThjNGUtYzM5Yzk3O
WY0OTNjIn0...
Temos o seguinte retorno:
{
 "coProduto": "03220",
 "pcBase": "10,68",
 "pcBaseGeral": "11,13",
 "peVariacao": "0,0000",
 "pcReferencia": "11,13",
 "vlBaseCalculoImposto": "19,92",
 "inPesoCubico": "N",
 "psCobrado": "300",
 "servicoAdicional": [
 {
 "coServAdicional": "019",
 "tpServAdicional": "V",
 "pcServicoAdicional": "1,79"
 },
 {
 "coServAdicional": "001",
 "tpServAdicional": "A",
 "pcServicoAdicional": "7,00"
 }
 ],
 "peAdValorem": "0,0100",
 "vlSeguroAutomatico": "21,00",
 "qtAdicional": "0",
 "pcFaixa": "11,13",
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 38
 "pcFaixaVariacao": "11,13",
 "pcProduto": "11,13",
 "pcTotalServicosAdicionais": "8,79",
 "pcFinal": "19,92"
}
No Postman:
Para obter a precificação de até 5 simulações, será utilizado o POST. Para base url:
https://apihom.correios.com.br/preco e com o POST: /v1/nacional
curl --location --
request POST 'https://apihom.correios.com.br/preco/v1/nacional' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9.... \
--data-raw '{
 "idLote": "1",
 "parametrosProduto": [
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 39
 {
 "coProduto": "04162",
 "nuRequisicao": "1",
 "cepOrigem": "70902000",
 "psObjeto": "300",
 "tpObjeto": "2",
 "comprimento": "20",
 "largura": "20",
 "altura": "20",
 "servicosAdicionais": [{ "coServAdicional":"019"}, {"coServAdicional":"00
1"} ],
 "vlDeclarado": "100",
 "dtEvento": "18/03/2022",
 "cepDestino": "71930000"
 },{
 "coProduto": "04162",
 "nuRequisicao": "1",
 "cepOrigem": "70902000",
 "psObjeto": "300",
 "tpObjeto": "2",
 "comprimento": "20",
 "largura": "20",
 "altura": "20",
 "servicosAdicionais": [{ "coServAdicional":"019"}, {"coServAdicional":"00
1"} ],
 "vlDeclarado": "100",
 "dtEvento": "18/03/2022",
 "cepDestino": "71930000"
 }
 ]
}'
Obtendo o seguinte retorno:
[ {
 "coProduto": "04162",
 "pcBase": "9,73",
 "pcBaseGeral": "10,14",
 "peVariacao": "0,0000",
 "pcReferencia": "10,14",
 "vlBaseCalculoImposto": "17,93",
 "nuRequisicao": "1",
 "inPesoCubico": "N",
 "psCobrado": "300",
 "servicoAdicional": [
 {
 "coServAdicional": "019",
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 40
 "tpServAdicional": "V",
 "pcServicoAdicional": "0,79"
 },
 {
 "coServAdicional": "001",
 "tpServAdicional": "A",
 "pcServicoAdicional": "7,00"
 }
 ],
 "peAdValorem": "0,0100",
 "vlSeguroAutomatico": "21,00",
 "qtAdicional": "0",
 "pcFaixa": "10,14",
 "pcFaixaVariacao": "10,14",
 "pcProduto": "10,14",
 "pcTotalServicosAdicionais": "7,79",
 "pcFinal": "17,93"
 },
 {
 "coProduto": "04162",
 "pcBase": "9,73",
 "pcBaseGeral": "10,14",
 "peVariacao": "0,0000",
 "pcReferencia": "10,14",
 "vlBaseCalculoImposto": "17,93",
 "nuRequisicao": "1",
 "inPesoCubico": "N",
 "psCobrado": "300",
 "servicoAdicional": [
 {
 "coServAdicional": "019",
 "tpServAdicional": "V",
 "pcServicoAdicional": "0,79"
 },
 {
 "coServAdicional": "001",
 "tpServAdicional": "A",
 "pcServicoAdicional": "7,00"
 }
 ],
 "peAdValorem": "0,0100",
 "vlSeguroAutomatico": "21,00",
 "qtAdicional": "0",
 "pcFaixa": "10,14",
 "pcFaixaVariacao": "10,14",
 "pcProduto": "10,14",
 "pcTotalServicosAdicionais": "7,79",
 "pcFinal": "17,93"
 }]
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 41
No Postman
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 42
14. API Rastro
Esta API permite consultar o status do objeto dentro do fluxo postal. A aba desta API
será:
A exemplo das demais APIs, é utilizado um url base:
https://apphom.correios.com.br/rastro com o GET: /v1/objetos/{codigoObjeto}
Objetos de exemplo: DG049186230BR, DG049186226BR e DG049186212BR
Realizando a requisição:
curl --location --
request GET 'https://apihom.correios.com.br/srorastro/v1/objetos/DG049186226BR?r
esultado=T' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9....
Obtendo o retorno:
{
 "versao": "1.8.7",
 "quantidade": 1,
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 43
 "resultado": "Todos os Eventos",
 "objetos": [
 {
 "codObjeto": "DG049186226BR",
 "tipoPostal": {
 "sigla": "DG",
 "descricao": "ENCOMENDA SEDEX (ETIQ LOGICA)",
 "categoria": "SEDEX"
 },
 "dtPrevista": "2022-03-11T20:58:00",
 "modalidade": "F",
 "peso": 0.5,
 "formato": "Pacote",
 "eventos": [
 {
 "codigo": "BDE",
 "tipo": "01",
 "dtHrCriado": "2022-03-11T17:03:00",
 "descricao": "Objeto entregue ao destinatário",
 "unidade": {
 "tipo": "Unidade de Atendimento",
 "endereco": {
 "uf": "AC",
 "cidade": "XAPURI"
 }
 }
 },
 {
 "codigo": "OEC",
 "tipo": "03",
 "dtHrCriado": "2022-03-11T17:02:45",
 "descricao": "Objeto em rota de entrega",
 "detalhe": "Aguarde envio de link para acompanhar a entrega
em tempo real\r\n",
 "unidade": {
 "tipo": "Unidade de Tratamento",
 "endereco": {
 "uf": "SP",
 "cidade": "SAO PAULO"
 }
 }
 },
 {
 "codigo": "RO",
 "tipo": "01",
 "dtHrCriado": "2022-03-11T17:02:35",
 "descricao": "Objeto em trânsito",
 "detalhe": "Por favor, aguarde",
 "unidade": {
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 44
 "tipo": "Unidade de Distribuição",
 "endereco": {
 "uf": "DF",
 "cidade": "BRASILIA"
 }
 },
 "unidadeDestino": {
 "tipo": "Unidade de Tratamento",
 "endereco": {
 "uf": "GO",
 "cidade": "APARECIDA DE GOIANIA"
 }
 }
 },
 {
 "codigo": "PO",
 "tipo": "01",
 "dtHrCriado": "2022-03-10T19:10:36",
 "descricao": "Objeto postado",
 "unidade": {
 "tipo": "Unidade de Atendimento",
 "endereco": {
 "uf": "SP",
 "cidade": "SAO PAULO"
 }
 }
 }
 ]
 }
 ]
}
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 45
15. API de pré-postagem dos Correios
A API de pré-postagem é microsserviço no qual permite ao cliente encaminhar aos
Correios um arquivo eletrônico com todos os dados necessários para realizar uma
postagem. Além disso, permite realizar o acompanhamento, geração de rótulos e até o
cancelamento da pré-postagem.

Cada pré-postagem é considerada um objeto postal. A novidade é o cuidado com
relação ao volume de pré-postagens que são enviadas ao nossos servidores.
Como o volume poderá variar de 1 ou centenas de pré-postagens, em um único envio
eletrônico, para obter uma resposta rápida do servidor dos Correios estamos adotando duas
formas de requisição: a forma síncrona e a forma assíncrona.
A diferença entre síncrono e assíncrono:
 Uma requisição síncrona, deve aguardar a finalização do processamento e
somente poderá realizar uma nova solicitação após a resposta da requisição, esta
ação, pode dar a sensação de congelamento da requisição.
Geração
agrupada de
objetos simples
Geração de
objetos de
encomendas
Emissão de
rótulos de
endereçamento
Gerar Aviso de
Recebimento
Gerar a
Declaração de
Conteúdo
Cancelar a PréPostagem
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 46
 Uma requisição assíncrona, o cliente envia uma requisição e recebe dados que
permitem a consulta do status de processamento. Isso permite realizar novas
requisições assíncronas, sem a necessidade de aguardar o fim do
processamento das outras requisições. Ao fim poderá requisitar a coleta dos
dados que foram processados.
Os dados de pré-postagens, tais como: dados de contrato, dados de remetente,
dados de destinatário, dados do objeto e serviços adicionais que serão contratados. Serão
validados campo a campo, desta forma, se houver alguma inconsistência será devolvido
uma mensagem de erro informando o motivo. Com a validação dos dados antes da
encomenda ser levada na agência aumenta a assertividade no processo de postagem,
diminuindo a necessidade de ajustes no balcão.
Além disso, a ferramenta está comunicando com o recurso que possibilitará o
fornecimento do rótulo de endereçamento, dispensando a construção do rótulo pelo cliente.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 47
H. Pré-Postagem
No Postman, importe a coleção da Pré-postagem.:
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 48
Se o preenchimento do JSON foi feita corretamente, lembre-se de consultar o
Schema, o retorno do status da requisição será 200 e com o (1) id da pré-postagem.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 49
A importância de consultar o CWS, em Schemas e ver o detalhamento do atributo. Possui
as regras, informando se o atributo é obrigatório, qual tipo e o tamanho.
I. Emitindo/Reemitindo o rótulo de endereçamento do objeto
O endereçamento consiste no conjunto de informações que identificam e orientam o
caminho da sua encomenda nos Correios, da postagem à entrega. O correto
endereçamento de um objeto tem impactos diretos na efetividade da entrega nos prazos
estabelecidos.
Esta API de pré-postagem utiliza uma nova API de geração de rótulo de
endereçamento, criada para tirar do usuário a tarefa de montar o rótulo antes da sua
impressão. Além disso, somente através da API de pré-postagem que vai gerar o código
do objeto que será impresso no rótulo, no momento em que sua emissão for solicitada pelo
usuário.
A emissão do rótulo de endereçamento do objeto deverá ser solicitada pela
informação do código da pré-postagem ou pela informação do código de registro do objeto
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 50
(em caso de reimpressão) e o tipo do rótulo (P-padrão ou R-reduzido). A impressão só
poderá ser realizada com as mesmas credenciais utilizadas para gerar a pré-postagem.
Requisição
https://apihom.correios.com.br/prepostagem/v1/prepostagens/rotulo/assincrono/pdf
{
 "idsPrePostagem": [
 "PRgddyJTC0QMyNqlCX7w0H9A"

 ],
 "tipoRotulo": "P",
 "formatoRotulo": "ET"
}
J. Solicitação de faixas de etiquetas
Logo na criação da pré-postagem não é necessário informar um número de objeto,
sendo assim, o sistema já entende que deve atribuir a uma pré-postagem um número de
objeto para o rastreamento.
Há claro as exceções, onde é o usuário deseja utilizar um número de objeto de forma
antecipada. Porém há regras:
O sistema deve permitir a liberação da faixa de etiquetas, utilizando a média dos
últimos 3 meses de postagem. Caso tenha uma excepcionalidade na solicitação da
quantidade de etiquetas devido a um evento que não estava previsto deve consultar o
assistente comercial solicitando uma excepcionalidade de etiquetas.
Para solicitar etiquetas:
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 51
Para consultar o saldo:
Com esses recursos será possível consultar quem fez a solicitação e a quantidade.
Desta forma, verifique sempre antes de solicitar uma nova faixa, se há necessidade de fazer
novos pedidos. Já que há uma regra de controle para solicitações de faixas de etiquetas.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 52
K. Emitindo a declaração de conteúdo
Requisição
v1/prepostagens/declaracaoconteudo/{ids}
Detalhamento do recurso
PROPRIEDADE TIPO TAMANHO OBRIGATÓRIO DESCRIÇÃO
ids String 24 Sim
Código da pré-postagem.
Deve ser um código Válido.
O status da pré-postagem deve ser
pré-postado. Em nenhum outro
status o rótulo será emitido.
Retorno: arquivo em html.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 53
L. Emitindo o Aviso de Recebimento (AR)
Requisição
v1/prepostagens/avisorecebimento/{ids}
Detalhamento do recurso
PROPRIEDADE TIPO TAMANHO OBRIGATÓRIO DESCRIÇÃO
ids String 24 Sim
Código da pré-postagem.
Deve ser um código Válido.
O status da pré-postagem deve ser
pré-postado. Em nenhum outro
status o rótulo será emitido.
Retorno: arquivo em html.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 54
M. Consultando objetos postados e pré-postados
Lista as pré-postagens de forma paginada. Retorna um booleano indicando se há
uma próxima página. É obrigatório informar combinação de parâmetros ou apenas um
parâmetro relacionado a Id/Código/Eticket.
Requisição
/v2/prepostagens
N. Cancelamento de uma prépostagem
O cancelamento poderá ser realizado utilizando estes recursos.
Pelo id da pré-postagem ou pelo código do objeto.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 55
O. Postagem em Lote para objetos simples ou sem o número de rastreamento.
Utilizado para postagens de cartas simples.
a) Gerando o Lote
Para gerar um lote de pré-postagens, criar uma requisição do tipo POST para
https://apihom.correios.com.br/prepostagem/v1/prepostagens/lote.
Antes de utilizar a funcionalidade, lembre-se da validade do token.
Na aba body, escolha a opção form-data e inclua o arquivo com os exemplos de lote
para serem gerados.
No campo Key, é obrigatório colocar o nome “lote”, conforme print abaixo.
Se a requisição estiver correta, vai ser gerado um id para o lote e o seu
processamento iniciará de forma assíncrona.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 56
b) Consultando o Lote
Consultando o lote de pré-postagens Para consultar o lote gerado, deverá ser feito
uma requisição do tipo GET para a URL :
https://apihom.correios.com.br/prepostagem/v1/prepostagens/lote/{id do lote}.
Um dos retornos desse recurso são os ids das pré-postagens geradas. Essas ids
serão usadas para gerar os rótulos, descrito a seguir.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 57
P. Gerando o rótulo de pré-postagens
Para consultar o lote gerado, deverá ser feito uma requisição do tipo POST para a
URL https://apihom.correios.com.br/prepostagem/v1/prepostagens/rotulo.
No body da requisição, deverão ser informados os Ids das pré-postagens. No caso
de carta simples, pode-se informar até 6 ids por requisição. Deve-se informar também o
tipo de rótulo (P = padrão, R = reduzido).
Exemplo: { "idsPrePostagem":[
"PR1JncySxyRO0Eq0OaQp6dSQ",
"PR2qlXxTEeTkGX4VLJE05Daw",
"PRdwWpHjB0RXm39yK3tz1y0w",
"PRE48D30P0RHmYYMhVhEdQuA",
"PRi76lTnCGTsGLc7IdSHmSvw",
"PRNdWRO2tSTGCQqFSh5PEwHw" ],
"tipoRotulo" : "R"
}
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 58
16. API Pedido Informação (Fale Conosco)
A API Pedido Informação permite a integração com o canal Fale Conosco dos
Correios.
Estão disponíveis 3 métodos que permitem registar, reativar e acompanhar as
manifestações de objetos registrados nacionais. E outro método que permite consultar a
versão atual da API.
A URL base é: ‘https://apihom.correios.com.br/pedido-informacao’.
CADASTRA
Cadastra uma nova manifestação de objeto registrado nacional no Fale Conosco dos
Correios.
A requisição deverá ser pelo método POST que deverá enviar o seguinte corpo:
{
 "contrato": "1234567890",
 "cartao": "1234567890",
 "telefone": "string",
 "pedidos": [
 {
 "codigoObjeto": "AA123456789BR",
 "emailResposta": "mariasilva@hotmail.com",
 "nomeDestinatario": "Maria da Silva",
 "codigoMotivoReclamacao": 132,
 "tipoEmbalagem": "E",
 "tipoManifestacao": "R"
 }
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 59
 ]
}
Onde:
contrato: Número do contrato de postagem do objeto.
cartao: Número do cartão de postagem do objeto.
telefone: Número de telefone do reclamante.
pedidos: Uma lista com 1 ou N pedidos, informando:
codigoObjeto: Número do objeto postal a ser reclamado;
emailResposta: Endereço de e-mail válido para recebimento das respostas;
nomeDestinatario: Nome do destinatário do objeto postal;
codigoMotivoReclamacao: Código numérico referente ao motivo da manifestação,
conforme tabela de referência abaixo.
tipoEmbalagem: Código referente ao tipo de embalagem: E – Envelope; C – Caixa;
tipoManifestacao: Código referente ao tipo de manifestação a ser registrada: R –
Reclamação; I – Solicitação de Ressarcimento.
Tabela de Motivos
Código Motivo
132 Remessa/Objeto Postal entregue em local divergente
133 Remessa/Objeto Postal violada
134 Remessa/Objeto Postal avariada/danificada
135 Remessa/Objeto Postal entregue com atraso
136 Remessa/Objeto Postal devolvida indevidamente
141 Não recebimento do pedido de confirmação
142 Remetente não recebeu o pedido de cópia
148 Remetente não recebeu o AR
211 Remessa/Objeto Postal não entregue
240 AR Digital - Imagem não disponível
1414 Remessa/Objeto Postal sem tentativa de entrega domiciliar
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 60
Exemplo de requisição:
curl -X 'POST' \
 'https://apihom.correios.com.br/pedido-informacao/v1/externo/pedidos/cadastra' \
 -H 'accept: application/json' \
 -H 'Content-Type: application/json' \
 -H 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9.eyJhbWJpZW50ZSI6IkhPTU
 -d '{
 "contrato": "1234567890",
 "cartao": "1234567890",
 "telefone": "string",
 "pedidos": [
 {
 "codigoObjeto": "AA123456789BR",
 "emailResposta": "mariasilva@hotmail.com",
 "nomeDestinatario": "Maria da Silva",
 "codigoMotivoReclamacao": 132,
 "tipoEmbalagem": "E",
 "tipoManifestacao": "R"
 }
 ]
}
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 61
Exemplo de retorno:
{
 "codigoRetorno": 0,
 "descricaoRetorno": "Olá, sua manifestação foi registrada com sucesso.",
 "numeroLote": "0000000",
 "dataHoraCadastro": "20/04/2023 16:13:15",
 "pi": [
 {
 "codigo do objeto": "AA123456789BR",
 "numero do pi": "123456789",
 "codigo retorno": "0",
 "descrição retorno": "Olá, sua manifestação foi registrada com sucesso."
 }
 ],
 "mensagensPi": 0
}
Será retornada uma lista “pi” que constará os retornos de cada pedido.
Cada retorno contará com um código e uma descrição, que poderá variar conforme
a tabela a seguir, de acordo com cada situação.
codigoRetorno descricaoRetorno
4 Olá, dados informados não encontrados na base dos Correios.
30 Olá, precisamos que o CPF/CNPJ seja informado
31 CPF/CNPJ nâo é válido
55 Olá, o objeto não pertence ao contrato/cartão de postagem informado.
60 Olá, para prosseguir o ID Tíquete precisa ser informado.
121 Olá, o número do contrato não existe na base de dados dos Correios.
125 Olá, o número do contrato informado não corresponde ao da postagem do objeto.
126 Olá, o número do cartão de postagem informado não corresponde ao da postagem
do objeto.
240 Olá, é necessário informar um e-mail para resposta.
241 Olá, e-mail informado não está no formato correto.
250 Olá, o código do objeto não foi informado.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 62
260 Olá, o código do motivo da manifestação não foi informado.
261 Olá, o código do motivo da manifestação está fora do formato.
262 Olá, não é permitido o registro desta manifestação/motivo via Webservice ou
Correios Mobile.
271 Olá, o código do objeto está fora do formato “XX999999999XX”.
272 Olá, este canal é exclusivo para o registro de manifestação para objetos/serviço
nacionais.
280 Olá, o tipo de embalagem não foi informado.
281 Olá, o tipo de embalagem não é válido.
282 Olá, o tipo de manifestação não é válido.
301 Olá, o nome do destinatário não foi informado.
510
Olá, o prazo máximo para registro desta manifestação (90 dias, contados da “Data
da entrega” ou “Data prevista de entrega”, o que ocorrer primeiro ), encontra-se
expirado.
530
Olá, a entrega, 1ª tentativa de entrega ou a disponibilização do objeto para retirada
ocorreu dentro do prazo previsto de entrega. Para esta consulta não será gerado
protocolo de atendimento.
531
Olá, o objeto em questão não foi entregue, conforme dados disponíveis no sistema
de rastreamento do objeto. Para esta consulta não será gerado protocolo de
atendimento.
534
Olá, o objeto está aguardando retirada na agência, conforme dados disponíveis no
sistema de rastreamento do objeto. Para esta consulta não será gerado protocolo
de atendimento.
538 Olá, a devolução do Aviso de Recebimento AR está dentro do prazo previsto, razão
pela qual não é possível o registro da manifestação pelo motivo selecionado.
539 Olá, a disponibilização da Imagem do AR Digital está dentro do prazo previsto,
razão pela qual não é possível o registro da manifestação pelo motivo selecionado.
540
Olá, código de serviço do objeto não localizado, razão pela qual, neste momento,
não é possível o registro da manifestação pelo motivo selecionado. Caso o
problema persista, gentileza contatar a Central de Atendimento dos Correios - CAC.
543
Olá, o objeto em questão não foi entregue, conforme dados disponíveis no sistema
de rastreamento do objeto. Para esta consulta não será gerado protocolo de
atendimento.
544
Olá, o objeto está dentro do prazo previsto de entrega, conforme sistema
calculador de preços e prazos. Para esta consulta não será gerado protocolo de
atendimento.
545
Olá, o objeto em questão não se encontra com situação que possibilite o registro
por esse motivo, conforme dados disponíveis no sistema de rastreamento do
objeto. Para esta consulta não será gerado protocolo de atendimento.
546
Olá, o objeto teve sua entrega realizada, conforme dados disponíveis no sistema de
rastreamento de objetos. Para esta consulta não será gerado protocolo de
atendimento.
547 Olá, para registro por este motivo o objeto precisa estar entregue. Para esta
consulta não será gerado protocolo de atendimento.
548
Olá, o objeto está aguardando retirada na agência, conforme dados disponíveis no
sistema de rastreamento do objeto. Para esta consulta não será gerado protocolo
de atendimento.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 63
549 Olá, para este motivo necessária a confirmação da devolução do objeto ao
remetente. Para esta consulta não será gerado protocolo de atendimento.
550 Olá, o objeto em questão não está relacionado com o motivo da manifestação
selecionado.
560 Olá, o motivo selecionado não gera registro de manifestação.
562 Olá, o objeto em questão não possui evidência de postagem cancelada a pedido do
remetente. Para esta consulta não será gerado protocolo de atendimento.
563
Olá, código de serviço do objeto não foi localizado, razão pela qual, neste
momento, não é possível o registro da manifestação pelo motivo selecionado. Caso
o problema persista, gentileza contatar a Central de Atendimento dos Correios -
CAC.
564
Olá, o prazo máximo para registro desta manifestação (30 dias, contados da “Data
da entrega” ou “Data prevista de entrega”, o que ocorrer primeiro), encontra-se
expirado.
580 Olá, o tipo de manifestação não foi informado.
634 Olá, o logradouro não possui entrega domiciliar.
638 Olá, o objeto não foi encaminhado para entrega em unidades dos Correios.
639 Olá, o objeto foi direcionado para entrega em unidade dos Correios a pedido do
cliente. Para esta consulta não será gerado protocolo de atendimento
900 Olá, já existe uma manifestação registrada para objeto informado.
999 Olá, ocorreu um erro durante o processo de cadastro. Tente novamente em alguns
minutos.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 64
REATIVA
Reativa uma manifestação de objeto registrado nacional respondida previamente no
Fale Conosco dos Correios.
A requisição deverá ser pelo método POST que deverá enviar o seguinte corpo:
{
 "contrato": "1234567890",
 "cartao": "1234567890",
 "reativacoes": [
 {
 "protocolo": "98043414",
 "tipoManifestacao": "I",
 "motivoReativacao": "135",
 "observacao": "string"
 }
 ]
}
Sendo:
contrato: Número do contrato de postagem do objeto.
cartao: Número do cartão de postagem do objeto.
reativacoes: Uma lista com 1 ou N reativações, informando:
protocolo: Número da manifestação a ser reativada;
tipoManifestacao: Código referente ao tipo de manifestação a ser registrada: R –
Reclamação; I – Solicitação de Ressarcimento.
MotivoReativacao: Código numérico referente ao motivo da manifestação,
conforme tabela de referência abaixo.
observação: Texto livre para inserção de observações sobre o motivo da reativação.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 65
Tabela de Motivos
Código Motivo
132 Remessa/Objeto Postal entregue em local divergente
133 Remessa/Objeto Postal violada
134 Remessa/Objeto Postal avariada/danificada
135 Remessa/Objeto Postal entregue com atraso
136 Remessa/Objeto Postal devolvida indevidamente
141 Não recebimento do pedido de confirmação
142 Remetente não recebeu o pedido de cópia
148 Remetente não recebeu o AR
211 Remessa/Objeto Postal não entregue
240 AR Digital - Imagem não disponível
1414 Remessa/Objeto Postal sem tentativa de entrega domiciliar
Exemplo de requisição:
curl -X 'POST' \
 'https://api.correios.com.br/pedido-informacao/v1/externo/pedidos/reativa' \
 -H 'accept: application/json' \
 -H 'Content-Type: application/json' \
 -H 'Authorization: Bearer
eyJhbGciOiJSUzUxMiJ9.eyJhbWJpZW50ZSI6IlBST0RVQ0FPIiwiaWQiOiIxOTAiLCJwZm
wiOiJTIiwiYXBpIjpbMjMsNTMsNTQsODcsNTE4LDU3Nyw1ODhdLCJpcCI6IjE3Ny40My4 '
\
 -d '{
 "contrato": "1234567890",
 "cartao": "1234567890",
 "reativacoes": [
 {
 "protocolo": "98043414",
 "tipoManifestacao": "I",
 "motivoReativacao": "135",
 "observacao": "string"
 }
 ]
}'
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 66
Exemplo de retorno:
{
 "protocolo": "0",
 "codigoRetorno": 512,
 "descricaoRetorno": "Olá, sua manifestação foi reativada com sucesso.",
 "numeroLote": "0000000",
 "Data hora reativação": "20/04/2023 16:13:15",
 "pi": [
 {
 "protocolo": "123456789",
 "numero do pi": "123456789",
 "codigo retorno": "0",
 "descrição retorno": "Olá, sua manifestação foi reativada com sucesso."
 }
 ]
}
Será retornada uma lista “pi” que constará os retornos de cada pedido.
Cada retorno contará com um código e uma descrição, que poderá variar conforme
a tabela a seguir, de acordo com cada situação.
codigoRetorn
o
descricaoRetorno
4 Olá, dados informados não encontrados na base dos Correios.
50 Olá, o número do protocolo não foi informado.
55 Olá, o objeto não pertence ao contrato/cartão de postagem informado.
56 Olá, protocolo informado não está respondido
122 Olá, o objeto não pertence ao contrato/cartão de postagem informado.
260 Olá, o código do motivo da manifestação não foi informado.
512 Olá, sua manifestação foi reativada com sucesso.
513 Olá, os campos Observação e Motivo devem ser informados.
531 Olá, o objeto em questão não foi entregue, conforme dados disponíveis no sistema de
rastreamento do objeto. Para esta consulta não será gerado protocolo de atendimento.
534 Olá, o objeto está aguardando retirada na agência, conforme dados disponíveis no
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 67
sistema de rastreamento do objeto. Para esta consulta não será gerado protocolo de
atendimento.
539 Olá, a disponibilização da Imagem do AR Digital está dentro do prazo previsto, razão pela
qual não é possível o registro da manifestação pelo motivo selecionado.
545
Olá, o objeto em questão não se encontra com situação que possibilite o registro por
esse motivo, conforme dados disponíveis no sistema de rastreamento do objeto. Para
esta consulta não será gerado protocolo de atendimento.
550 Olá, o objeto em questão não está relacionado com o motivo da manifestação
selecionado.
560 Olá, o motivo selecionado não gera registro de manifestação.
562 Olá, o objeto em questão não possui evidência de postagem cancelada a pedido do
remetente. Para esta consulta não será gerado protocolo de atendimento.
575 Olá, informamos que o protocolo não foi encontrado.
582 Olá, o tipo da manifestação não pode ser alterado.
583 Olá, o motivo informado não é permitido para este tipo de manifestação.
586 Olá, o tipo de reativação não é válido.
587 Olá, o prazo máximo para reativação expirou em {0}
588 Olá, o motivo informado não é permitido para o assunto da manifestação.
589 Olá, a indenização está dentro do prazo de pagamento. Prazo: {0}
590 Olá, já existe solicitação de ressarcimento para este objeto.
591 Olá, a manifestação encontra-se em andamento.
592 Olá, não é possível reativar manifestações do tipo reclamação sem um número de
objeto.
593 Olá, essa manifestação não encontra-se encerrada.
594 Olá, o objeto da manifestação está vinculado a outro contrato.
595 Olá, o objeto não atende aos critérios para reativação pelo motivo solicitado.
596 Olá, o objeto foi entregue dentro do prazo previsto, por isso a reativação não é permitida
por este motivo.
597 Olá, o objeto foi entregue, assim a reativaçao não é permitida por este motivo.
598 Olá, o objeto está aguardando retirada, assim a reativaçao não é permitida por este
motivo.
634 Olá, o logradouro não possui entrega domiciliar.
999 Olá, ocorreu um erro durante o processo de cadastro. Tente novamente em alguns
minutos.
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 68
ACOMPANHA
Permite acompanhar o status de uma manifestação de objeto registrado nacional no
Fale Conosco dos Correios.
A requisição deverá ser pelo método GET, conforme a seguir:
{
 "contrato": "1234567890",
 "canal": "W",
 "codigodoObjetoOuProtocolo": "12345678 "
}
Onde:
contrato: Número do contrato de postagem do objeto;
canal: Canal de registro da manifestação (sempre deverá ser informado W);
codigodoObjetoOuProtocolo: Número do protocolo da manifestação ou o código
de registro do objeto postal nacional.
Exemplo de requisição:
curl -X 'GET' \
 'https://api.correios.com.br/pedidoinformacao/v1/externo/pedidos/acompanha?contrato=1234567890&canal=W&codigodoOb
jetoOuProtocolo=AA123456789BR%20%2C%2012345678%20' \
 -H 'accept: application/json' \
 -H 'Authorization: Bearer eyJhbGciOiJSUzUxMiJ9. '
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 69
Exemplo de retorno:
{
 "codigoObjeto": "AB000000000BR",
 "numeroPi": "123456789",
 "motivoReclamacaoInicial": "134",
 "descMotivoReclamacaoInicial": "Conteúdo Avariado",
 "motivoDescReclamacaoInicial": "Conteúdo Avariado",
 "motivoReclamacaoFinal": "135",
 "descMotivoReclamacaoFinal": "Conteúdo Avariado",
 "Data de Abertura PI": "20/04/2023",
 "Data de Postagem do Objeto": "10/01/2023",
 "Data Máxima de Entrega": "30/01/2023",
 "Código do Serviço": "04790",
 "Descrição do Serviço": "SEDEX 10 à vista",
 "Postagem Depois da Hora": "S",
 "Data Último Evento": "30/01/2023",
 "Código Último Evento": "00",
 "Tipo Último Evento": "BDE",
 "Descrição Último Evento": "Entregue",
 "Situação Manifestação": "string",
 "Houve Recorrência": "S",
 "Indicativo Procedência": "N",
 "Motivo Recorrência": "135",
 "Data Última Recorrência": "30/01/2023",
 "Mensagem Última Recorrência": "string",
 "Mensagem Última Resposta": "string",
 "Data Última Resposta": "30/01/2023",
"Código Retorno": "00",
 "descricaoRetorno": "Olá, sua manifestação foi registrada com sucesso.",
 "Tipo Manifestação": "I",
 "Indica se a manifestacao foi registrada pelo nivel de servico": "N"
}
Manual de Integração
Diretoria de Negócios – Superintendência Executiva de Canais de Vendas - SUCAN
Revisão 09/2023 – V2.2 70
Serão retornadas informações referentes a manifestação consultada. Ou, no caso
de insucesso, poderão ser retornadas as mensagens conforme tabela a seguir:
codigoRetorno descricaoRetorno
4 Olá, dados informados não encontrados na base dos Correios.
122 Olá, o objeto não pertence ao contrato/cartão de postagem informado.
291 Tipo de consulta inválido
631 Olá, esta manifestação foi registrada pelo sistema nível de serviço, assim não é
possível acompanhá-la.
990 Não foi encontrada uma manifestação que atenda aos critérios informados
999 Olá, ocorreu um erro durante o processo de cadastro. Tente novamente em alguns
minutos.
17. Considerações Finais
Este material foi desenvolvido para facilitar ao leitor que estava acostumado com o
Web Services dos Correios, que havia um padrão SOAP XML e com a migração para REST
poderá sentir falta de material explicativo que era fornecido para cada sistema. Com o
Correios API, centralizamos as documentações e como a atualização é dinâmica
recomenda-se que retorne com frequência.
Para todas as APIs citadas neste material, são as que estão liberadas para uso.
Desta forma, caso tenham dúvidas referente a API o procedimento é entrar em contato com
o Assistente Comercial de sua região ou Contrato.
Informações de atendimento poderão ser obtidas pelo nosso site:
https://www.correios.com.br/falecomoscorreios/central-de-atendimento

 
