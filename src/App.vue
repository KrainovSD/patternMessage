<template>
  <div class="workplace">
    <div class="userInfo">
      <h1>Bret</h1>
      <div class="userInfo__container">
        <button class="userInfo__loadButton" @click="loadNewRandomUser">
          Загрузить случайного пользователя
        </button>
        <p class="userInfo__title">Имя пользователя</p>
        <input readonly type="text" class="userInfo_inputInfo" :value="name" />
        <p class="userInfo__title">Адресс e-mail</p>
        <input readonly type="text" class="userInfo_inputInfo" :value="email" />
        <p class="userInfo__title">Контактный телефон</p>
        <input
          readonly
          type="text"
          class="userInfo_inputInfo"
          :value="number"
        />
        <p class="userInfo__title">Основной веб-сайт</p>
        <input readonly type="text" class="userInfo_inputInfo" :value="site" />
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
        maxlength="264"
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
        readonly
        id=""
        maxlength="264"
        class="editor__patternField"
      ></textarea>
    </div>
  </div>
</template>

<script>
function random(max) {
  return Math.floor(Math.random() * max);
}
export default {
  name: "App",
  userData: {
    Delphine: {
      name: "Glenna Richert",
      email: "Chaim_McDermott@dana.io",
      number: "(775)976-6974 x41206",
      site: "condrad.com",
    },
    Leopoldo_Corkery: {
      name: "Mrs. Dennis Schullst",
      email: "Karley_Dach@jasper.info",
      number: "1-477-935-8478 x6430",
      site: "ola.org",
    },
    Bret: {
      name: "Leanne Graham",
      email: "Sincere@april.biz",
      number: "1-770-736-8031 x56442",
      site: "hidegard.org",
    },
    "Elwyn.Skilles": {
      name: "Kurtis Welssnat",
      email: "Telly.Hoeger@billy.biz",
      number: "210.067.6132",
      site: "condrad.com",
    },
  },
  data() {
    return {
      name: "",
      email: "",
      number: "",
      site: "",
      editField: "",
    };
  },
  created() {
    this.loadNewRandomUser();
  },
  methods: {
    loadNewRandomUser() {
      let keyList = Object.keys(this.$options.userData);
      let randomID = random(keyList.length);
      let randomUser = Object.fromEntries(
        Object.entries(this.$options.userData[keyList[randomID]])
      );
      if (this.name == randomUser.name) {
        this.loadNewRandomUser();
        return;
      }
      Object.keys(randomUser).forEach((el) => {
        this[el] = randomUser[el];
      });
    },
  },
};
</script>

<style src="../public/css/style.css"></style>
