<script>
  
</script>

<template>
    <div class = "head">
        <div class = "links">
          <a>About me</a>
          <a>Projects</a>
          <a>Connection</a>
        </div>


        <div class = "buttons">
          <button type="button">My CV</button>
        </div>
    </div>
    <hr class="separator">
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
  gap: 40px;
  font-size: 20px;
  padding: 34px 15px;
  cursor:pointer;
}

a {
  color: rgb(196, 196, 196);
  text-decoration: none; /* Убираем подчеркивание у ссылок по умолчанию */
  position: relative; /* Для позиционирования псевдоэлемента */
}

a::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -35px; /* Позиция подчеркивания */
  width: 100%; /* Подчеркивание на всю ширину ссылки */
  height: 4px; /* Толщина подчеркивания */
  background-color: #33CAFF; /* Цвет подчеркивания (оранжевый) */
  opacity: 0; /* Начальная прозрачность (подчеркивание скрыто) */
  transition: opacity 0.5s ease; /* Плавное появление подчеркивания */
}

a:hover::after {
  opacity: 1; /* Подчеркивание становится видимым */
  
}
a:hover {
  color: white;
}
.separator {
  width: 100%; /* Ширина линии */
  border: none; /* Убираем стандартную рамку */
  height: 1px; /* Толщина линии */
  background-color: #383838; /* Цвет линии */
  margin-top: 0px; /* Отступ сверху */
}
</style>
