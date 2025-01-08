<template>
  <div class="head">
    <!-- Центральный блок с ссылками -->
    <div class="links">
      <a>About me</a>
      <a>Projects</a>
      <a>Connection</a>
    </div>

    <!-- Блок с картинкой -->
    <div class="butterfly">
      <img src="./assets/butterfly.png" alt="butterfly">
    </div>

    <!-- Правый блок с кнопкой -->
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
        <h2>Converter</h2> <!-- Заголовок над текстом -->
        <p>The essence of the project is currency conversion, and I have worked with
          currencies such as Hryvnia, Ruble, Dram, Dollar, Euro and Pound Sterling. 
          The last three of them are the most popular currencies in the world.</p>
      </div>
    </div>

    <div class = "cars">
      <img src="./assets/aboutMe.png" alt="cars">
      <div class = "cars-text">
        <h2>Cars</h2> 
        <p>
          Thanks to this project, the user will be able to choose the 
          right car using artificial intelligence and order it from another country.
          Also, choose your favorite cars and add them to favorites.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyComponent',
};
</script>

<style>
body {
  background-color: #1F1F1F;
  margin: 0;
  padding: 0;
  font-family: 'Open Sans', sans-serif; /* Шрифт для всего документа */
}

.head {
  display: flex;
  justify-content: space-between; /* Распределяем пространство между элементами */
  align-items: center; /* Выравниваем элементы по центру по вертикали */
  padding: 0 20px; /* Отступы слева и справа */
}

.links {
  display: flex;
  gap: 40px; /* Расстояние между ссылками */
  font-size: 20px;
  padding: 34px 15px;
  cursor: pointer;
}

a {
  color: rgb(196, 196, 196);
  text-decoration: none; /* Убираем подчеркивание у ссылок */
  position: relative; /* Для позиционирования псевдоэлемента */
}

a::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -35px; /* Позиция подчеркивания */
  width: 100%; /* Подчеркивание на всю ширину ссылки */
  height: 4px; /* Толщина подчеркивания */
  background-color: #33CAFF; /* Цвет подчеркивания */
  opacity: 0; /* Начальная прозрачность (подчеркивание скрыто) */
  transition: opacity 0.5s ease; /* Плавное появление подчеркивания */
}

a:hover::after {
  opacity: 1; /* Подчеркивание становится видимым */
}

a:hover {
  color: white;
}

.butterfly {
  position: absolute; /* Абсолютное позиционирование */
  left: 50%; /* Сдвигаем картинку на 50% вправо */
  transform: translateX(-50%); /* Центрируем картинку */
}

.butterfly img {
  width: 100px; /* Ширина картинки */
  height: auto; /* Высота автоматически подстраивается */
}

.buttons {
  margin-left: auto; /* Кнопка сдвигается вправо */
}

.my-button {
  padding: 15px 30px; /* Внутренние отступы кнопки */
  font-size: 20px; /* Размер текста */
  color: white; /* Цвет текста */
  background-color: #33CAFF; /* Цвет фона кнопки */
  border: none; /* Убираем границу */
  border-radius: 10px; /* Закругленные углы */
  cursor: pointer; /* Курсор в виде указателя */
  transition: background-color 0.3s ease; /* Плавное изменение цвета */
}

.my-button:hover {
  background-color: #1F8FB0; /* Цвет фона при наведении */
}

.separator {
  width: 100%; /* Ширина линии */
  border: none; /* Убираем стандартную рамку */
  height: 1px; /* Толщина линии */
  background-color: #383838; /* Цвет линии */
  margin-top: 0px; /* Отступ сверху */
}

.aboutMe {
  display: flex; /* Используем flexbox для расположения текста и картинки */
  align-items: center; /* Выравниваем элементы по центру по вертикали */
  gap: 80px; /* Расстояние между текстом и картинкой */
  max-width: 1200px; /* Ограничение ширины блока */
  margin-left: 10%; /* Отступ слева */
  padding: 20px; /* Отступы внутри блока */
  padding-bottom: 40px;
}

.aboutMe .text {
  flex: 1; /* Текст занимает оставшееся пространство */
}

.aboutMe h1 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: #33CAFF;
  font-size: 45px;
  margin-top: 0;
  margin-bottom: 20px; /* Отступ снизу */
}

.aboutMe p {
  font-family: 'Open Sans', sans-serif;
  font-weight: 400;
  color: white;
  font-size: 25px;
  line-height: 1.6; /* Межстрочный интервал */
  word-wrap: break-word; /* Перенос длинных слов */
}

.aboutMe .image img {
  width: 400px; /* Ширина картинки */
  height: 400px; /* Высота картинки */
  border-radius: 50%; /* Делаем картинку круглой */
  object-fit: cover; /* Сохраняем пропорции картинки */
  margin-left: 40px; /* Сдвигаем картинку правее */
}

.projects h1 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: white;
  font-size: 30px;
  text-align: center;
  margin-bottom: 0px; /* Отступ снизу */
}

.projects .converter {
  display: flex; /* Используем flexbox для выравнивания */
  align-items: center; /* Выравниваем элементы по центру по вертикали */
  gap: 40px; /* Расстояние между картинкой и текстом */
  margin: 20px auto; /* Центрируем блок и добавляем отступы */
  max-width: 1200px; /* Ограничение ширины блока */
}

.projects .converter img {
  width: 300px; /* Ширина картинки */
  height: 300px; /* Высота картинки */
  border-radius: 50%; /* Делаем картинку круглой */
  object-fit: cover; /* Сохраняем пропорции картинки */
}

.projects .converter-text {
  flex: 1; /* Текст занимает оставшееся пространство */
}

.projects .converter h2 {
  font-family: 'Open Sans', sans-serif;
  font-weight: 700;
  color: #33CAFF;
  font-size: 30px;
  margin-top: 0; /* Убираем отступ сверху */
  margin-bottom: 10px; /* Отступ снизу для заголовка */
}

.projects .converter p {
  font-family: 'Open Sans', sans-serif;
  font-weight: 400;
  color: white;
  font-size: 20px;
  line-height: 1.6; /* Межстрочный интервал */
  margin: 0; /* Убираем отступы у текста */
}
</style>