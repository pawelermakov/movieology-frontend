<script lang="ts" setup>
interface Banner {
  id: string
  poster: string
  title: string
  plot: string
  year: string
  genre: string
  duration: string
}

const bannerMock: Banner = {
  id: '1',
  poster: 'https://img-www.tf-cdn.com/movie/2/interstellar-2014.jpeg',
  title: 'Interstellar',
  plot: 'When Earth becomes uninhabitable in the future, a farmer and ex-NASA pilot Joseph Cooper tasks to pilot a spacecraft along with a team of researchers, to find a new planet for humans',
  year: '2014',
  genre: 'Fiction',
  duration: '1h 53min'
}

const color = `url(${bannerMock.poster})`
</script>

<template>
  <div class="banner flex p-8 w-full rounded-2xl drop-shadow-xl cursor-pointer">
    <div class="text-white self-end">
      <h1 class="text-4xl mb-2 font-bold">{{ bannerMock.title }}</h1>
      <p>{{ bannerMock.plot }}</p>
      <div class="mt-6 flex justify-between w-[30%]">
        <span>{{ bannerMock.year }}</span>
        <span>{{ bannerMock.genre }}</span>
        <span>{{ bannerMock.duration }}</span>
      </div>
    </div>
  </div>
</template>

<style>
.banner {
  background: linear-gradient(rgb(255 255 255 / 0%), #262c31d9), v-bind(color);
  background-size: cover;
}
</style>
