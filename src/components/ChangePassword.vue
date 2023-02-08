<template>
  <div class="change-password">
    <div class="change-password__content">
      <img src="@/assets/postmost-logo.png" alt="organization logo">
      <h2 class="change-password__title">Изменение пароля</h2>
      <form action="">
        <div class="change-password__form-area">
          <label class="change-password__placeholder"> {{!email ? " Email / Логин" : ""}}
            <input class="change-password__input" type="email" v-model="email">
          </label>
          <div class="change-password__dash"></div>
        </div>
        <div class="change-password__form-area">
          <label class="change-password__placeholder"> {{!security ? " Контрольная строка" : ""}}
            <input class="change-password__input" type="text" v-model="security">
          </label>
          <div class="change-password__dash"></div>
          <p v-if="(security !== SECURITY_KEY) && security" class="change-password__alert-message">Неверное контрольное
            слово</p>
        </div>
        <div class="change-password__form-area">
          <label class="change-password__placeholder"> {{!pass ? " Новый пароль" : ""}}
            <input class="change-password__input" :type="visibility ? 'text' : 'password'" v-model="pass">
            <i class="material-icons change-password__visibility" @click="changeVisibility">{{visibility ? "visibility": "visibility_off"}}</i>
          </label>
          <div class="change-password__dash"></div>
          <p v-if="(pass.length < 6) && pass" class="change-password__alert-message">Пароль должен быть не менее 6
            символов </p>
        </div>
        <div class="change-password__form-area">
          <label class="change-password__placeholder"> {{!passCheck ? " Подтверждение пароля" : ""}}
            <input class="change-password__input" type="password" v-model="passCheck">
          </label>
          <div class="change-password__dash"></div>
          <p v-if="(pass !== passCheck) && passCheck" class="change-password__alert-message">Пароли не совпадают</p>
        </div>

        <div class="change-password__note"> Обязательные поля</div>
        <button type="submit" class="change-password__submit-button">Изменить пароль <i class="material-icons change-password__arrow">arrow_forward</i></button>
      </form>
      <a href="http://" target="_blank" rel="noopener noreferrer" class="change-password__ext-link">Зарегистроваться</a>
      <a href="http://" target="_blank" rel="noopener noreferrer" class="change-password__ext-link">Войти</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChangePassword",
  data() {
    return {
      SECURITY_KEY: "cat",
      visibility: false,
      email: "",
      security: "",
      pass: "",
      passCheck: "",
    }
  },
  methods: {
    changeVisibility() {
      this.visibility = !this.visibility
    }
  }
}
</script>

<style lang="scss">
@font-face {
  font-family: Manrope;
  src: url('~@/assets/fonts/Manrope-VariableFont_wght.ttf');
}

@font-face {
  font-family: Inter;
  src: url('~@/assets/fonts/Inter-VariableFont_slnt,wght.ttf');
}

$buttonColor: #2B689B;

.change-password {
  margin: 100px auto;
  min-width: 350px;
  max-width: 500px;
  background-color: #fff;
  box-shadow: 4px 4px 25px rgba(14, 76, 121, 0.18);
  border-radius: 10px;
  font-family: Inter, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $buttonColor;

  &__content {
    padding: 40px 50px;
  }

  &__title {
    font-family: Manrope;
    font-weight: 600;
    line-height: 38px;
    font-size: 28px;
  }

  &__placeholder {
    display: block;
    position: relative;
    text-align: start;
    margin-left: 10px;

    &::before {
      content: "*";
      color: #FFB6C1;
    }
  }

  &__input {
    border: 0;
    position: absolute;
    left: 11px;
    background: none;

    &:focus,
    &:focus-visible,
    &:active {
      outline: none;
    }
  }
  &__visibility {
    font-size: 18px;
    position: absolute;
    left: 90%;
    bottom: 1px;
  }

  &__dash {
    width: 100%;
    height: 1px;
    background-color: $buttonColor;
    margin-top: 10px;
  }

  &__alert-message {
    position: absolute;
    margin: 5px 0 0 0;
    text-align: start;
    margin-left: 10px;
    font-weight: 400;
    font-size: 15px;
    line-height: 21px;
    color: #F13F58;
  }

  &__form-area {
    margin-bottom: 50px;

    &:nth-child(4) {
      margin-bottom: 30px;
    }
  }

  &__note {
    text-align: start;
    margin-left: 10px;
    line-height: 22px;
    font-size: 16px;

    &::before {
      content: "*";
      color: #FFB6C1;
    }
  }

  &__submit-button {
    cursor: pointer;
    position: relative;
    margin: 30px 0;
    padding: 20px 40px;
    background: #FFE292;
    border: 0;
    border-radius: 5px;
    color: #0E406A;
    font-weight: 400;
    font-size: 17px;
    line-height: 21px;
  }
  &__arrow {
    position: absolute;
    top: 25px;
    left: 190px;
    font-size: 14px;
    transform: scaleX(120%);
  }

  &__ext-link {
    text-decoration: none;
    color: $buttonColor;
    font-size: 16px;
    font-weight: 600;
    line-height: 19px;

    &:hover {
      color: #3D7FB7;
    }

    &:last-child {
      margin-left: 35px;
    }
  }
}
</style>