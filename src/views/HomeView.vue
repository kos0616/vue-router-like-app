<template>
  <div class="bg-gray-200 h-screen shadow px-3 py-5">
    <img alt="Vue logo" src="../assets/logo.png" class="mx-auto mb-2" />
    <p class="text-gray-500 mb-3">Hello! Click item to Start.</p>

    <div class="card">
      <router-link to="/about" class="card-item">Item 1</router-link>
      <router-link to="/about" class="card-item">Item 2</router-link>
    </div>

    <div class="card">
      <router-link to="/about" class="card-item">Item 3</router-link>
      <router-link to="/about" class="card-item">Item 4</router-link>
      <router-link to="/about" class="card-item">Item 5</router-link>
    </div>
  </div>
</template>
