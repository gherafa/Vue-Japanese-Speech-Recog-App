<template>
  <h3 
    class="text-2xl md:text-3xl text-center text-gray-400 dark:text-gray-400 min-h-[60px] break-words"
  >
    <div v-if="!kanjiResult" class="text-gray-500 text-center">
      No Kanji generated yet...
    </div>

    <div v-else class="text-2xl font-semibold text-center text-gray-700">
      <p class="text-gray-500 leading-relaxed">Pratice Kanji Pronounciation </p>
      <p class="text-2xl font-bold px-2">{{ kanjiResult.practice_text }}</p>
      <div class="flex justify-between mx-5 px-4 py-2 border-b mb-4">
        <p class="text-gray-700 leading-relaxed">Level </p>
        <p class="text-gray-800 font-medium break-words">{{ kanjiResult.level }}</p>
      </div>
      <div class="flex justify-between mx-5 px-4 py-2 border-b mb-4">
        <p class="text-gray-700 leading-relaxed">Topic </p>
        <p class="text-gray-800 font-medium break-words">{{ kanjiResult.topic }}</p>
      </div>
      <ButtonResultElement :value="kanjiResult.romaji" section="Romaji" />
      <ButtonResultElement :value="kanjiResult.translation" section="Translation" />
    </div>
  </h3>
</template>

<script setup>
import { ref } from 'vue'
import ButtonResultElement from './ButtonResultElement.vue';

const props = defineProps({
  kanjiResult: Object
})
</script>