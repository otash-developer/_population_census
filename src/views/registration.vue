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
     <form id="registrationForm" class="max-w-md mx-auto bg-white px-8 pt-6 pb-8 mb-4 m-5">
        <div class="mb-4">
            <label for="input1" class="block text-gray-700 text-sm font-bold mb-2">Ном:</label>
            <input type="text" id="input1" name="input1" placeholder="Насим" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline rounded-2xl">
            <span id="input1Error" class="text-red-500 hidden">Лутфан ин майдонро пур кунед.</span>
        </div>
        <div class="mb-4">
            <label for="input2" class="block text-gray-700 text-sm font-bold mb-2">Насаб:</label>
            <input type="text" id="input2" name="input2" placeholder="Насимов" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline rounded-2xl">
            <span id="input2Error" class="text-red-500 hidden">Лутфан ин майдонро пур кунед.</span>
        </div>
        <div class="mb-4">
            <label for="input3" class="block text-gray-700 text-sm font-bold mb-2">Номи падар:</label>
            <input type="text" id="input3" name="input3" placeholder="Насимович" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline rounded-2xl">
            <span id="input3Error" class="text-red-500 hidden">Лутфан ин майдонро пур кунед.</span>
        </div>
        <div class="mb-6">
            <label for="input4" class="block text-gray-700 text-sm font-bold mb-2">Номери тел:</label>
            <input type="text" id="input4" name="input4" placeholder="992980000000" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline rounded-2xl">
            <span id="input4Error" class="text-red-500 hidden">Лутфан ин майдонро пур кунед.</span>
        </div>
        <div class="flex items-center justify-center">
            <button type="submit" class="bg-blue-500 text-white hover:bg-blue-700 hover:text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline rounded-2xl">Фиристодан</button>
        </div>
    </form>
</template>