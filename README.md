
# Jogo do número secreto em JavaScript

Este documento descreve como criar um jogo do número secreto usando JavaScript. O jogo consiste em um computador que escolhe um número aleatório de 0 a 100 e o jogador tenta adivinhá-lo em 10 tentativas ou menos.

Pré-requisitos
Para seguir este tutorial, você precisará dos seguintes pré-requisitos:

Um editor de texto ou IDE
Um ambiente de desenvolvimento JavaScript (IDE ou CLI)
Instalando o Node.js
A Node.js é uma plataforma de execução JavaScript de código aberto que permite executar JavaScript fora do navegador. Para instalar a Node.js, siga as instruções no site oficial da Node.js.

Criando um projeto
Depois de instalar a Node.js, crie um novo projeto JavaScript usando o seguinte comando:
```bash
npm init
```
Isso criará um arquivo package.json no diretório atual. Adicione a seguinte dependência ao arquivo package.json:

"dependencies": {
  "express": "^4.17.1"
}
Em seguida, instale a dependência usando o seguinte comando:
```bash
npm install
```
Criando o código do jogo
O código do jogo é dividido em duas partes: a lógica do jogo e a interface do usuário.

A lógica do jogo é responsável por gerar o número secreto, receber os palpites do jogador e determinar se o jogador acertou o número. O seguinte código mostra a lógica do jogo:

JavaScript
```bash
function sorteio() {
  return Math.floor(Math.random() * 101);
}

function palpite(numero) {
  if (numero == numero_secreto) {
    return true;
  } else if (numero < numero_secreto) {
    return "Muito baixo";
  } else {
    return "Muito alto";
  }
}
```
A interface do usuário é responsável por exibir o número de tentativas restantes, o palpite do jogador e a resposta do jogo. O seguinte código mostra a interface do usuário:

JavaScript
```bash
function renderizar() {
  const tentativas = 10 - tentativas_restantes;
  const palpite = prompt("Digite seu palpite: ");
  const resposta = palpite(parseInt(palpite));

  return (
    <div>
      <h1>Jogo do número secreto</h1>
      <p>Tentativas restantes: {tentativas}</p>
      <p>Palpite: {palpite}</p>
      <p>Resposta: {resposta}</p>
    </div>
  );
}
```
Juntando tudo
Para juntar tudo, podemos usar um framework web, como Express, para criar um servidor web. O seguinte código mostra como usar o Express para criar um servidor web que hospeda o jogo:

JavaScript
```bash
const app = express();

app.get("/", (req, res) => {
  res.send(renderizar());
});

app.listen(3000, () => {
  console.log("Servidor iniciado na porta 3000");
});
```
# Para testar o jogo, podemos abrir um navegador e navegar para http://localhost:3000. O jogo deve exibir o número de tentativas restantes, o palpite do jogador e a resposta do jogo.

# Conclusão
Este tutorial forneceu uma introdução básica sobre como criar um jogo do número secreto usando JavaScript. Você pode usar este tutorial como base para criar seu próprio jogo personalizado.
