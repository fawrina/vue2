<template>
  <div>
    <ul>
      <li v-for=»item in menuItems» :key=»item.id»>
        {{ item.text }}
      </li>
    </ul>
  </div>
</template>

<script>
Export default {
  Data() {
    Return {
      menuItems: [
        { id: 1, text: 'Главная' },
        { id: 2, text: 'О нас' },
        { id: 3, text: 'Контакты' }
      ]
    };
  }
};
</script>

<style scoped>
/* Стили, специфичные для этого компонента */
Ul {
  List-style-type: none;
  Padding: 0;
  Margin: 0;
  Display: flex;
  Background-color: #eee;
}

Li {
  Padding: 15px;
  Border-right: 1px solid #ccc;
  Cursor: pointer;
}

Li:last-child {
  Border-right: none;
}
</style>
