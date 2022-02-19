<template></template>

<script setup lang="ts">
const obj = { prenom: 'Jean', age: 12 };

function render() {
  console.log('Mise à jour du template par Vue.js');
}

const proxy = new Proxy(obj, {
  get(obj, prop) {
    render();
    return obj[prop];
  },
  set(obj, prop) {
    obj[prop] = value;
    render();
    return true;
  },
});

console.log(proxy.prenom);
</script>

<style></style>
