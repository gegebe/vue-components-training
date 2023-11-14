<script setup>
  const properties = defineProps(["first-name","last-name","gender", "height", "birth", "picture"])
</script>

<template>

  <article>
    <img :src="picture" :alt="firstName">
    <div class="details">
      <p><span>Nombre:</span> {{ firstName }}</p>
      <p><span>Apellido:</span> {{ lastName }}</p>
      <p><span>Género:</span> {{ gender }}</p>
      <p><span>Altura:</span> {{ (height/100).toFixed(2)+"m" }}</p>
      <p><span>Fecha de nacimiento:</span> {{ birth.toLocaleString('es-ES', {year: 'numeric', month: 'numeric', day: 'numeric'}) }}</p>
    </div>
  </article>

</template>

<style scoped>

article {
  display: flex;
  gap:20px;

  margin:10px;
  padding:10px;
  border:1px solid blueviolet;
  box-shadow: 2px 2px blueviolet;
  transition: 0.3s;
}

article:hover{
  box-shadow: 4px 4px blueviolet;
}

article img {
  flex-basis: 100px;
  flex-shrink: 0;
  flex-grow: 0;
  align-items: center;
  justify-content: center;
}

.details {
  display: flex;
  flex-direction: column;
}

.details span {
  color: blueviolet;
  font-weight: 600;
}

</style>