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
     <!-- Саволномаи якум -->
     <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
     <div class="flex items-center ml-5">
        <h1>1. Муносибат ба шахсе, ки дар хона аввал навишта шудааст.</h1>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship1" name="relationship"  value="option1" class="form-radio  text-blue-500">
            <label for="relationship1" class="ml-2 text-gray-500">1. Шахсе, ки аввал навишта шудааст.</label>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship2" name="relationship"  value="option2" class="form-radio  text-blue-500">
            <label for="relationship2" class="ml-2 text-gray-500">2. зан, шавҳар</label>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship2" name="relationship"  value="option2" class="form-radio  text-blue-500">
            <label for="relationship2" class="ml-2 text-gray-500">3. духтар, писар</label>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="c" name="relationship"  value="option3" class="form-radio  text-blue-500">
            <label for="relationship3" class="ml-2 text-gray-500">4. модар, падар</label>
          </div>      
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship4" name="relationship"  value="option4" class="form-radio  text-blue-500">
            <label for="relationship4" class="ml-2 text-gray-500">5. хоҳар, бародар</label>
          </div>
          <div class="flex items-centerc ml-8">
            <input type="radio" id="relationship5" name="relationship"  value="option5" class="form-radio  text-blue-500">
            <label for="relationship5" class="ml-2 text-gray-500">6. хусур, хушдоман, модарарӯс, падарарӯс</label>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship6" name="relationship"  value="option6"  class="form-radio  text-blue-500">
            <label for="relationship7" class="ml-2 text-gray-500">7. келин, домод</label>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship6" name="relationship"  value="option6"  class="form-radio  text-blue-500">
            <label for="relationship7" class="ml-2 text-gray-500">8. бибӣ, бобо</label>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship8" name="relationship"  value="option7" class="form-radio text-blue-500">
            <label for="relationship8" class="ml-2 text-gray-500">9. набера, абера</label>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship9" name="relationship"  value="option8" class="form-radio  text-blue-500">
            <label for="relationship9" class="ml-2 text-gray-500">10. дигар дараҷаи хешагӣ</label>
          </div>
          <div class="flex items-center ml-8">
            <input type="radio" id="relationship10" name="relationship" value="option9" class="form-radio  text-blue-500">
            <label for="relationship10" class="ml-2 text-gray-500">11. хеш не</label>
          </div>
        </div>
<!-- Саволномаи дуюм -->
        <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
          <div class="flex items-center ml-5">
            <h1>2.Ҷинс</h1>
              </div>
              <div class="flex items-center ml-8">
                <input type="radio" id="gender1" name="gender0" value="option10" class="form-radio  text-blue-500">
                <label for="relationship1" class="ml-2 text-gray-500">1. Мард</label>
              </div>
              <div class="flex items-center ml-8">
                <input type="radio" id="gender2" name="gender0"  value="option11" class="form-radio  text-blue-500">
                <label for="relationship2" class="ml-2 text-gray-500">2. Зан</label>
              </div>
            </div>
<!-- Саволномаи сеюм -->
            <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                <div class="flex items-center ml-5">
                  <h1>3. Санаи таваллуд</h1>
                    </div>
                        <div class=" flex items-center ml-8">
                          <label for="birthdayDay"  class="ml-2 text-gray-500">Рӯз, моҳ, сол</label>
                          <input type="date" id="birthdayDay" name="birthdayDay" placeholder="Рӯз" class="m-2 rounded-2xl shadow appearance-none border rounded w-[70px] py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                        </div>
                        <div class=" flex items-center ml-8">
                          <label for="age" class="ml-2 text-gray-500">сину сол</label>
                          <input type="text" id="age" name="age" placeholder="cину сол" class="m-2 rounded-2xl shadow appearance-none border rounded w-[70px] py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
                        </div>
                      </div>
