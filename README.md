HTML:
Login.html:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="./css/reset.css">
    <link rel="stylesheet" href="./css/login.css">

    <script defer src="/js/login.js"></script>

    <title>jogo da memoria | login</title>
</head>
<body>
<form class="login-form">
<div class="login-header">
    <img src="/Imagens/JoJo's_Bizarre_Adventure_logo.png" alt="logo icon">
    <h1>Jogo da memoria</h1>
    <input type="text" placeholder="Name" class="login-input">
    <button type="submit" class="login-button" disabled>Jogar</button>
</div>
</form>
</body>
</html>

Game.html:

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="../css/reset.css">
  <link rel="stylesheet" href="../css/game.css">

  <script defer src="../js/game.js"></script>

  <title>Memory Game</title>
</head>

<body>

  <main>
    <header>
      <span class="player"></span>
      <span>Tempo: <span class="timer">00</span></span>
    </header>

    <div class="grid"></div>
  </main>

</body>

</html>


CSS:
Reset.css:

@import url(https://www.dafont.com/pt/forum/read/201831/jojo-s-bizarre-adventure);
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    list-style: none;
    border: none;
    font-family: 'jojo-s-bizarre-adventure', cursive;
}

Login.css:


.login-form{
    align-items: center;
    display: flex;
    flex-direction: column;
    height: 100vh;
    justify-content: center;
    background-color: #7d12d0;
}

.login-header{
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin-bottom: 50px;
}

.login-header img{
    width: 300px;
}

.login-header h1{
    color: #1e12d0;
    font-size: 1.5em;
}

.login-input{
    border: 2px #1470e8;
    border-radius: 5px;
    color: 	#060329;
    font-size: 1rem;
    margin-bottom: 15px;
    width: 100%;
    max-width: 300px;
    outline: none;
    padding: 8px;
}

.login-button{
    background-color: #417ecc;
    padding: 15px;
    border-radius: 5px;
    color: #1e12d0;
    cursor: pointer;
    font-size: 1rem;
    width: 100%;
    max-width: 300px;
}

.login-button:disabled {
    background-color: #eee;
    color: #aaa;
    cursor: auto;
}


Game.css:

main{
    display: flex;
    flex-direction: column;
    width: 100%;
    background-image: url('../Imagens/backgroud.jpg');
    background-size: cover;
    min-width: 100vh;
    align-items: center;
    justify-content: center;
    padding: 20px 20px 50px;
}
header{
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    max-width: 800px;
    padding: 30px;
    margin: 0 0 30px;
    border-radius: 5px;
    background-color: rgba(255, 255, 255, 0.5);
    font-size: 1.2em;
}

.grid{
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 15px;
    width: 100%;
    max-width: 800px;
    margin: 0 auto;
}

.card{
    width: 100%;
    aspect-ratio: 3/4;
    border-radius: 5px;
    position: relative;
    transition: all 400ms ease;
    transform-style: preserve-3d;
    background-color: #ccc;
}

.face{
    width: 100%;
    height: 100%;
    position: absolute;
    background-size: cover;
    background-position: center;
    border: 2px solid #ffe735;
    border-radius: 5px;
    transition: all 400ms ease;
}

.front{
    transform: rotateY(180deg);
}

.back{
    background-image:url('../Imagens/capa.torot.jpg');
    backface-visibility: hidden;
}

.reveal-card{
    transform: rotateY(180deg);
}

.disabled-card{
    filter: saturate(0);
    opacity: 0.5;
}

@media screen and (max-width:920px) {
  .grid {
    grid-template-columns: repeat(5, 1fr);

  }
}

