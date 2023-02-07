<template>
  <div class="change-password">
    <div class="change-password__content">
      <img src="@/assets/postmost-logo.png" alt="organization logo">
      <h2 class="change-password__title">Изменение пароля</h2>
      <form action="">
        <label>
          <input type="email" name="" id="">
        </label>
        <div class="change-password__dash"></div>
        <div class="change-password__note">Обязательные поля</div>
        <button>Изменить пароль</button>
      </form>
      <a href="http://" target="_blank" rel="noopener noreferrer" class="change-password__ext-link">Зарегистроваться</a>
      <a href="http://" target="_blank" rel="noopener noreferrer" class="change-password__ext-link">Войти</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChangePassword",
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

  &__dash {
    width: 100%;
    height: 1px;
    background-color: $buttonColor;
  }

  &__note {
    line-height: 22px;
    font-size: 16px;

    &::before {
      content: "*";
      color: #FFB6C1;
    }
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