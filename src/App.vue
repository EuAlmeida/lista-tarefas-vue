<template id="td">
  <section>
    <cabecalho :valor="titulo" />
    <div class="container">
      <adicionar-tarefa @adicionarTarefa="adicionarTarefa" />
      <listar-tarefas :tarefas="tarefas" />
      <footer>
        Mudar Titulo da Lista de Tarefas
        <entrada-dados v-model="titulo" type="text" />
      </footer>
    </div>
    <rodape />
  </section>
</template>

<script>
import Cabecalho from "./components/Cabecalho.vue";
import Rodape from "./components/Rodape.vue";
import ListarTarefas from "./components/ListaTarefas.vue";
import AdicionarTarefa from "./components/AdicionarTarefa.vue";
import EntradaDados from "./components/templates/EntradaDados.vue";
export default {
  name: "App",
  components: {
    Cabecalho,
    Rodape,
    ListarTarefas,
    AdicionarTarefa,
    EntradaDados,
  },
  data() {
    return {
      titulo: "Minha lista de tarefas",
      tarefas: [
        { titulo: "Estudar", checked: false },
        { titulo: "Programar", checked: true },
      ],
    };
  },
  methods: {
    adicionarTarefa(novaTarefa) {
      this.tarefas.push({
        titulo: novaTarefa,
        checked: false,
      });
    },
  },
};
</script>

<style>
.container {
  width: 60%;
  margin: 20px auto 0px auto;
  font-family: 'PT Serif', serif;
}

ul li {
  list-style: none;
}

.removed {
  color: gray;
}

.removed label {
  text-decoration: line-through;
}

</style>