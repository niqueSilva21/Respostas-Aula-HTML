
ATIVIDADE 01

O JavaScript é uma linguagem de programação que permite tornar as páginas web interativas e dinâmicas. Ele é executado no navegador do usuário (lado do cliente) e pode responder a eventos, manipular o conteúdo da página, validar formulários, criar animações e muito mais.

Como o JavaScript é usado para criar páginas web: Manipulação do conteúdo (DOM): JavaScript pode alterar o conteúdo da página sem precisar recarregá-la. Por exemplo, pode mostrar ou esconder elementos, alterar textos ou adicionar novos itens a uma lista. Interatividade: Ele responde a ações do usuário, como cliques, movimentos do mouse ou digitação. Efeitos visuais: Pode criar animações, sliders de imagens, carrosséis, pop-ups, etc. Comunicação com servidores: Pode buscar ou enviar dados sem recarregar a página (usando AJAX ou fetch). Validação de formulários: Verifica se os dados inseridos estão corretos antes de enviar para o servidor. Interação com o CSS: 

O JavaScript pode modificar o CSS dinamicamente, ou seja:

Alterar classes ou estilos inline de elementos para mudar cor, tamanho, visibilidade, etc. Ativar ou desativar animações CSS. Criar efeitos visuais complexos em conjunto com bibliotecas como: jQuery (para animações e efeitos visuais simples) GSAP (para animações avançadas) Anime.js, Three.js (para gráficos e animações 3D) 

Exemplo simples:

<button onclick="document.getElementById('caixa').style.backgroundColor = 'blue'"> Mudar Cor </button> <div id="caixa" style="width:100px; height:100px; background:red;"></div> 

Esse botão usa JavaScript para alterar a cor da div com o ID caixa, interagindo diretamente com o estilo CSS.

ATIVIDADE 02

Validação de Formulários com JavaScript no Lado do Cliente 

A validação de formulários é uma etapa essencial para garantir que os dados inseridos pelos usuários estejam corretos antes de serem enviados para o servidor. O JavaScript permite realizar essa validação diretamente no navegador do usuário, evitando envios desnecessários e melhorando a experiência do usuário.

Como o JavaScript captura os dados de um formulário 

O JavaScript consegue acessar os valores dos campos de um formulário por meio do DOM (Document Object Model). Os dados podem ser capturados usando métodos como:

let nome = document.getElementById("nome").value; 

Ou, em um formulário com name="email":

let email = document.forms["formulario"]["email"].value; 

Esses valores podem então ser testados por regras definidas, como "não pode estar vazio", "precisa ter no mínimo 8 caracteres", etc.

Validação antes do envio 

Você pode usar JavaScript para impedir o envio de um formulário caso os dados estejam incorretos:

document.getElementById("formulario").addEventListener("submit", function(event){ let email = document.getElementById("email").value; if(email === "") { alert("O campo de e-mail é obrigatório."); event.preventDefault(); // Impede o envio do formulário } }); 

Essa abordagem evita o envio ao servidor se os dados forem inválidos, economizando recursos e melhorando a segurança.

Expressões Regulares (RegEx) 

As expressões regulares são padrões usados para testar se um texto (como um e-mail ou CPF) está em um formato esperado.

Como funcionam 

Uma expressão regular é escrita em uma forma especial e pode ser usada para comparar strings. Exemplo de expressão para validar e-mail:

let regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/; let email = "exemplo@email.com"; if (regex.test(email)) { console.log("E-mail válido"); } else { console.log("E-mail inválido"); } ^ e $ marcam o início e fim da string [^\s@]+ significa "qualquer coisa, menos espaço ou @" O @ e . são obrigatórios no padrão Validações avançadas com RegEx 

Com expressões regulares, é possível validar formatos como:

E-mails Números de telefone Senhas (com letras maiúsculas, minúsculas, números e símbolos) CEPs, CPFs, etc. 

Exemplo de validação de senha segura:

let senha = "Senha123!"; let regexSenha = /^(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[\W_]).{8,}$/; if (regexSenha.test(senha)) { console.log("Senha forte"); } else { console.log("Senha fraca"); } 

ATIVIDADE 03

Arquitetura Cliente-Servidor na Web Como funciona a comunicação entre cliente e servidor 

Quando você digita o endereço de um site em um navegador (como Chrome ou Firefox), o navegador atua como o cliente, e o site que você quer acessar está armazenado em um servidor web. A comunicação entre esses dois acontece através da internet usando um modelo chamado cliente-servidor.

Fluxo de eventos (passo a passo) 

Usuário digita a URL no navegador: Exemplo: https://www.exemplo.com.

Consulta ao DNS (Sistema de Nomes de Domínio):
O navegador precisa descobrir qual é o endereço IP do servidor onde o site está hospedado. Para isso, ele consulta o DNS, que converte www.exemplo.com em um endereço numérico como 192.0.2.1.

Requisição HTTP:
Com o IP, o navegador envia uma requisição HTTP para o servidor. Essa requisição pode pedir, por exemplo, a página index.html.

Resposta HTTP:
O servidor processa a requisição e envia de volta uma resposta HTTP, que contém o conteúdo solicitado (HTML, CSS, imagens, scripts, etc.).

Renderização no navegador:
O navegador recebe os dados e renderiza (exibe) a página para o usuário.

Papéis do Cliente e do Servidor 

Cliente (Navegador):

Inicia a requisição Exibe o conteúdo para o usuário Pode armazenar dados temporários (cookies, cache) 

Servidor (Back-end):

Recebe e interpreta requisições Processa dados (como buscas ou cadastros) Envia a resposta com os arquivos ou dados solicitados Conceitos Importantes 

Requisição HTTP:
Enviada pelo navegador com dados como o tipo de recurso desejado (GET, POST), informações do usuário e cabeçalhos.

Resposta HTTP:
Enviada pelo servidor contendo o status (ex: 200 OK), tipo de conteúdo, e o próprio conteúdo da página.

DNS (Domain Name System):
Funciona como uma "agenda" da internet, transformando nomes de sites em endereços IP que os computadores conseguem  entender  

# Respostas-Aula-HTML
