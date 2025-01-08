<template>
  <div class="background-container">
    <!-- Контейнер для кругов -->
    <div class="circles-container"></div>

    <!-- Основной контент -->
    <div class="content">
      <!-- Шапка -->
      <div class="head">
        <div class="links">
          <a>About me</a>
          <a>Projects</a>
          <a>Connection</a>
        </div>

        <div class="butterfly">
          <img src="./assets/butterfly.png" alt="butterfly">
        </div>

        <div class="buttons">
          <button class="my-button">My CV</button>
        </div>
      </div>
      <hr class="separator">

      <!-- Блок "About Me" -->
      <div class="aboutMe">
        <div class="text">
          <h1>Metelykx</h1>
          <p>Hello everyone! My name is Denis Ivashchenko (metelykx is my pseudonym) I am from Crimea and I am 19 years old. I'm currently studying at a local university and programming in Swift and JavaScript.
            My main goal is to develop my products that will help society and cooperate with Pavel Durov.
            I have a passion for programming and I love to create new things. I also like to travel and explore new places. I hope that you will find me interesting and that I can help you in any way.</p>
        </div>
        <div class="image">
          <img src="./assets/aboutMe.jpg" alt="aboutMe">
        </div>
      </div>

      <!-- Блок "Projects" -->
      <div class="projects">
        <h1>Projects</h1>

        <div class="converter">
          <img src="./assets/card.png" alt="converter">
          <div class="converter-text">
            <h2>Converter</h2>
            <p>The essence of the project is currency conversion, and I have worked with
              currencies such as Hryvnia, Ruble, Dram, Dollar, Euro and Pound Sterling.
              The last three of them are the most popular currencies in the world.</p>
          </div>
        </div>

        <div class="cars">
          <img src="./assets/person.png" alt="">
          <div class="cars-text">
            <h2>Cars</h2>
            <p>
              Thanks to this project, the user will be able to choose the
              right car using artificial intelligence and order it from another country.
              Also, choose your favorite cars and add them to favorites.
            </p>
          </div>
        </div>

        <div class="cart">
          <img src="./assets/cart.png" alt="">
          <div class="cart-text">
            <h2>Marketplace</h2>
            <p>
              The marketplace was launched in December 2024. In the region where I live,
              grocery delivery is poorly developed and it was decided to solve this problem.
              A marketplace with food delivery from different stores in the region
            </p>
          </div>
        </div>
      </div>

      <!-- Блок "Connection" -->
      <div class="connection">
        <h1>Connection</h1>
        <div class="social_media">
          <div class="telegram">
            <img src="./assets/telegram.png" alt="">
            <h3>Telegram Channel</h3>
          </div>
          <div class="youtube">
            <img src="./assets/youtube.png" alt="">
            <h3>Youtube</h3>
          </div>
          <div class="github">
            <img src="./assets/github.png" alt="">
            <h3>Github</h3>
          </div>
          <div class="gmail">
            <img src="./assets/gmail.png" alt="">
            <h3>Gmail</h3>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyComponent',
  mounted() {
    this.createBackgroundCircles();
  },
  methods: {
    createBackgroundCircles() {
      const container = document.querySelector('.circles-container');

      // Массив с параметрами кругов (размер, позиция)
      const circles = [
        { size: 200, top: 25, left: 5 },   // Круг 1 (левый верхний угол)
        { size: 200, top: 40, left: 80 }, // Круг 2 (правый верхний угол) 
        { size: 200, top: 60, left: 20 }, 
        {size: 200, top: 75, left:70 }// Круг 4 (правый нижний угол)
    
      ];

      circles.forEach(circle => {
        const div = document.createElement('div');
        div.classList.add('background-circle');

        // Устанавливаем размеры и позиции
        div.style.width = `${circle.size}px`;
        div.style.height = `${circle.size}px`;
        div.style.top = `${circle.top}%`;
        div.style.left = `${circle.left}%`;

        container.appendChild(div);
      });
    },
  },
};
</script>

<style>
body {
  background-color: #1F1F1F;
  margin: 0;
  padding: 0;
  font-family: 'Open Sans', sans-serif;
  overflow: auto; /* Разрешаем скролл */
}

.background-container {
  position: relative;
  overflow: hidden; /* Круги не выходят за пределы контейнера */
}

.circles-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1; /* Круги на заднем плане */
}

.content {
  position: relative;
  z-index: 2; /* Контент на переднем плане */
}

.head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}

