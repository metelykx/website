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



  <div class="aboutMe">
    <h1>Metelykx</h1>
    <p>Hello everyone! My name is Denis Ivashchenko (metelykx is my pseudonym) I am from Crimea and I am 19 years old. I'm currently studying at a local university and programming in Swift and JavaScript.
      My main goal is to develop my products that will help society and cooperate with Pavel Durov.
      I have a passion for programming and I love to create new things. I also like to travel and explore new places. I hope that you will find me interesting and that I can help you in any way.</p>
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
  text-decoration: none; /* Убираем подчеркивание у ссылок по умолчанию */
  position: relative; /* Для позиционирования псевдоэлемента */
  font-family: 'Open Sans', sans-serif;
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
  font-family: 'Open Sans', sans-serif;
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

.aboutMe h1{ 
  font-family: 'Open Sans', sans-serif;
  font-weight:700;
  color:#33CAFF;
  font-size: 45px;
  margin-left:300px;
  margin-top:50px;
}

</style>