<!-- Саволномаи чорум -->
                  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                    <div class="flex items-center ml-5">
                      <h1>4. Ҷои таваллуд</h1>
                        </div>
                        <div class="flex items-center ml-8">
                          <input type="radio" id="gender3" name="gender" value="option12" class="form-radio  text-blue-500">
                          <label for="relationship1" class="ml-2 text-gray-500">1. Дар ҳамин минтақа</label>
                        </div>
                        <div class="flex items-center ml-8">
                          <input type="radio" id="gender3" name="gender" value="option12" class="form-radio  text-blue-500">
                          <label for="relationship1" class="ml-2 text-gray-500">2. Ноҳия</label>
                        </div>
                        <div class="flex items-center ml-8">
                          <input type="radio" id="gender4" name="gender" value="option13" class="form-radio  text-blue-500">
                          <label for="relationship1" class="ml-2 text-gray-500">3. Шаҳр</label>
                        </div>
                        <div class="flex items-center ml-8">
                          <input type="radio" id="gender5" name="gender"  value="option14" class="form-radio  text-blue-500">
                          <label for="relationship2" class="ml-2 text-gray-500">4. Давлвт</label>
                        </div>
                        <div class="flex justify-center relative">
                          <input type="text" id="gender5" name="gender1"  placeholder="ҷои тавалудро нависед" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline ">
                        </div>
                      </div>
<!-- Саволномаи панҷум -->
                      <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                        <div class="flex items-center ml-5">
                          <h1>6.1. Забони модарӣ</h1>
                            </div>
                            <div class="flex items-center ml-8">
                              <input type="radio" id="gender3" name="gender1" value="option12" class="form-radio  text-blue-500">
                              <label for="relationship1" class="ml-2 text-gray-500">1. тоҷикӣ</label>
                            </div>
                            <div class="flex items-center ml-8">
                              <input type="radio" id="gender4" name="gender1" value="option13" class="form-radio  text-blue-500">
                              <label for="relationship1" class="ml-2 text-gray-500">2. ӯзбекӣ</label>
                            </div>
                            <div class="flex items-center ml-8">
                              <input type="radio" id="gender5" name="gender1"  value="option14" class="form-radio  text-blue-500">
                              <label for="relationship2" class="ml-2 text-gray-500">3. русӣ</label>
                            </div>
                            <div class="flex items-center ml-8">
                              <input type="radio" id="gender5" name="gender1"  value="option14" class="form-radio  text-blue-500">
                              <label for="relationship2" class="ml-2 text-gray-500">4. қирғизи</label>
                            </div>
                            <div class="flex justify-center relative">
                              <input type="text" id="gender5" name="gender1"  placeholder="ё дигар забон" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline ">
                            </div>
                          </div>
