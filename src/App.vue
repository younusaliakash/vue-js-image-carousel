<script setup>
import { ref } from "vue";

const images = [
  {
    id: "1",
    thumb: "images/bird-gebe4f38c5_1280.jpg",
    full: "images/bird-gebe4f38c5_1280.jpg",
  },

  {
    id: "2",
    thumb: "/images/cat-ge915aad9c_1280.jpg",
    full: "/images/cat-ge915aad9c_1280.jpg",
  },

  {
    id: "3",
    thumb: "/images/kingfisher-g3d86e437c_1280.jpg",
    full: "/images/kingfisher-g3d86e437c_1280.jpg",
  },

  {
    id: "4",
    thumb: "/images/leopard-g0304cc158_1280.jpg",
    full: "/images/leopard-g0304cc158_1280.jpg",
  },

  {
    id: "5",
    thumb: "/images/parrot-g8d2f8a5e8_1280.jpg",
    full: "/images/parrot-g8d2f8a5e8_1280.jpg",
  },
];

const fullImage = ref(`${images[0].full}`);

function setImage(index) {
  fullImage.value = images[index].full;
}
</script>

<template>
  <section class="container">
    <h1 class="text-center text-2xl py-5">Image Carousel</h1>
    <div>
      <div class="mb-5 flex justify-center">
        <img class="rounded cursor-pointer w-2/4 relative" :src="fullImage" />
      </div>

      <div class="flex space-x-2 align-center justify-center">
        <div
          v-for="(image, index) in images"
          :key="index"
          class="cursor-pointer sm:w-20 w-10 rounded-md"
          :class="
            image.full !== fullImage
              ? 'border-4 border-white bg-light-blue-600 opacity-50'
              : 'border-4 border-sky-500 '
          "
        >
          <img @click="setImage(index)" :src="image.thumb" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
