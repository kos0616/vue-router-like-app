<template>
  <div class="bg-gray-100 h-screen shadow px-3 py-5">
    <div class="mb-3">
      <router-link to="/" class="font-bold text-cyan-600 hover:underline">
        ＜ BACK
      </router-link>
    </div>
    <div class="card mb-2">
      <router-link to="/" class="card-item">Item 1</router-link>
      <router-link to="/" class="card-item">Item 2</router-link>
    </div>
    <p class="text-gray-500 mb-5">
      This is an about page. Click "BACK" or Item to go back.
    </p>

    <div class="card">
      <router-link to="/" class="card-item">Item 3</router-link>
      <router-link to="/" class="card-item">Item 4</router-link>
      <router-link to="/" class="card-item">Item 5</router-link>
    </div>
    <p class="text-gray-500">This is an about page.</p>
  </div>
</template>
