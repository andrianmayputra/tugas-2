<template>
  <div id="app">
    <h1 :class="{ 'red-text': isRed, 'italic': isItalic }">Selamat datang di web saya</h1>
    <p></p>
    <input type="text" v-model="inputText" @input="updateText">
    <p :style="{ 'font-weight': fontWeight }">Input teks Anda: {{ inputText }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isRed: false,
      isItalic: false,
      inputText: '',
      fontWeight: 'normal'
    };
  },
  methods: {
    updateText(event) {
      this.inputText = event.target.value;
      if (this.inputText.length > 10) {
        this.isRed = true;
        this.isItalic = true;
        this.fontWeight = 'bold';
      } else {
        this.isRed = false;
        this.isItalic = false;
        this.fontWeight = 'normal';
      }
    }
  }
};
</script>

<style>
#app {
  text-align: center;
  background-color: #f0f0f0;
  padding: 20px;
}

.red-text {
  color: red;
}

.italic {
  font-style: italic;
}
</style>
