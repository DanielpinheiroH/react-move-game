🕹️ Reagir-Mover-Jogo
Um joguinho simples feito em React, onde você controla um quadrado usando o teclado (setas) para coletar moedas 🪙 e ganhar pontos.
Ideal como exemplo de prática com React Hooks, eventos de teclado e controle de estado.

🎥 Demonstração:


🚀 Tecnologias utilizadas
✅ React
✅ React Hooks (useState, useEffect)
✅ JavaScript (ES6+)
✅ CSS (estilização simples)


1️⃣ Criação do projeto React
O projeto foi criado utilizando o Vite, por ser mais leve e rápido para projetos React:

bash
Copiar
Editar
# Criar o projeto com Vite
npm create vite@latest react-mover-jogo --template react

# Acessar a pasta do projeto
cd react-mover-jogo

# Instalar as dependências
npm install

2️⃣ Estrutura inicial do projeto
Criei a seguinte estrutura:
📂 Estrutura do projeto
bash
Copiar
Editar
/src
 └── App.jsx        # Código completo do jogo (player, coin, score, controle)
 └── index.js       # Ponto de entrada do React
 └── App.css        # Estilização do jogo
 
 3️⃣ Lógica do jogo
Implementei a lógica central no App.jsx:

✅ Criei um estado para a posição do player (x, y)
✅ Criei um estado para a posição da moeda (x, y)
✅ Criei um estado para o placar (score)

4️⃣ Controle do teclado
Utilizei um useEffect que escuta o evento keydown da janela:

js
Copiar
Editar
window.addEventListener('keydown', handleKeyDown);
A função handleKeyDown atualiza a posição do player de acordo com as teclas de seta:

ArrowUp → Move para cima

ArrowDown → Move para baixo

ArrowLeft → Move para a esquerda

5️⃣ Colisão do player com a moeda
Outro useEffect foi criado para checar a distância entre o player e a moeda:

js
Copiar
Editar
const dx = playerPos.x - coinPos.x;
const dy = playerPos.y - coinPos.y;
const distance = Math.sqrt(dx * dx + dy * dy);

if (distance < 5) {
  // Colidiu: aumenta o score e gera nova posição da moeda
}
Quando o player colide com a moeda:

✅ Aumenta +1 ponto no score
✅ Gera uma nova posição aleatória para a moeda

6️⃣ Reinício do jogo
Criei um botão "Reiniciar Jogo" que chama uma função resetGame():

js
Copiar
Editar
const resetGame = () => {
  setPlayerPos({ x: 50, y: 50 });
  setCoinPos(getRandomPosition());
  setScore(0);
};
Assim o jogo volta ao estado inicial.

7️⃣ Estilização (CSS)
Criei um container central para o jogo (.game-container)

O player é um quadrado azul (.player)

A moeda é um círculo dourado (.coin)

O placar e botão de reset foram estilizados simples e centralizados

8️⃣ Testes
Testei:

✅ Movimentação com teclado
✅ Coleta de moedas
✅ Placar funcionando
✅ Botão "Reiniciar jogo" funcionando
✅ Responsividade simples

* Resumo *
Resumo de como foi criado:

1️⃣ Criado projeto React com Vite
2️⃣ Estados do player, moeda e score com useState
3️⃣ Controle de teclado com useEffect + keydown
4️⃣ Colisão com distância euclidiana
5️⃣ Botão de reset com resetGame()
6️⃣ Estilo com CSS simples
7️⃣ Testes completos

📚 Tecnologias usadas
React (com Hooks)

Vite

JavaScript ES6+

CSS3

