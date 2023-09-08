<template>
  <div class="alunosForms">
    <label>
      Nome
      <input type="text" v-model="nome" />
    </label>
    <label>
      Nota
      <input type="text" v-model="nota" />
    </label>
    <button class="btnSubmit" @click="chamarFuncaoAdicionarAluno">Enviar</button>
  </div>
</template>

<script>
export default {
  props: {
    funcaoAdicionarAluno: Function
  },
  data() {
    return {
      nome: '',
      nota: ''
    }
  },
  methods: {
    chamarFuncaoAdicionarAluno() {
      this.funcaoAdicionarAluno(this.nome, this.nota)
    }
  }
}
</script>

<style scoped>
.alunosForms {
  display: flex;
  gap: 10px;
  width: max-content;
  align-items: end;
}
label {
  display: flex;
  flex-direction: column;
  gap: 2px;
  color: rgb(43, 0, 255);
  font-size: 24px;
}
input {
  width: 200px;
  height: 30px;
  padding: 5px;
  background-color: rgb(233, 233, 233);
}
input:focus {
  outline-color: rgb(43, 0, 255);;
  outline-style: inset;
  outline-width: 2px;
}
.btnSubmit {
  width: 100px;
  height: 30px;
  background-color: rgb(43, 0, 255);;
  border: none;
  padding: 5px 0;
  border-radius: 10px;
  cursor: pointer;
  color: white;
}
</style>