.links {
  display: flex;
  gap: 40px;
  font-size: 20px;
  padding: 34px 15px;
  cursor: pointer;
}

a {
  color: rgb(196, 196, 196);
  text-decoration: none;
  position: relative;
}

a::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -35px;
  width: 100%;
  height: 4px;
  background-color: #33CAFF;
  opacity: 0;
  transition: opacity 0.5s ease;
}

a:hover::after {
  opacity: 1;
}

a:hover {
  color: white;
}

.butterfly {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}

.butterfly img {
  width: 100px;
  height: auto;
}

.buttons {
  margin-left: auto;
}

.my-button {
  padding: 15px 30px;
  font-size: 20px;
  color: white;
  background-color: #33CAFF;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.my-button:hover {
  background-color: #1F8FB0;
}

.separator {
  width: 100%;
  border: none;
  height: 1px;
  background-color: #383838;
  margin-top: 0px;
}

.aboutMe {
  display: flex;
  align-items: center;
  gap: 80px;
  max-width: 1200px;
  margin-left: 10%;
  padding: 20px;
  padding-bottom: 40px;
}

.aboutMe .text {
  flex: 1;
}

.aboutMe h1 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: #33CAFF;
  font-size: 45px;
  margin-top: 0;
  margin-bottom: 20px;
}

.aboutMe p {
  font-family: 'Open Sans', sans-serif;
  font-weight: 400;
  color: white;
  font-size: 25px;
  line-height: 1.6;
  word-wrap: break-word;
}

.aboutMe .image img {
  width: 400px;
  height: 400px;
  border-radius: 50%;
  object-fit: cover;
  margin-left: 40px;
}

.projects h1 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: white;
  font-size: 30px;
  text-align: center;
  margin-bottom: 0px;
}

.projects .converter {
  display: flex;
  align-items: center;
  gap: 40px;
  margin: 20px auto;
  max-width: 1200px;
}

.projects .converter img {
  width: 250px;
  height: 250px;
  border-radius: 50%;
  object-fit: cover;
}

.projects .converter-text {
  flex: 1;
}

.projects .converter h2 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: #33CAFF;
  font-size: 30px;
  margin-top: 0;
  margin-bottom: 10px;
}

.projects .converter p {
  font-family: 'Open Sans', sans-serif;
  font-weight: 400;
  color: white;
  font-size: 20px;
  line-height: 1.6;
  margin: 0;
}

.projects .cars {
  display: flex;
  align-items: center;
  gap: 40px;
  margin: 20px auto;
  max-width: 1200px;
}

.projects .cars img {
  width: 250px;
  height: 250px;
  object-fit: cover;
}

.projects .cars-text {
  flex: 1;
}

.projects .cars h2 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: #33CAFF;
  font-size: 30px;
  margin-top: 0;
  margin-bottom: 10px;
}

.projects .cars p {
  font-family: 'Open Sans', sans-serif;
  font-weight: 400;
  color: white;
  font-size: 20px;
  line-height: 1.6;
  margin: 0;
}

.projects .cart {
  display: flex;
  align-items: center;
  gap: 40px;
  margin: 20px auto;
  max-width: 1200px;
}

.projects .cart img {
  width: 250px;
  height: 250px;
  object-fit: cover;
}

.projects .cart-text {
  flex: 1;
}

.projects .cart h2 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: #33CAFF;
  font-size: 30px;
  margin-top: 0;
  margin-bottom: 10px;
}

.projects .cart p {
  font-family: 'Open Sans', sans-serif;
  font-weight: 400;
  color: white;
  font-size: 20px;
  line-height: 1.6;
  margin: 0;
}

.connection {
  text-align: center;
  margin-top: 40px;
}

.connection h1 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: white;
  font-size: 30px;
  margin-bottom: 20px;
}

.social_media {
  display: flex;
  justify-content: center;
  gap: 80px;
  max-width: 1200px;
  margin: 0 auto;
}

.social_media img {
  width: 250px;
  height: 250px;
  object-fit: cover;
}

.social_media h3 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 400;
  color: white;
  font-size: 20px;
  margin-top: 10px;
}

/* Адаптация для мобильных устройств */
@media (max-width: 768px) {
  .social_media {
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }
}

.background-circle {
  position: absolute;
  background-color: rgba(51, 202, 255, 0.1);
  border-radius: 50%;
  z-index: -1; /* Круги на заднем плане */
  animation: float 10s infinite ease-in-out;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}
</style>