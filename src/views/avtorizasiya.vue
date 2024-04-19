<template>
    <nav class="bg-blue-500 p-4">
        <div class="max-w-7xl mx-auto px-4">
            <div class="flex justify-between">
                <!-- Логотип -->
                <div class="md:flex md:items-center md:space-x-4" >
                    <a href="#" class="text-white text-lg font-semibold">Тоҷ</a>
                    <a href="#" class="text-white text-lg font-semibold">Ру</a>
                    <a href="#" class="text-white text-lg font-semibold">Eng</a>
                </div>
                <!-- Навигационные ссылки -->
                <div class="hidden md:flex md:items-center md:space-x-4">
                    <a href="index.html" class="text-white hover:text-gray-300">Главная</a>
                    <a href="#" class="text-white hover:text-gray-300">О нас</a>
                    <a href="#" class="text-white hover:text-gray-300">Услуги</a>
                    <a href="registration.html" class="text-white hover:text-gray-300">Даромад</a>
                </div>
                <!-- Кнопка для мобильного меню (отображается только на мобильных устройствах) -->
                <div class="flex md:hidden">
                    <button id="mobile-menu-toggle" class="text-white focus:outline-none">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24">
                            <path fill="currentColor" d="M4 6h16v2H4zm0 5h16v2H4zm0 5h16v2H4z" />
                        </svg>
                    </button>
                </div>
            </div>
        </div>
        <!-- Мобильное меню (отображается только на мобильных устройствах) -->
        <div id="mobile-menu" class="md:hidden hidden">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                <a href="index.html" class="block text-white hover:text-gray-300">Главная</a>
                <a href="#" class="block text-white hover:text-gray-300">О нас</a>
                <a href="#" class="block text-white hover:text-gray-300">Услуги</a>
                <a href="registration.html" class="block text-white hover:text-gray-300">Даромад</a>
            </div>
        </div>
    </nav>
     <!-- Контактная информация -->
     <div class="m-5">
        <h1 class="text-center text-3xl font-bold m-5" >Баруйхатгирии аҳоли 2024</h1>
        <h2 class="text-center text-xl font-semibold m-5">Кабинети шахсии истифодабаранда</h2>
     </div>
     <!-- <form  class="max-w-md mx-auto bg-white px-8 pt-6 pb-8 mb-4 m-5"> -->
        <form @submit.prevent="submit" action="" class="max-w-md mx-auto bg-white px-8 pt-6 pb-8 mb-4 m-5">
        <div class="mb-4">
            <input type="text" id="input1" name="input1" v-model="authorization.login" placeholder="Рақами телефон:" class="shadow appearance-none border-rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline rounded-2xl ">
        </div>
        <div class="mb-4">
            <input type="password" id="input2" name="input2" v-model="authorization.password" placeholder="Рамз:" class="shadow appearance-none border-rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline rounded-2xl">
            <p v-if="passwordError" class="text-red-500 mt-5 flex justify-center">Рақами телефон  ё рамз хато ворид карда шуд</p>
        </div>
        <div class="mb-4 flex justify-center">
            <button  @click="authorizationUser()" class="bg-blue-500 text-white hover:bg-blue-700 hover:text-white font-bold py-2 px-4  focus:outline-none focus:shadow-outline rounded-2xl">Фиристодан</button>
            <!-- <button type="submit" class="bg-blue-500 text-white hover:bg-blue-700 hover:text-white font-bold py-2 px-4 rounded-2xl">Фиристодан</button> -->
        </div>
    </form>
    <!-- </form> -->
</template>
<script>
import axios from 'axios';

export default {
  data() {
    return {
      authorization: {
        login: '',
        password: null,
      },
      loginError: null,
      passwordError: null
    };
  },
  methods: {
    async authorizationUser() {
      try {
        const response = await axios.post('http://192.168.137.112:8095/Base/Authorization', this.authorization);
        console.log(response, 'efwef');
        this.$router.push('/anket');
      } catch (error) {
        console.error(error);
        if (error.response.status === 401) {
          this.passwordError = 'Неверный пароль';
        }
      }
    }
  }
};
</script>