IMAGENS:
![backgroud](https://github.com/user-attachments/assets/622085f2-1d15-485b-812a-7ceff0d1850c)
![capa](https://github.com/user-attachments/assets/03f12ac7-d456-46b2-a0fd-9a352b01ea95)
![chariot](https://github.com/user-attachments/assets/54d6118f-9848-48fd-ad4e-221f5e62fbae)
![death](https://github.com/user-attachments/assets/c42a6fed-45e0-413c-82df-0ae540bce1dd)
![emperor](https://github.com/user-attachments/assets/86905fa1-e2ec-4902-821a-14088dac72be)
![erophant](https://github.com/user-attachments/assets/70043c32-088a-4fc1-bb81-74a4c153eb99)
![fool](https://github.com/user-attachments/assets/06a9169d-ed52-44ac-8b68-c7a3a6cb359a)
![hermet](https://github.com/user-attachments/assets/15c838e6-0d07-4c05-ae16-ca93e2af66d4)
![JoJo's_Bizarre_Adventure_logo](https://github.com/user-attachments/assets/f228ce1b-b540-4caf-8143-20ce6d7f9868)
![magigian](https://github.com/user-attachments/assets/c7db0cbf-cc4b-406a-b9aa-04a6b1fbab96)
![star](https://github.com/user-attachments/assets/63ce8ffa-b52e-4751-9ca0-a363ecceb7f0)
![tower](https://github.com/user-attachments/assets/23dc5219-a15f-4fe4-8e22-ac5224e3af68)
![word](https://github.com/user-attachments/assets/02005002-0398-4857-9a80-d93f77e68472)


JS:
Login.js:

const input = document.querySelector('.login-input');
const button = document.querySelector('.login-button');
const form = document.querySelector('.login-form');

const ValidateInput =({target})=> {
    if(target.value.length > 2){
        button.removeAttribute('disabled');
        return;
    }
        button.setAttribute('disabled', '');
    
}

const handleSubmit = (event) =>{
    event.preventDefault();

    localStorage.setItem('player', input.value);
    window.location = 'game.html';
}

input.addEventListener('input', ValidateInput);
form.addEventListener('submit', handleSubmit);

Game.js:
const grid = document.querySelector('.grid');
const spanPlayer = document.querySelector('.player');
const timer = document.querySelector('.timer');

const characters = [
  'chariot',
  'death',
  'emperor',
  'erophant',
  'fool',
  'hermet',
  'magigian',
  'star',
  'tower',
  'word',
];

const createElement = (tag, className) => {
  const element = document.createElement(tag);
  element.className = className;
  return element;
}

let firstCard = '';
let secondCard = '';

const checkEndGame = () => {
  const disabledCards = document.querySelectorAll('.disabled-card');

  if (disabledCards.length === 20) {
    clearInterval(this.loop);
    alert(`Parabéns, ${spanPlayer.innerHTML}! Seu tempo foi de: ${timer.innerHTML}`);
  }
}

const checkCards = () => {
  const firstCharacter = firstCard.getAttribute('data-character');
  const secondCharacter = secondCard.getAttribute('data-character');

  if (firstCharacter === secondCharacter) {

    firstCard.firstChild.classList.add('disabled-card');
    secondCard.firstChild.classList.add('disabled-card');

    firstCard = '';
    secondCard = '';

    checkEndGame();

  } else {
    setTimeout(() => {

      firstCard.classList.remove('reveal-card');
      secondCard.classList.remove('reveal-card');

      firstCard = '';
      secondCard = '';

    }, 500);
  }

}

const revealCard = ({ target }) => {

  if (target.parentNode.className.includes('reveal-card')) {
    return;
  }

  if (firstCard === '') {

    target.parentNode.classList.add('reveal-card');
    firstCard = target.parentNode;

  } else if (secondCard === '') {

    target.parentNode.classList.add('reveal-card');
    secondCard = target.parentNode;

    checkCards();

  }
}

const createCard = (character) => {

  const card = createElement('div', 'card');
  const front = createElement('div', 'face front');
  const back = createElement('div', 'face back');

  front.style.backgroundImage = `url('../Imagens/${character}.jpg')`;

  card.appendChild(front);
  card.appendChild(back);

  card.addEventListener('click', revealCard);
  card.setAttribute('data-character', character)

  return card;
}

const loadGame = () => {
  const duplicateCharacters = [...characters, ...characters];

  const shuffledArray = duplicateCharacters.sort(() => Math.random() - 0.5);

  shuffledArray.forEach((character) => {
    const card = createCard(character);
    grid.appendChild(card);
  });
}

const startTimer = () => {

  this.loop = setInterval(() => {
    const currentTime = +timer.innerHTML;
    timer.innerHTML = currentTime + 1;
  }, 1000);

}

window.onload = () => {
  spanPlayer.innerHTML = localStorage.getItem('player');
  startTimer();
  loadGame();
}
