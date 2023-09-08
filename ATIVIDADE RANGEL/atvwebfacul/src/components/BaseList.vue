<!-- <template>
  <table v-if="alunos.length > 0">
    <caption>
      {{
        title
      }}
    </caption>
    <tr v-for="(aluno, index) in alunos" :key="index">
      <td>{{ aluno.nome }}</td>
      <td>{{ aluno.nota }}</td>
    </tr>
  </table>
  <table v-else>
    <caption>
      {{
        title
      }}
    </caption>
    <tr>
      <td>Nenhum aluno encontrado</td>
    </tr>
  </table>
</template> -->

<template>
  <table>
    <caption>
      {{
        title
      }}
    </caption>
    <tbody>
      <tr>
        <td>Aluno</td>
        <td>Nota</td>
      </tr>
      <tr v-if="alunos.length === 0">
        <td colspan="2">Nenhum aluno encontrado</td>
      </tr>
      <tr v-else v-for="(aluno, index) in alunos" :key="index">
        <td>{{ aluno.nome }}</td>
        <td>{{ aluno.nota }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    title: String,
    alunos: Array
  }
}
</script>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
  color: black;
  border-color: black;
  width: 350px;
}
caption {
  color: white;
  margin-bottom: 20px;
  font-size: 24px;
}
td {
  border: 1px solid #000000;
  padding: 10px;
  text-align: center;
}

tr {
  background-color: #ffffff;
  font-weight: bold;
}

tr:nth-child(odd) {
  background-color: rgb(43, 0, 255);;
}
</style>
