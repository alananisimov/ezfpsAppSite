<template>
<h3 class="my-5 text-lg font-medium text-gray-900 dark:text-white">Выберите режим оптимизации:</h3>
                    <ul class="grid w-full gap-3 grid-cols-3">
                        <li>
                            <input name="mode" type="radio" id="easy-option" value="easy" class="hidden peer" @click="changemode('easy')">
                            <label for="easy-option" class="text-gray-500 bg-white border-2 border-gray-200 rounded-lg cursor-pointer dark:hover:text-gray-300 dark:border-gray-700 peer-checked:border-blue-600 hover:text-gray-600 dark:peer-checked:text-gray-300 peer-checked:text-gray-600 hover:bg-gray-50 dark:text-gray-400 dark:bg-gray-800 dark:hover:bg-gray-700 h-full">                           
                                <div class="block">
                                    <img class="mb-2 w-7 h-7" src="https://i.ibb.co/jkSX1v3/low-signal.png">
                                    <div class="w-full text-lg font-semibold">Качество</div>
                                    <div class="w-full text-sm">Очистка файлов, оптимизация запуска, проверка на вредоносное ПО.</div>
                                </div>
                            </label>
                        </li>
                        <li>
                            <input name="mode" type="radio" id="medium-option" value="medium" @click="changemode('medium')">
                            <label for="medium-option" class=" p-5 text-gray-500 bg-white border-2 border-gray-200 rounded-lg cursor-pointer dark:hover:text-gray-300 dark:border-gray-700 peer-checked:border-blue-600 hover:text-gray-600 dark:peer-checked:text-gray-300 peer-checked:text-gray-600 hover:bg-gray-50 dark:text-gray-400 dark:bg-gray-800 dark:hover:bg-gray-700 h-full">
                                <div class="block">
                                    <img class="mb-2 w-7 h-7" src="https://i.ibb.co/KKsnZNK/mobile-signal.png">
                                    <div class="w-full text-lg font-semibold">Производительность</div>
                                    <div class="w-full text-sm">Чистка реестра, дефрагментация диска.</div>
                                </div>
                            </label>
                        </li>
                        <li>
                            <input name="mode" type="radio" id="hard-option" value="hard" @click="changemode('hard')">
                            <label for="hard-option" class="p-5 text-gray-500 bg-white border-2 border-gray-200 rounded-lg cursor-pointer dark:hover:text-gray-300 dark:border-gray-700 peer-checked:border-blue-600 hover:text-gray-600 dark:peer-checked:text-gray-300 peer-checked:text-gray-600 hover:bg-gray-50 dark:text-gray-400 dark:bg-gray-800 dark:hover:bg-gray-700 h-full">
                                <div class="block">
                                    <img class="mb-2 w-7 h-7" src="https://i.ibb.co/gWXgCz3/high-signal.png">
                                    <div class="w-full text-lg font-semibold">Надежность</div>
                                    <div class="w-full text-sm">Настройка сервисов, удаление плохих процессов.</div>
                                </div>
                            </label>
                        </li>
                    </ul>
</template>
<script setup>
let mode = ref('');
function changemode(new_mode){
    console.log(new_mode);
    mode = new_mode;
}

</script>
