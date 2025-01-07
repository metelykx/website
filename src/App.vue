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
  bottom: -4px; /* Позиция подчеркивания */
  width: 100%; /* Подчеркивание на всю ширину ссылки */
  height: 4px; /* Толщина подчеркивания */
  background-color: #33CAFF; /* Цвет подчеркивания (оранжевый) */
  opacity: 0; /* Начальная прозрачность (подчеркивание скрыто) */
  transition: opacity 0.5s ease; /* Плавное появление подчеркивания */
}

a:hover::after {
  opacity: 1; /* Подчеркивание становится видимым */
}
</style>
