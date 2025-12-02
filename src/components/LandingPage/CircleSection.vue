<script setup lang="ts">
import Button from '../ui/Button.vue'
</script>

<template>
  <section
    class="mt-[125px] md:mt-[343px] max-w-[1102px] w-full padding relative h-full min-h-[946px] flex items-center justify-center"
  >
    <div
      class="w-[250px] border border-gray-400/20 aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />
    <div
      class="w-[100px] border border-gray-400/20 aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />
    <div
      class="w-[375px] border border-gray-400/20 aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />
    <div
      class="w-[550px] border border-gray-400/20 aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />
    <div
      class="w-[725px] border border-gray-400/20 aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%]"
    />

    <div
      class="w-[350px] aspect-square rounded-full absolute top-[50%] left-[50%] transform translate-x-[-50%] translate-y-[-50%] bg-primary/5 blur-[30px]"
    />

    <div class="relative flex flex-col items-center justify-center">
      <h1>text</h1>
      <Button class="rounded-full! px-8">Learn more</Button>
    </div>
  </section>
</template>
