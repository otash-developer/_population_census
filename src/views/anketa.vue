<template>
  <nav class="bg-blue-500 p-4">
    <div class="max-w-7xl mx-auto px-4">
      <div class="flex justify-between">
        <!-- Логотип -->
        <div class="md:flex md:items-center space-x-4">
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
        <a href="#" class="block text-white hover:text-gray-300">Главная</a>
        <a href="#" class="block text-white hover:text-gray-300">О нас</a>
        <a href="#" class="block text-white hover:text-gray-300">Услуги</a>
        <a href="#" class="block text-white hover:text-gray-300">Даромад</a>
      </div>
    </div>
  </nav>
  <!-- Саволномаи якум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>1. Муносибат ба шахсе, ки дар хона аввал навишта шудааст.</h1>
    </div>
    <div v-for="familyMember in populationList.familyMember" :is="familyMember.id" class="flex items-center ml-8">
      <label :for="familyMember.name" class="ml-2 text-gray-500">
        <input v-model="anketa.familyMemberId" type="radio" :id="familyMember.name" name="familyMember"
          :value="familyMember.id" class="form-radio  text-blue-500">
        {{ familyMember.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи дуюм -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>2.Ҷинс</h1>
    </div>
    <div v-for="gender in populationList.gender"  :is="gender.id" class="flex items-center ml-8">
      <label :for="gender.name"  class="ml-2 text-gray-500">
        <input v-model="anketa.genderId" type="radio" :id="gender.name" 
        :value="gender.id" class="form-radio  text-blue-500">
        {{ gender.name }}
      </label>
    </div>
    
  </div>
  <!-- Саволномаи сеюм -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>3. Санаи таваллуд</h1>
    </div>
    <div class=" flex items-center ml-8">
      <label for="birthdayDay" class="ml-2 text-gray-500">Рӯз, моҳ, сол</label>
      <input v-model="anketa.dateofBirth" type="date" id="birthdayDay" name="birthdayDay" placeholder="Рӯз"
        class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
    <div class=" flex items-center ml-8">
      <label for="age" class="ml-2 text-gray-500">сину сол</label>
      <input v-model="anketa.age" type="text" id="age" name="age" placeholder="cину сол"
        class="m-2 rounded-2xl shadow appearance-none border-rounded w-70 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
  </div>
  <!-- Саволномаи чорум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>4. Ҷои таваллуд</h1>
    </div>
    <div v-for="placeOfBirth in populationList.placeOfBirth" :is="placeOfBirth.id" class="flex items-center ml-8">
      <label :for="placeOfBirth.name" class="ml-2 text-gray-500">
        <input @change="getPlaces()" v-model="anketa.placeOfBirthId" type="radio" :id="placeOfBirth.name" 
          :value="placeOfBirth.id" class="form-radio  text-blue-500">
        {{ placeOfBirth.name }}
      </label>
    </div>
    <div v-if="anketa.placeOfBirthId !== 1" class="flex justify-center relative">
      <select v-model="anketa.stateId" name=""
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline "
        id="">
        <option v-for="place in places" :is="place.id" :value="place.id">
          {{ place.name }}
        </option>
      </select>
    </div>
  </div>
  <!-- Саволномаи панҷум 1 -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>5. Миллат</h1>
    </div>
    <div  v-for="nationality in populationList.nationality"  :is="nationality.id" class="flex items-center ml-8">
      <label :for="nationality.name" :id="nationality.name" class="ml-2 text-gray-500">
        <input  type="radio" :id="nationality.name"  name="nationality" 
        :value="nationality.id" class="form-radio  text-blue-500">
       {{ nationality.name }}
      </label>
    </div>
    <div class="flex justify-center relative">
      <input type="text" v-model="anketa.nationalityId" placeholder="ё дигар миллат"
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline ">
    </div>
  </div>
  <!-- Саволномаи панҷум 2-->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>6.1. Забони модарӣ</h1>
    </div>
    <div  v-for="nativeLanguage in populationList.nativeLanguage"  :is="nativeLanguage.id" class="flex items-center ml-8">
      <label :for="nativeLanguage.name" :id="nativeLanguage.name" class="ml-2 text-gray-500">
        <input v-model="anketa.nativeLanguageId" type="radio" :id="nativeLanguage.name"  name="nativeLanguage" 
        :value="nativeLanguage.id" class="form-radio  text-blue-500">
        {{ nativeLanguage.name }}
      </label>
    </div>
    <div class="flex justify-center relative">
      <input type="text"  placeholder="ё дигар забон"
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline ">
    </div>
  </div>
  <!-- Саволномаи ҳафтум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>6.2. Дигар забонҳое, ки бо он шумо озодона гап мезанед</h1>
    </div>
    <div v-for=" languageSkills in populationList.languageSkills"  :is="languageSkills.id"  class="flex items-center ml-8">
      <label :for="languageSkills.name"  class="ml-2 text-gray-500">
        <input v-model="anketa.languageSkillsId" :id="languageSkills.name" type="radio" name="languageSkills" 
        :value="languageSkills.id" class="form-radio  text-blue-500">
        {{ languageSkills.name }}
      </label>
    </div>
    <div class="flex justify-center relative">
      <input type="text"  placeholder="дигар забон"
      class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline ">
    </div>
  </div>
  <!-- Саволномаи нуҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>7. Пайравӣ ба дин</h1>
    </div>
    <div v-for="religions in populationList.religions" :is="religions.id" class="flex items-center ml-8">
      <label :for="religions.name" class="ml-2 text-gray-500">
        <input v-model="anketa.religionsId" :id="religions.name" type="radio"  
        :value="religions.id" class="form-radio  text-blue-500">
        {{ religions.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи даҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>8. Шаҳрвандӣ</h1>
    </div>
    <div v-for="citizenship in populationList.citizenship" :is="citizenship.id" class="flex items-center ml-8">
      <label :for="citizenship.name" class="ml-2 text-gray-500">
        <input  @change="getPlaces()" v-model="anketa.citizenshipId" :id="citizenship.name" type="radio"  
        :value="citizenship.id" class="form-radio  text-blue-500">
        {{ citizenship.name }}
      </label>
      </div>
      <div v-if="anketa.citizenshipId == 2" class="flex justify-center relative">
      <select v-model="anketa.citizenshipCountryId" name=""
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline "
        id="">
        <option v-for="state in populationList.state" :is="state.id" value="">
          {{ state.name }}
        </option>
      </select>
    </div>
  </div>
  <!-- Саволномаи ёздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>9. Оё кӯдак ба муассисаи томактабӣ меравад?<span class="text-gray-500">(барои кӯдакони синни 1-6 сола)</span>
      </h1>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio"  v-model="anketa.readingWritingAbility"  :value="true" class="form-radio  text-blue-500">
      <label for="relationship1" class="ml-2 text-gray-500">1. Ха</label>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio"   v-model="anketa.readingWritingAbility" :value="null" class="form-radio  text-blue-500">
      <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
    </div>
  </div>
  <!-- Саволномаи дувоздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>10. Навъи муассисаи таълимӣ, ки дар он таҳсил мекунад <span class="text-gray-500">(барои шахсони синни 6-60
          сола)</span></h1>
    </div>
    <div v-for="educationInstitutions in populationList.educationInstitutions" :is="educationInstitutions.id" class="flex items-center ml-8">
      <label :for="educationInstitutions.name" :id="educationInstitutions.name" class="ml-2 text-gray-500">
        <input v-model="anketa.educationInstitutionsId" :id="educationInstitutions.name" type="radio"  name="educationInstitutions" 
        :value="educationInstitutions.id" class="form-radio  text-blue-500">
        {{ educationInstitutions.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи сенздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>11.1 Таҳсилот<span class="text-gray-500">(барои шахсони синни 10-сола ва калонсол)</span></h1>
    </div>
    <div  v-for="educationalLevel in populationList.educationalLevel" :is="educationalLevel.id" class="flex items-center ml-8">
      <label :for="educationalLevel.name"  class="ml-2 text-gray-500">
        <input v-model="anketa.educationalLevelId" :id="educationalLevel.name" type="radio"  name="educationalLevel" 
        :value="educationalLevel.id" class="form-radio  text-blue-500">
        {{ educationalLevel.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи чордаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>11.2. Оё хонда ва навашта метавонед?<span class="text-gray-500">(барои шахсони синни 6-9сола ва шахсоне,ки
          ба саволи 11.1 “таҳсили ибтидоӣ надорад” қайд шудааст)</span></h1>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.readingWritingAbility"  :value="true" class="form-radio  text-blue-500">
      <label for="relationship1" class="ml-2 text-gray-500">1. ҳа</label>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.readingWritingAbility" :value="null" class="form-radio  text-blue-500">
      <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
      {{ readingWritingAbility}}
    </div>
  </div>
  <!-- Саволномаи понздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>11.3. Оё дараҷаи илми доред? <span class="text-gray-500">(барои шахсони дори таҳсилоти олӣ ва баъд аз
          муассисаи олии касбӣ)</span></h1>
    </div>
    <div v-for="candidatesQualifications in populationList.candidatesQualifications" :is="candidatesQualifications.id" class="flex items-center ml-8">
      <label :for="candidatesQualifications.name"  class="ml-2 text-gray-500">
        <input v-model="anketa.candidatesQualificationsId" :id="candidatesQualifications.name" type="radio" name="candidatesQualifications" 
        :value="candidatesQualifications.id"  class="form-radio  text-blue-500">
        {{ candidatesQualifications.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи шонздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>12. Вазъи оиловӣ? <span class="text-gray-500">(барои шахсони синни 15-сола ва калонсолон)</span></h1>
    </div>
    <div v-for="familyStatus in populationList.familyStatus" :is="familyStatus.id" class="flex items-center ml-8">
      <label :for="familyStatus.name"  class="ml-2 text-gray-500">
        <input type="radio"  v-model="anketa.familyStatusId" :id="familyStatus.name" name="familyStatus"
        :value="familyStatus.id" class="form-radio  text-blue-500">
        {{ familyStatus.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи ҳабдаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>13. Манбаъҳои васоити зиндагӣ нишон дода шавад</h1>
    </div>
    <div v-for="financialSources in populationList.financialSources" :is="financialSources.id" class="flex items-center ml-8">
      <label :for="financialSources.name"  class="ml-2 text-gray-500">
        <input type="radio"  v-model="anketa.financialSourcesId" :id="financialSources.name" 
        :value="financialSources.id" class="form-radio  text-blue-500">
        {{ financialSources.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи ҳаждаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>14. Шумо аз рӯзи таваллудатон дар маҳаллаи аҳоли нишини  мазкур доимӣ истқомат мекунед?</h1>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.placeOfBirthSameAsResidence" :value="true" class="form-radio  text-blue-500">
      <label for="relationship1" class="ml-2 text-gray-500">1. ҳа</label>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio"  v-model="anketa.placeOfBirthSameAsResidence" :value="null" class="form-radio  text-blue-500">
      <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
    </div>
  </div>
  <!-- Саволномаи нуздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1><span class="text-gray-500">Саволҳои 15-20 барои шахсони синни 15-сола калонсол</span>
        <br>15. Оё дар давоми ҳафтаи то оғози баруйҳатгирӣ ягон кор ё машғулияте, ки маош ё даромад биёрад, доштед?</h1>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.incomeThisWeek" :value="true" class="form-radio  text-blue-500">
      <label for="relationship1" class="ml-2 text-gray-500">1. ҳа</label>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.incomeThisWeek" :value="null" class="form-radio  text-blue-500">
      <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
    </div>
  </div>
  <!-- Саволномаи ҳабдаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>16. Дар кадом соҳа машғул будед <span class="text-gray-500">(намуди фаъолияти иқтисодӣ)</span>?</h1>
    </div>
    <div v-for="positionInProfession in populationList.positionInProfession" :is="positionInProfession.id" class="flex items-center ml-8">
      <label :for="positionInProfession.name"  class="ml-2 text-gray-500">
        <input type="radio"  v-model="anketa.positionInProfessionId" :id="positionInProfession.name" 
        :value="positionInProfession.id" class="form-radio  text-blue-500">
        {{ positionInProfession.name }}
      </label>
    </div>
  </div>
   <!-- Саволномаи ҳабдаҳум -->
   <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>17. Машғулияти асосии шумо дар ҳафтаи гузашта<span class="text-gray-500">(касбу ихтисос)</span>?</h1>
    </div>
    <div v-for="mainProfessionPreviousWeek in populationList.mainProfessionPreviousWeek" :is="mainProfessionPreviousWeek.id" class="flex items-center ml-8">
      <label :for="mainProfessionPreviousWeek.name"  class="ml-2 text-gray-500">
        <input type="radio"  v-model="anketa.mainProfessionPreviousWeekId" :id="mainProfessionPreviousWeek.name" 
        :value="mainProfessionPreviousWeek.id" class="form-radio  text-blue-500">
        {{ mainProfessionPreviousWeek.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи нуздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>18. Кори Шумо дар ҳудуди маҳалли аҳолинише, ки истиқомат мекунед, ҷойгир аст?</h1>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.residenceWorkStatus" :value="true" class="form-radio  text-blue-500">
      <label for="relationship1" class="ml-2 text-gray-500">1. ҳа</label>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.residenceWorkStatus" :value="null" class="form-radio  text-blue-500">
      <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
    </div>
  </div>
  <!-- Саволномаи ҳабдаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>19. Мақом дар шуғл</h1>
    </div>
    <div v-for="formerProfessions in populationList.formerProfessions" :is="formerProfessions.id" class="flex items-center ml-8">
      <label :for="formerProfessions.name"  class="ml-2 text-gray-500">
        <input type="radio"  v-model="anketa.formerProfessionsId" :id="formerProfessions.name" 
        :value="formerProfessions.id" class="form-radio  text-blue-500">
        {{ formerProfessions.name }}
      </label>
    </div>
  </div>
  <!-- Саволномаи нуздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1><span class="text-gray-500">саволи 20.1 барои шасонеки, ки ба саволи 15 ”НЕ” ҷавоб додан</span>
        <br>20.1. Шумо дар 4 ҳафтаи охир кор чустуҷӯ намудед? </h1>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.jobSearchLast4Weeks" :value="true" class="form-radio  text-blue-500">
      <label for="relationship1" class="ml-2 text-gray-500">1. ҳа</label>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio"v-model="anketa.jobSearchLast4Weeks" :value="null" class="form-radio  text-blue-500">
      <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
    </div>
  </div>
   <!-- Саволномаи нуздаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>20.2. Агар ба Шумо кори муносибатро пешниҳод мекарадан, метавонистед дар ҳафтаи наздик ба он шурӯъ намоед? </h1>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.jobOffersAcceptedNextWeeks" :value="true"  class="form-radio  text-blue-500">
      <label for="relationship1" class="ml-2 text-gray-500">1. ҳа</label>
    </div>
    <div class="flex items-center ml-8">
      <input type="radio" v-model="anketa.jobOffersAcceptedNextWeeks" :value="null"   class="form-radio  text-blue-500">
      <label for="relationship2" class="ml-2 text-gray-500">2. не</label>
    </div>
  </div>
  <!-- Саволномаи ҳабдаҳум -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1>20.3. Сабабҳои асосии ҷустуҷӯ накардани корро нишон диҳед?</h1>
    </div>
    <div v-for="factorsForNotJobHunting in populationList.factorsForNotJobHunting" :is="factorsForNotJobHunting.id" class="flex items-center ml-8">
      <label :for="factorsForNotJobHunting.name"  class="ml-2 text-gray-500">
        <input type="radio"  v-model="anketa.factorsForNotJobHuntingId" :id="factorsForNotJobHunting.name" 
        :value="factorsForNotJobHunting.id" class="form-radio  text-blue-500">
        {{ factorsForNotJobHunting.name }}
      </label>
    </div>
  </div>
  <!-- kugkuguiyfvkugvuiyv -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1><span class="text-gray-500">Барои занҳои синни 15-сола ва калонсол</span>
        <br> 21.1 Чанд фарзанд таваллуд кардаед <span class="text-gray-500">(бе ҳисоби мурда таваллудшудагон)</span></h1>
    </div>
    <div class="flex items-center ml-8">
      <label for="numberofChildrenBorn1" class="ml-2 text-gray-500">Ҳамаги</label>
      <input type="text" v-model="anketa.numberofChildrenBorn" for="numberofChildrenBorn1"
      class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
    <div class="flex items-center ml-8">
      <label for="numberofChildrenBorn2" class="ml-2 text-gray-500">аз онҳо: писар</label>
      <input type="text" v-model="anketa.numberOfBoysAliv" for="numberofChildrenBorn2"
      class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
    <div class="flex items-center ml-8">
      <label for="numberofChildrenBorn3" class="ml-2 text-gray-500">духтар</label>
      <input type="text" v-model="anketa.numberOfGirlsAlive" for="numberofChildrenBorn3"
       class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
  </div>
  <!-- awao\weomwio\neg -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5">
      <h1><span class="text-gray-500">Барои занҳои синни 15-сола ва калонсол</span>
        <br> 21.2. Аз фарзандони таваллудшуда чантоашон дар қайди ҳаёт ҳастанд?</h1>
    </div>
    <div class="flex items-center ml-8">
      <label for="numberofLivingChildren1" class="ml-2 text-gray-500">Ҳамаги</label>
      <input type="text" v-model="anketa.numberofLivingChildren" for="numberofLivingChildren1"
      class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
    <div class="flex items-center ml-8">
      <label for="numberofLivingChildren2" class="ml-2 text-gray-500">аз онҳо: писар</label>
      <input type="text" v-model="anketa.boy" for="numberofLivingChildren2"
      class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
    <div class="flex items-center ml-8">
      <label for="numberofLivingChildren3" class="ml-2 text-gray-500">духтар</label>
      <input type="text" v-model="anketa.girl" for="numberofLivingChildren3"
      class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
  </div>
  <!-- lep[awlep[ttp[]]] -->
  <div class="max-w-md mx-auto bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 mt-5">
    <div class="flex items-center ml-5"> 
      <h1>21.3. Шумо дар кадом сол фарзанди якуматонро таваллуд кардаед?</h1>
    </div>
    <div class="flex items-center ml-8">
      <label for="ageWhenFirstChildWasBorn1" class="ml-2 text-gray-500">моҳ</label>
      <input type="text"  for="ageWhenFirstChildWasBorn1" 
      class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
    <div class="flex items-center ml-8">
      <label for="ageWhenFirstChildWasBorn2" class="ml-2 text-gray-500">сол</label>
      <input type="data" v-model="anketa.ageWhenFirstChildWasBorn" for="ageWhenFirstChildWasBorn2"
      class="m-2 rounded-2xl shadow appearance-none border-rounded w-100 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
    </div>
  </div>
  <!-- кинопка батн -->
  <div class="mb-4 flex justify-center">
    <button @click="sendPopulationData()"
      class="bg-blue-500 text-white hover:bg-blue-700 hover:text-white font-bold py-2 px-4 rounded-2xl">Фиристодан</button>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      anketa: {
        n1: 0,
        n2: 1,
        n3: 2,
        n4: 3,
        n5: 4,
        familyMemberId: null,
        genderId: null,
        dateofBirth: null,
        age: null,
        placeOfBirthId: 1,
        nationalityId: null,
        nativeLanguageId: null,
        languageSkillsId: null,
        stateId: 1,
        religionId: null,
        citizenshipId: null,
        preschoolAttendance: false, //9
        educationInstitutionsId: null,
        educationalLevelId: null,
        readingWritingAbility: false, //11.2
        candidatesQualificationsId: null,
        familyStatusId: null,
        financialSourcesId: null,
        placeOfBirthSameAsResidence: false, //14
        incomeThisWeek: false, //15
        positionInProfessionId: null,
        mainProfessionPreviousWeekId: null,
        residenceWorkStatus: false, //18
        formerProfessionsId: null,
        jobSearchLast4Weeks: false, //20.1
        jobOffersAcceptedNextWeeks: false, //20.2
        factorsForNotJobHuntingId: null,
        numberofChildrenBorn: null,
        boy: null,
        girl: null,
        numberofLivingChildren: null,
        numberOfBoysAliv: null,
        numberOfGirlsAlive: null,
        ageWhenFirstChildWasBorn: null,
        nationalityName: "",
        nativeLanguageName: "",
        languageSkillName: "",
        religionName: "",
        citizenshipCountryId: 1,
      },
      populationList: [],
      places: []
    };
  },
  mounted() {
    this.getInfo()
  },
  methods: {
    getInfo() {
      axios
        .get('http://192.168.137.112:8095/Base/GetInfo')
        .then(res => {
          this.populationList = res.data
          console.log(res.data.familyMember);
        })
        .catch(err => {
          console.log(err);
        })
    },
    async getPlaces() {
      console.log(this.anketa.placeOfBirthId);
      let city = []
      let region = []
      await this.populationList.region.forEach(el => {
        el.status == "01" ? city.push(el) : region.push(el)
      });
      if (this.anketa.placeOfBirthId !== 1) {
        this.places = this.anketa.placeOfBirthId == 2 ? city : region
        console.log(this.places);
      }
      if (this.anketa.placeOfBirthId == 3) {
        this.anketa.stateId = 2
      } else {
        this.anketa.stateId = 1
      }
      if (this.anketa.citizenshipId == 3) {
        this.anketa.citizenshipCountryId = 2
      } 
    },
    
    sendPopulationData() {
      axios
      .post("http://192.168.137.112:8095/Base/AddProfile", this.anketa)
      .then(res => {
        console.log(res)
        console.log('Успех!');
      })
      .catch(err => {
        console.log(err);
      })
    }
  },
};
</script>
