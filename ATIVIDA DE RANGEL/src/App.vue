<template>
  <main>
    <AlunosForms :funcaoAdicionarAluno="adicionarAluno" />
    <section class="listas">
      <BaseList title="aprovados" :alunos="alunosAprovados" />
      <BaseList title="reprovados" :alunos="alunosReprovados" />
    </section>
  </main>
</template>

<script>
import AlunosForms from './components/AlunosForms.vue'
import BaseList from './components/BaseList.vue'
export default {
  mounted() {
    document.title = 'Atv Facul'
  },
  components: {
    AlunosForms,
    BaseList
  },
  data() {
    return {
      alunosAprovados: [],
      alunosReprovados: []
    }
  },
  methods: {
    adicionarAluno(nome, nota) {
      const novoAluno = { nome, nota }
      if (novoAluno.nota > 6) {
        this.alunosAprovados.push(novoAluno)
      } else {
        this.alunosReprovados.push(novoAluno)
      }
    }
  }
}
</script>

<style scoped>
main {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 35px;
  padding-top: 200px;
}
.listas {
  display: flex;
  gap: 35px;
  align-items: start;
}
</style>