<!-- Саволномаи ҳафтум -->
                          <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                            <div class="flex items-center ml-5">
                              <h1>6.2. Дигар забонҳое, ки бо он шумо озодона гап мезанед</h1>
                                </div>
                                <div class="flex items-center ml-8">
                                  <input type="radio" id="gender3" name="gender2" value="option12" class="form-radio  text-blue-500">
                                  <label for="relationship1" class="ml-2 text-gray-500">1. тоҷикӣ</label>
                                </div>
                                <div class="flex items-center ml-8">
                                  <input type="radio" id="gender4" name="gender2" value="option13" class="form-radio  text-blue-500">
                                  <label for="relationship1" class="ml-2 text-gray-500">2. ӯзбекӣ</label>
                                </div>
                                <div class="flex items-center ml-8">
                                  <input type="radio" id="gender5" name="gender2"  value="option14" class="form-radio  text-blue-500">
                                  <label for="relationship2" class="ml-2 text-gray-500">3. русӣ</label>
                                </div>
                                <div class="flex items-center ml-8">
                                  <input type="radio" id="gender5" name="gender2"  value="option14" class="form-radio  text-blue-500">
                                  <label for="relationship2" class="ml-2 text-gray-500">4. қирғизи</label>
                                </div>
                                <div class="flex justify-center relative">
                                  <input type="text" id="gender5" name="gender1"  placeholder="дигар забон" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline ">
                                </div>
                              </div>
                              <!-- Саволномаи нуҳум -->
                              <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                                <div class="flex items-center ml-5">
                                  <h1>7. Пайравӣ ба дин</h1>
                                    </div>
                                    <div class="flex items-center ml-8">
                                      <input type="radio" id="gender1" name="gender3" value="option10" class="form-radio  text-blue-500">
                                      <label for="relationship1" class="ml-2 text-gray-500">Ислом</label>
                                    </div>
                                    <div class="flex items-center ml-8">
                                      <input type="radio" id="gender2" name="gender3"  value="option11" class="form-radio  text-blue-500">
                                      <label for="relationship2" class="ml-2 text-gray-500">Насронӣ</label>
                                    </div>
                                    <div class="flex items-center ml-8">
                                      <input type="radio" id="gender1" name="gender3" value="option10" class="form-radio  text-blue-500">
                                      <label for="relationship1" class="ml-2 text-gray-500">нестам</label>
                                    </div>
                                    <div class="flex items-center ml-8">
                                      <input type="radio" id="gender2" name="gender3"  value="option11" class="form-radio  text-blue-500">
                                      <label for="relationship2" class="ml-2 text-gray-500">рад кардани ҷавоб</label>
                                    </div>
                                  </div>
                                  <!-- Саволномаи даҳум -->
                                  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                                    <div class="flex items-center ml-5">
                                      <h1>8. Шаҳрвандӣ</h1>
                                        </div>
                                        <div class="flex items-center ml-8">
                                          <input type="radio" id="gender3" name="gender4" value="option12" class="form-radio  text-blue-500">
                                          <label for="relationship1" class="ml-2 text-gray-500">1. Ҷумҳурии Тоҷикистон</label>
                                        </div>
                                        <div class="flex items-center ml-8">
                                          <input type="radio" id="gender4" name="gender4" value="option13" class="form-radio  text-blue-500">
                                          <label for="relationship1" class="ml-2 text-gray-500">2. бе шаҳрванди</label>
                                        </div>
                                        <div class="flex items-center ml-8">
                                          <input type="radio" id="gender5" name="gender4"  value="option14" class="form-radio  text-blue-500">
                                          <label for="relationship2" class="ml-2 text-gray-500">3. дигар давлат</label>
                                        </div>
                                        <div class="flex justify-center relative">
                                          <input type="text" id="gender5" name="gender1"  placeholder="ё дигар шаҳрванд" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline ">
                                        </div>
                                      </div>
                                      <!-- Саволномаи ёздаҳум -->
                                      <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                                        <div class="flex items-center ml-5">
                                          <h1>9. Оё кӯдак ба муассисаи томактабӣ меравад?<span class="text-gray-500">(барои кӯдакони синни 1-6 сола)</span></h1>
                                            </div>
                                            <div class="flex items-center ml-8">
                                              <input type="radio" id="gender1" name="gender6" value="option10" class="form-radio  text-blue-500">
                                              <label for="relationship1" class="ml-2 text-gray-500">1. ҳа</label>
                                            </div>
                                            <div class="flex items-center ml-8">
                                              <input type="radio" id="gender2" name="gender6"  value="option11" class="form-radio  text-blue-500">
                                              <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
                                            </div>
                                          </div>
                                          <!-- Саволномаи дувоздаҳум -->
                                          <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                                            <div class="flex items-center ml-5">
                                               <h1>10. Навъи муассисаи таълимӣ, ки дар он таҳсил мекунад <span class="text-gray-500">(барои шахсони  синни 6-60 сола)</span></h1>
                                                 </div>
                                                 <div class="flex items-center ml-8">
                                                   <input type="radio" id="relationship1" name="relationship3"  value="option1" class="form-radio  text-blue-500">
                                                   <label for="relationship1" class="ml-2 text-gray-500">1. муассисаи таҳсилоти умумӣ</label>
                                                 </div>
                                                 <div class="flex items-center ml-8">
                                                   <input type="radio" id="relationship2" name="relationship3"  value="option2" class="form-radio  text-blue-500">
                                                   <label for="relationship2" class="ml-2 text-gray-500">2. муассисаи таҳсилоти имбтидои касбӣ</label>
                                                 </div>
                                                 <div class="flex items-center ml-8">
                                                   <input type="radio" id="relationship2" name="relationship3"  value="option2" class="form-radio  text-blue-500">
                                                   <label for="relationship2" class="ml-2 text-gray-500">3. муассисаи таҳсилоти миёнаи касбӣ</label>
                                                 </div>
                                                 <div class="flex items-center ml-8">
                                                   <input type="radio" id="c" name="relationship3"  value="option3" class="form-radio  text-blue-500">
                                                   <label for="relationship3" class="ml-2 text-gray-500">4. маркази таҳсилоти калонсолон</label>
                                                 </div>      
                                                 <div class="flex items-center ml-8">
                                                   <input type="radio" id="relationship4" name="relationship3"  value="option4" class="form-radio  text-blue-500">
                                                   <label for="relationship4" class="ml-2 text-gray-500">5. муассисаи таҳсилоти олии касбӣ</label>
                                                 </div>
                                                 <div class="flex items-centerc ml-8">
                                                   <input type="radio" id="relationship12" name="relationship3"  value="option5" class="form-radio  text-blue-500">
                                                   <label for="relationship12" class="ml-2 text-gray-500">6. баъд аз муассисаи олии касбӣ</label>
                                                 </div>
                                                 <div class="flex items-center ml-8">
                                                   <input type="radio" id="relationship6" name="relationship3"  value="option6"  class="form-radio  text-blue-500">
                                                   <label for="relationship7" class="ml-2 text-gray-500">7. таҳсил намекунад</label>
                                                 </div>
                                               </div>
                                               <!-- Саволномаи сенздаҳум -->
                                               <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                                                <div class="flex items-center ml-5">
                                                   <h1>11.1 Таҳсилот<span class="text-gray-500">(барои шахсони  синни 10-сола калонсол)</span></h1>
                                                     </div>
                                                     <div class="flex items-center ml-8">
                                                       <input type="radio" id="relationship1" name="relationship7"  value="option1" onchange="handleRadioChange()"  class="form-radio  text-blue-500">
                                                       <label for="relationship1" class="ml-2 text-gray-500">1. ибтидоӣ</label>
                                                     </div>
                                                     <div class="flex items-center ml-8">
                                                       <input type="radio" id="relationship2" name="relationship7"  value="option2" onchange="handleRadioChange()"  class="form-radio  text-blue-500">
                                                       <label for="relationship2" class="ml-2 text-gray-500">2. умумии асосӣ</label>
                                                     </div>
                                                     <div class="flex items-center ml-8">
                                                       <input type="radio" id="relationship2" name="relationship7"  value="option2" onchange="handleRadioChange()"  class="form-radio  text-blue-500">
                                                       <label for="relationship2" class="ml-2 text-gray-500">3. миёнаи умумӣ</label>
                                                     </div>
                                                     <div class="flex items-center ml-8">
                                                       <input type="radio" id="c" name="relationship3"  value="option3" onchange="handleRadioChange()"  class="form-radio  text-blue-500">
                                                       <label for="relationship3" class="ml-2 text-gray-500">4. ибтидои касбӣ</label>
                                                     </div>      
                                                     <div class="flex items-center ml-8">
                                                       <input type="radio" id="relationship4" name="relationship7"  value="option4" onchange="handleRadioChange()"  class="form-radio  text-blue-500">
                                                       <label for="relationship4" class="ml-2 text-gray-500">5. миёнаи касбӣ</label>
                                                     </div>
                                                     <div class="flex items-center ml-8">
                                                      <input type="radio" id="relationship13" name="relationship7" value="option5" onchange="handleRadioChange()" class="form-radio text-blue-500">
                                                      <label for="relationship13" class="ml-2 text-gray-500">6. олии касбӣ</label>
                                                    </div>
                                                    <div id="additionalRadioGroup"></div>
                                                     <div class="flex items-center ml-8">
                                                       <input type="radio" id="relationship6" name="relationship7"  value="option6" onchange="handleRadioChange()"  class="form-radio  text-blue-500">
                                                       <label for="relationship7" class="ml-2 text-gray-500">7. баъд аз муассисаи олии касбӣ</label>
                                                     </div>
                                                     <div class="flex items-center ml-8">
                                                      <input type="radio" id="relationship6" name="relationship7"  value="option6" onchange="handleRadioChange()"  class="form-radio  text-blue-500">
                                                      <label for="relationship7" class="ml-2 text-gray-500">8. таҳсилоти ибтидоӣ надорам </label>
                                                    </div>
                                                   </div>
                                                  <!-- Саволномаи чордаҳум -->
                                                   <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                                                    <div class="flex items-center ml-5">
                                                      <h1>11.2. Оё хонда ва навашта метавонед?<span class="text-gray-500">(барои шахсони  синни 6-9сола ва шахсоне,ки 
                                                        ба саволи 11.1 “таҳсили ибтидоӣ надорад” қайд шудааст)</span></h1>
                                                        </div>
                                                        <div class="flex items-center ml-8">
                                                          <input type="radio" id="gender1" name="gender12" value="option10" class="form-radio  text-blue-500">
                                                          <label for="relationship1" class="ml-2 text-gray-500">1. ҳа</label>
                                                        </div>
                                                        <div class="flex items-center ml-8">
                                                          <input type="radio" id="gender2" name="gender12"  value="option11" class="form-radio  text-blue-500">
                                                          <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
                                                        </div>
                                                      </div>
                                                      <!-- Саволномаи понздаҳум -->
                                                      <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                                                        <div class="flex items-center ml-5">
                                                          <h1>11.3. Оё дараҷаи илми доред? <span class="text-gray-500">(барои шахсони дори таҳсилоти олӣ ва баъд аз 
                                                            муассисаи олии касбӣ)</span></h1>
                                                            </div>
                                                            <div class="flex items-center ml-8">
                                                              <input type="radio" id="gender1" name="gender13" value="option10" class="form-radio  text-blue-500">
                                                              <label for="relationship1" class="ml-2 text-gray-500">1. номзади илм</label>
                                                            </div>
                                                            <div class="flex items-center ml-8">
                                                              <input type="radio" id="gender2" name="gender13"  value="option11" class="form-radio  text-blue-500">
                                                              <label for="relationship2" class="ml-2 text-gray-500">2. доктори илм</label>
                                                            </div>
                                                            <div class="flex items-center ml-8">
                                                              <input type="radio" id="gender1" name="gender13" value="option10" class="form-radio  text-blue-500">
                                                              <label for="relationship1" class="ml-2 text-gray-500">3. доктори PhD</label>
                                                            </div>
                                                            <div class="flex items-center ml-8">
                                                              <input type="radio" id="gender2" name="gender13"  value="option11" class="form-radio  text-blue-500">
                                                              <label for="relationship2" class="ml-2 text-gray-500">4. надорад</label>
                                                            </div>
                                                          </div>
                                                          <!-- Саволномаи шонздаҳум -->
                                                          <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
                                                            <div class="flex items-center ml-5">
                                                               <h1>12. Вазъи оиловӣ? <span class="text-gray-500">(барои шахсони синни 15-сола ва калонсолон)</span></h1>
                                                                 </div>
                                                                 <div class="flex items-center ml-8">
                                                                   <input type="radio" id="relationship1" name="relationship16"  value="option1" class="form-radio  text-blue-500">
                                                                   <label for="relationship1" class="ml-2 text-gray-500">1. ҳеҷ вақат дар ақди никоҳ набудам</label>
                                                                 </div>
                                                                 <div class="flex items-center ml-8">
                                                                   <input type="radio" id="relationship2" name="relationship16"  value="option2" class="form-radio  text-blue-500">
                                                                   <label for="relationship2" class="ml-2 text-gray-500">2. дар ақди никоҳ ба қайд гирифташуда дар САҲШ мебошам</label>
                                                                 </div>
                                                                 <div class="flex items-center ml-8">
                                                                   <input type="radio" id="relationship2" name="relationship16"  value="option2" class="form-radio  text-blue-500">
                                                                   <label for="relationship2" class="ml-2 text-gray-500">3. дар ақди никоҳи беқайд қарор дорам</label>
                                                                 </div>
                                                                 <div class="flex items-center ml-8">
                                                                   <input type="radio" id="c" name="relationship16"  value="option3" class="form-radio  text-blue-500">
                                                                   <label for="relationship3" class="ml-2 text-gray-500">4. марди занмурда (бевамард), бевазан</label>
                                                                 </div>      
                                                                 <div class="flex items-center ml-8">
                                                                   <input type="radio" id="relationship4" name="relationship16"  value="option4" class="form-radio  text-blue-500">
                                                                   <label for="relationship4" class="ml-2 text-gray-500">5. талоқшуда (расман)</label>
                                                                 </div>
                                                                 <div class="flex items-centerc ml-8">
                                                                   <input type="radio" id="relationship12" name="relationship16"  value="option5" class="form-radio  text-blue-500">
                                                                   <label for="relationship12" class="ml-2 text-gray-500">6. чудошуда</label>
                                                                 </div>
                                                               </div>
                                                               <div class="mb-4 flex justify-center">
                                                                <a href="#"><button type="submit" class="bg-blue-500 text-white hover:bg-blue-700 hover:text-white font-bold py-2 px-4 rounded-2xl">Фиристодан</button></a>
                                                            </div>
</template>