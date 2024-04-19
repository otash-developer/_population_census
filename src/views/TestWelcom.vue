<script>
const model = defineModel()
</script>

<template>
    <input v-model="model" />
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      posts: [],
      authorization: {
        login: '',
        password: null,
      },
      errorMessage: '' // Добавляем переменную для отображения сообщения об ошибке
    };
  },
  methods: {
    async authorizationUser() {
      try {
        const response = await axios.post('http://192.168.137.112:8095/Base/Authorization', this.authorization);
        if (response.data.success) { // Проверяем успешность авторизации
          console.log('Авторизация успешна');
          // Войти в приложение
        } else {
          this.errorMessage = 'Неправильный логин или пароль'; // Ошибка авторизации
        }
      } catch (error) {
        console.error(error);
        this.errorMessage = 'Ошибка сервера'; // Ошибка сервера
      }
    }
  },
};
</script>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      posts: [],
      authorization: {
        login: '',
        password: null,
      }
    };
  },
  methods: {
    async authorizationUser() {
        await axios.post('http://192.168.137.112:8095/Base/Authorization', this.authorization)
        .then((res) => {
            console.log(res, 'efwef');
            this.$router.push('/anket')
        })
        .catch ((error) => {
            console.error(error)
        })
    }
  },
};
</script>