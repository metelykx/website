<script>
  
</script>

<template>
    <div class = "head">
        <div class = "links">
          <a>Обо мне</a>
          <a>Проекты</a>
          <a>Связь</a>
        </div>
    </div>
</template>

<style>
body {
  background-color: #1F1F1F;
}

.head {
  display: flex;
  justify-content: center;
  align-items: center;

}

.links {
  color: white;
  display: flex;
  gap: 20px;
}

a {
  color: white;
  text-decoration: none; /* Убираем подчеркивание у ссылок по умолчанию */
  position: relative; /* Для позиционирования псевдоэлемента */
}

a::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -4px; /* Позиция подчеркивания (можно регулировать) */
  width: 0; /* Начальная ширина подчеркивания */
  height: 4px; /* Толщина подчеркивания (увеличили размер) */
  background-color: #33CAFF; /* Цвет подчеркивания (оранжевый) */
  transition: width 0.3s ease; /* Анимация появления */
}

a:hover::after {
  width: 100%; /* Подчеркивание на всю ширину ссылки */
}
</style>
