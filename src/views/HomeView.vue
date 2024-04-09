<script setup>
import TheWelcome from '../components/TheWelcome.vue'
</script>

<template>
  <nav class="bg-blue-500 p-4">
        <div class="max-w-7xl mx-auto px-4">
            <div class="flex justify-between">
                <!-- Логотип -->
                <div class="md:flex md:items-center md:space-x-4">
                    <a href="#" class="text-white text-lg font-semibold language-link" data-lang="tj">Тоҷ</a>
                    <a href="#" class="text-white text-lg font-semibold language-link" data-lang="ru">Ру</a>
                    <a href="#" class="text-white text-lg font-semibold language-link" data-lang="en">Eng</a>
                </div>
                <!-- Навигационные ссылки -->
                <div class="hidden md:flex md:items-center md:space-x-4">
                    <a href="index.html" class="text-white hover:text-gray-300">Главная</a>
                    <a href="#" class="text-white hover:text-gray-300">О нас</a>
                    <a href="#" class="text-white hover:text-gray-300">Услуги</a>
                    <RouterLink class="text-white hover:text-gray-300" to="/regis">
                      Даромад
                    </RouterLink>

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
                <RouterLink class="text-white hover:text-gray-300" to="/regis">
                      Даромад
                </RouterLink>
            </div>
        </div>
    </nav>
     <!-- Контактная информация -->
     <div class="banner">
     <div class="flex items-start justify-between">
        <div class="m-5 md:flex md:items-center md:space-x-4">
           <img src="../assets/logo.png" alt="Баруйхатгирии аҳоли">
           <h1 class="m-5">Баруйхатгирии аҳоли<br>
               Ҷумҳурии Тоҷикистон</h1>
           </div>
           <div>
               <div class="flex">
                   <span class="text-center mt-8 mr-5 "  >Телефон барои тамос: <br> 4-12-43</span>
           </div>
       </div> 
    </div>
    <div class="flex justify-between">
        <div class="btn flex items-center">
          <RouterLink to="/auth">
            <button type="submit" class="bg-white text-black hover:bg-blue-700 hover:text-white  font-bold py-2 px-4 rounded-2xl m-5 ">Бақайдгири</button>
          </RouterLink>
        </div>
    <img src="../assets/8 1.png" alt="photo" class="h-1/2 w-1/2  ">
    </div>
</div>
</template>


<script>
export default {
 
}
</script>