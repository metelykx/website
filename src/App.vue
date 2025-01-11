<template>
  <div class="background-container">
    <!-- Контейнер для кругов -->
    <div class="circles-container"></div>

    <!-- Основной контент -->
    <div class="content">
      <!-- Шапка -->
      <div class="head">
        <!-- Бургер-меню (оставлено, но будет скрыто в мобильной версии) -->
        <div class="burger-menu" @click="toggleBurgerMenu">
          <div class="burger-line"></div>
          <div class="burger-line"></div>
          <div class="burger-line"></div>
        </div>

        <!-- Ссылки (оставлены, но будут скрыты в мобильной версии) -->
        <div class="links" :class="{ 'active': isBurgerMenuOpen }">
          <a href="#aboutMe" @click="closeBurgerMenu">{{ translations[currentLanguage].aboutMe }}</a>
          <a href="#project" @click="closeBurgerMenu">{{ translations[currentLanguage].projects }}</a>
          <a href="#connection" @click="closeBurgerMenu">{{ translations[currentLanguage].connection }}</a>
        </div>

        <div class="butterfly">
          <img src="./assets/butterfly.png" alt="butterfly">
        </div>

        <div class="buttons">
          <button class="my-button translate-button" @click="toggleLanguage">
            {{ translations[currentLanguage].toggleLanguage }}
          </button>
          <button class="my-button" @click="redirectToCV">
            {{ translations[currentLanguage].myCV }}
          </button>
        </div>
      </div>
      <hr class="separator">

      <!-- Блок "About Me" -->
      <div class="aboutMe" id="aboutMe">
        <div class="text">
          <h1>Metelykx</h1>
          <p>{{ translations[currentLanguage].aboutMeText }}</p>
        </div>
        <div class="image">
          <img src="./assets/aboutMe.jpg" alt="aboutMe">
        </div>
      </div>

      <!-- Блок "Projects" -->
      <div class="projects" id="project">
        <h1>{{ translations[currentLanguage].projects }}</h1>

        <div class="converter">
          <img src="./assets/card.png" alt="converter">
          <div class="converter-text">
            <h2>{{ translations[currentLanguage].converterTitle }}</h2>
            <p>{{ translations[currentLanguage].converterText }}</p>
          </div>
        </div>

        <div class="cars">
          <img src="./assets/person.png" alt="">
          <div class="cars-text">
            <h2>{{ translations[currentLanguage].carsTitle }}</h2>
            <p>{{ translations[currentLanguage].carsText }}</p>
          </div>
        </div>

        <div class="cart">
          <img src="./assets/cart.png" alt="">
          <div class="cart-text">
            <h2>{{ translations[currentLanguage].marketplaceTitle }}</h2>
            <p>{{ translations[currentLanguage].marketplaceText }}</p>
          </div>
        </div>
      </div>

      <!-- Блок "Connection" -->
      <div class="connection" id="connection">
        <h1>{{ translations[currentLanguage].connection }}</h1>
        <div class="social_media">
          <div class="telegram">
            <a href="https://t.me/metelykx1" target="_blank">
              <img src="./assets/telegram.png" alt="Telegram">
            </a>
            <h3>{{ translations[currentLanguage].telegram }}</h3>
          </div>
          <div class="youtube">
            <a href="https://www.youtube.com/@metelykx" target="_blank">
              <img src="./assets/youtube.png" alt="Youtube">
            </a>
            <h3>{{ translations[currentLanguage].youtube }}</h3>
          </div>
          <div class="github">
            <a href="https://github.com/metelykx" target="_blank">
              <img src="./assets/github.png" alt="Github">
            </a>
            <h3>{{ translations[currentLanguage].github }}</h3>
          </div>
          <div class="gmail">
            <a href="mailto:ivaschenkoodenys@gmail.com" target="_blank">
              <img src="./assets/gmail.png" alt="Gmail">
            </a>
            <h3>{{ translations[currentLanguage].gmail }}</h3>
          </div>
        </div>
      </div>
    </div>

    <!-- Модальное окно для CV -->
    <div v-if="showCVModal" class="modal-overlay">
      <div class="modal">
        <div class="modal-content">
          <h2>{{ translations[currentLanguage].myCV }}</h2>
          <p>Здесь будет содержимое вашего резюме.</p>
          <button @click="closeCVModal" class="my-button">Закрыть</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyComponent',
  data() {
    return {
      currentLanguage: 'en', // Текущий язык (по умолчанию английский)
      showCVModal: false, // Состояние модального окна
      isBurgerMenuOpen: false, // Состояние бургер-меню
      cvLinks: {
        en: 'https://docs.google.com/document/d/1ao88by3tvZzrcbDElZ9HiN26hmYADHadxFYu-c6K2Lc/edit?usp=sharing',
        ru: 'https://docs.google.com/document/d/1O2yhJTHKXwH8lFa38a-U-vgA-fK72Q5s3E3VAxcDWsU/edit?usp=sharing',
      },
      translations: {
        en: {
          aboutMe: 'About me',
          projects: 'Projects',
          connection: 'Connection',
          myCV: 'My CV',
          toggleLanguage: 'Russian',
          aboutMeText: 'Hello everyone! My name is Denis Ivashchenko (metelykx is my pseudonym) I am from Crimea and I am 19 years old. I\'m currently studying at a local university and programming in Swift and JavaScript. My main goal is to develop my products that will help society and cooperate with Pavel Durov. I have a passion for programming and I love to create new things. I also like to travel and explore new places. I hope that you will find me interesting and that I can help you in any way.',
          converterTitle: 'Converter',
          converterText: 'The essence of the project is currency conversion, and I have worked with currencies such as Hryvnia, Ruble, Dram, Dollar, Euro and Pound Sterling. The last three of them are the most popular currencies in the world.',
          carsTitle: 'Cars',
          carsText: 'Thanks to this project, the user will be able to choose the right car using artificial intelligence and order it from another country. Also, choose your favorite cars and add them to favorites.',
          marketplaceTitle: 'Marketplace',
          marketplaceText: 'The marketplace was launched in December 2024. In the region where I live, grocery delivery is poorly developed and it was decided to solve this problem. A marketplace with food delivery from different stores in the region.',
          telegram: 'Telegram Channel',
          youtube: 'Youtube',
          github: 'Github',
          gmail: 'Gmail',
        },
        ru: {
          aboutMe: 'Обо мне',
          projects: 'Проекты',
          connection: 'Связь',
          myCV: 'Моё резюме',
          toggleLanguage: 'Английский',
          aboutMeText: 'Всем привет! Меня зовут Денис Иващенко (metelykx — мой псевдоним). Я из Крыма, мне 19 лет. В настоящее время я учусь в местном университете и программирую на Swift и JavaScript. Моя главная цель — разрабатывать продукты, которые помогут обществу, и сотрудничать с Павлом Дуровым. Я увлечен программированием и люблю создавать новые вещи. Также мне нравится путешествовать и исследовать новые места. Надеюсь, что вы найдете меня интересным, и я смогу вам чем-то помочь.',
          converterTitle: 'Конвертер',
          converterText: 'Суть проекта — конвертация валют. Я работал с такими валютами, как гривна, рубль, драм, доллар, евро и фунт стерлингов. Последние три являются самыми популярными валютами в мире.',
          carsTitle: 'Автомобили',
          carsText: 'Благодаря этому проекту пользователь сможет выбрать подходящий автомобиль с помощью искусственного интеллекта и заказать его из другой страны. Также можно добавлять любимые автомобили в избранное.',
          marketplaceTitle: 'Маркетплейс',
          marketplaceText: 'Маркетплейс был запущен в декабре 2024 года. В регионе, где я живу, доставка продуктов развита слабо, и было решено решить эту проблему. Маркетплейс с доставкой еды из различных магазинов региона.',
          telegram: 'Телеграм-канал',
          youtube: 'Ютуб канал',
          github: 'Гитхаб репозиторий',
          gmail: 'Почта',
        },
      },
    };
  },
  methods: {
    toggleLanguage() {
      this.currentLanguage = this.currentLanguage === 'en' ? 'ru' : 'en';
    },
    openCVModal() {
      this.showCVModal = true; // Открываем модальное окно
    },
    closeCVModal() {
      this.showCVModal = false; // Закрываем модальное окно
    },
    redirectToCV() {
      // Перенаправляем на соответствующую ссылку в зависимости от языка
      window.open(this.cvLinks[this.currentLanguage], '_blank');
    },
    toggleBurgerMenu() {
      this.isBurgerMenuOpen = !this.isBurgerMenuOpen; // Открываем/закрываем бургер-меню
    },
    closeBurgerMenu() {
      this.isBurgerMenuOpen = false; // Закрываем бургер-меню
    },
    createBackgroundCircles() {
      const container = document.querySelector('.circles-container');

      const circles = [
        { size: 200, top: 25, left: 5 },
        { size: 200, top: 40, left: 80 },
        { size: 200, top: 60, left: 20 },
        { size: 200, top: 75, left: 70 },
      ];

      circles.forEach(circle => {
        const div = document.createElement('div');
        div.classList.add('background-circle');
        div.style.width = `${circle.size}px`;
        div.style.height = `${circle.size}px`;
        div.style.top = `${circle.top}%`;
        div.style.left = `${circle.left}%`;
        container.appendChild(div);
      });
    },
  },
  mounted() {
    this.createBackgroundCircles();
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

.links a::after {
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

.my-button.translate-button {
  padding: 10px 20px; /* Уменьшаем padding */
  font-size: 16px; /* Уменьшаем размер шрифта */
  margin-right: 20px; /* Отодвигаем кнопку левее */
  background-color: transparent; /* Прозрачный фон */
  border: 2px solid #33CAFF; /* Граница с цветом #33CAFF */
  color: #33CAFF; /* Цвет текста */
  transition: background-color 0.3s ease, color 0.3s ease, border-color 0.3s ease; /* Плавные переходы */
}

.my-button.translate-button:hover {
  background-color: #33CAFF; /* Фон при наведении */
  color: white; /* Цвет текста при наведении */
  border-color: #33CAFF; /* Цвет границы при наведении */
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

.social_media a {
  outline: none; /* Убираем голубую обводку при наведении */
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
  .head {
    flex-direction: column;
    align-items: center;
    padding: 10px;
  }

  /* Скрываем бургер-меню */
  .burger-menu {
    display: none;
  }

  /* Скрываем ссылки */
  .links {
    display: none;
  }

  /* Уменьшаем размер бабочки */
  .butterfly img {
    width: 60px; /* Уменьшаем размер бабочки для мобильных устройств */
    height: auto;
  }

  /* Центрируем бабочку и кнопки */
  .butterfly {
    transform: translateX(-280%);
  }

  .buttons {
    margin-top: 10px;
  }

  /* Адаптация для блока "About Me" */
  .aboutMe {
    flex-direction: column;
    gap: 20px;
    margin-left: 5%;
    padding: 10px;
  }

  .aboutMe .image img {
    width: 200px;
    height: 200px;
    margin-left: 0;
  }

  /* Адаптация для блока "Projects" */
  .projects .converter,
  .projects .cars,
  .projects .cart {
    flex-direction: column;
    gap: 20px;
    margin: 10px auto;
    padding: 10px;
  }

  .projects .converter img,
  .projects .cars img,
  .projects .cart img {
    width: 150px;
    height: 150px;
  }

  /* Адаптация для блока "Connection" */
  .social_media {
    flex-direction: column;
    gap: 20px;
  }

  .social_media img {
    width: 150px;
    height: 150px;
  }

  /* Адаптация для модального окна */
  .modal {
    max-width: 90%;
  }
}

/* Адаптация для планшетов */
@media (min-width: 768px) and (max-width: 1024px) {
  .head {
    padding: 10px;
  }

  
  .links {
    gap: 20px;
    font-size: 18px;
    padding: 20px;
  }

  .aboutMe {
    gap: 40px;
    margin-left: 5%;
    padding: 20px;
  }

  .aboutMe .image img {
    width: 300px;
    height: 300px;
  }

  .projects .converter,
  .projects .cars,
  .projects .cart {
    gap: 30px;
    margin: 20px auto;
    padding: 20px;
  }

  .projects .converter img,
  .projects .cars img,
  .projects .cart img {
    width: 200px;
    height: 200px;
  }

  .social_media {
    gap: 40px;
  }

  .social_media img {
    width: 150px;
    height: 150px;
  }

  .modal {
    max-width: 70%;
  }
}

/* Адаптация для десктопов */
@media (min-width: 1024px) {
  .head {
    padding: 0 20px;
  }

  .links {
    gap: 40px;
    font-size: 20px;
    padding: 34px 15px;
  }

  .aboutMe {
    gap: 80px;
    margin-left: 10%;
    padding: 20px;
  }

  .aboutMe .image img {
    width: 400px;
    height: 400px;
  }

  .projects .converter,
  .projects .cars,
  .projects .cart {
    gap: 40px;
    margin: 20px auto;
    padding: 20px;
  }

  .projects .converter img,
  .projects .cars img,
  .projects .cart img {
    width: 250px;
    height: 250px;
  }

  .social_media {
    gap: 80px;
  }

  

  .modal {
    max-width: 500px;
  }
}

/* Общие улучшения для всех устройств */
@media (max-width: 768px) {
  .my-button {
    padding: 10px 20px;
    font-size: 16px;
  }

  .my-button.translate-button {
    padding: 8px 16px;
    font-size: 14px;
  }

  .aboutMe h1 {
    font-size: 30px;
  }

  .aboutMe p {
    font-size: 18px;
  }

  .projects h1 {
    font-size: 24px;
  }

  .projects .converter h2,
  .projects .cars h2,
  .projects .cart h2 {
    font-size: 24px;
  }

  .projects .converter p,
  .projects .cars p,
  .projects .cart p {
    font-size: 16px;
  }

  .connection h1 {
    font-size: 24px;
  }

  .social_media h3 {
    font-size: 16px;
  }
}

/* Стили для модального окна */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7); /* Затемнение фона */
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000; /* Убедимся, что модальное окно поверх всего */
}

.modal {
  background-color: #1F1F1F;
  padding: 20px;
  border-radius: 10px;
  max-width: 500px;
  width: 100%;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
}

.modal-content {
  text-align: center;
}

.modal-content h2 {
  color: #33CAFF;
  font-size: 24px;
  margin-bottom: 20px;
}

.modal-content p {
  color: white;
  font-size: 18px;
  margin-bottom: 20px;
}

.modal-content button {
  margin-top: 20px;
}


.background-circle {
  position: absolute;
  border-radius: 50%;
  background-color: rgba(51, 202, 255, 0.1); /* Цвет кругов с прозрачностью */
  z-index: 1; /* Круги на заднем плане */
  animation: float 10s infinite ease-in-out; /* Анимация для кругов */
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