<script setup lang="ts">
import type { Post } from '@/types/post.ts'
import { PostType } from '@/types/post-type.ts'

const props = defineProps<{
  post: Post
}>()
</script>

<template>
  <div
    class="w-1/3 max-sm:w-full bg-white rounded-xl p-[7px] transition duration-300 active:duration-200
           sm:hover:bg-gray-light-2/40 active:scale-[0.97] will-change-transform"
    @touchstart.passive="() => {}"
  >
    <div
      class="h-full flex flex-col gap-[10px] cursor-pointer
             md:max-lg:gap-1.5 max-md:gap-1"
    >
      <div class="w-full flex justify-center">
        <img alt="Empty image" src="../assets/empty-image.png" class="pointer-events-none"/>
      </div>

      <div
        class="max-sm:max-w-[408px] mx-auto flex flex-col gap-[10px] md:max-lg:gap-1.5 max-md:gap-1 size-full"
      >
        <div class="flex gap-2.5 self-start text-gray-dark-3 text-[14px] md:max-lg:text-[12px] max-md:text-[10px]">
          <div v-if="props.post.type === PostType.NEWS">{{ props.post.date }}</div>
          <div v-if="props.post.type === PostType.NEWS">/</div>
          <div>{{ props.post.type }}</div>
        </div>

        <div class="self-start text-[24px] font-bold text-black-gray-text md:max-lg:text-[20px] max-md:text-[16px]">
          {{ props.post.header }}
        </div>

        <div class="self-start text-black-gray-text md:max-lg:text-[14px] max-md:text-[12px]">
          {{ props.post.description }}
        </div>
      </div>
    </div>
  </div>
</template>
