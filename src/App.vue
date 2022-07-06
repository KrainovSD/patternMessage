<template>
  <div class="workplace">
    <div class="userInfo">
      <h1>Bret</h1>
      <div class="userInfo__container">
        <button class="userInfo__loadButton">
          Загрузить случайного пользователя
        </button>
        <p class="userInfo__title">Имя пользователя</p>
        <input type="text" class="userInfo_inputInfo" />
        <p class="userInfo__title">Адресс e-mail</p>
        <input type="text" class="userInfo_inputInfo" />
        <p class="userInfo__title">Контактный телефон</p>
        <input type="text" class="userInfo_inputInfo" />
        <p class="userInfo__title">Основной веб-сайт</p>
        <input type="text" class="userInfo_inputInfo" />
      </div>
    </div>
    <div class="editor">
      <div class="editor__tokensList">
        <p class="editor__titleTokensList">Вставить токен:</p>
        <button class="editor__token">имя</button>
        <button class="editor__token">email</button>
        <button class="editor__token">телефон</button>
        <button class="editor__token">сайт</button>
      </div>
      <textarea
        name=""
        id=""
        cols="30"
        rows="10"
        class="editor__editField"
      ></textarea>
      <div class="editor__storageTools">
        <button class="editor__storageLoadButton">
          Загрузить из localStorage
        </button>
        <button class="editor__storageSaveButton">
          Сохранить в localStorage
        </button>
      </div>
      <textarea
        name=""
        id=""
        cols="30"
        rows="10"
        class="editor__patternField"
      ></textarea>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style src="../public/css/style.css"></style>
