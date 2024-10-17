<script>
export default {
  name: "App",
  data() {
    return {
      titulo: "",
      emoji: "",
      apreciaciones: ["Regular", "Bien", "Muy bien", "Increible"],
      apreciacion: "",
      competencias: ["Morfología de un componente", "Directivas","One-Way y Two-Way data binding","Estado","El patrón de diseño MVVM"],
      competencia: [],
      opinion: "",
    };
  },
};
</script>

<template>
  <div id="container">
    <div class="datos py-4">
      <div>
        <label for class="px-3">Título:</label>
        <input type="text" v-model="titulo" />
      </div>
      <hr />

      <div>
        <label for class="px-3">Emoji:</label>
        <select v-model="emoji">
          <option value="💻">💻</option>
          <option value="👩‍💻">👩‍💻</option>
          <option value="👨‍💻">👨‍💻</option>
        </select>
      </div>
      <hr />

      <div class="d-flex">
        <label for="apreciacion" class="px-3">Apreciación:</label>
        <div v-for="(item, index) in apreciaciones" class="px-2">
          <input type="radio" :value="item" v-model="apreciacion" />{{ item }}
        </div>
      </div>
      <hr />

      <div class="d-inline-flex">
        <label for class="px-3">Competencias Aprendidas:</label>
        <div v-for="(compe, index) in competencias" :key="index" class="px-2">
          <input type="checkbox" :value="compe" v-model="competencia" />{{
            compe
          }}
        </div>
      </div>
      <hr />

      <div class="d-flex">
        <label for class="px-3">Opinión:</label>
        <textarea
          name="textarea"
          rows="2"
          cols="50"
          v-model="opinion"
        ></textarea>
      </div>
    </div>
    <div class="texto px-5 py-4">
      <p>{{ emoji }}</p>
      <h3 class="fw-bold">{{ titulo }}</h3>
      <p>Y me parece: {{ apreciacion }}</p>
      <p class="fw-bold">He aprendido:</p>
      <p>{{ competencia }}</p>
      <p class="fw-bold">Mi opinión hasta ahora del framework es:</p>
      <p>{{ opinion }}</p>
    </div>
  </div>
</template>

<style scoped>
#container {
  display: flex;
  justify-content: center;
}

.datos {
  width: 600px;
  border-radius: 30px;
  background-color: black;
  color: white;
}
.texto {
  width: 800px;
  border-radius: 30px;
  border: 1px solid black;
  margin-left: 2rem;
  text-align: center;
}
</style>
