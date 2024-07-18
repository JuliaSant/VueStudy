
<template>
    <div class="matricula-form">
       <h1>Matriculas</h1>
          <hr />
          <div class="form-todo form-group">
            <p>
              <input placeholder="nome" type="text" name="author" class="form-control" v-model="name" />
            </p>
            <p>
              <textarea placeholder="Polo" name="polo" class="form-control" v-model="polo"></textarea>
            </p>
            <button v-on:click="addAluno" type="submit" class="btn btn-primary">Matricular</button>
          </div>

          <div class="list-group">
            <div class="list-group-item" v-for="(aluno, index) in alunos" :key="index">
              <span class="comment__author">Aluno: <strong>{{ aluno.name }}</strong></span>
              <p>Polo: {{ aluno.polo }}</p>
              <div>
                <a href="#" title="Excluir" v-on:click.prevent="removeMatricula(index)">Excluir</a>
              </div>
            </div>
          </div>
          <hr />
    </div>
</template>

<script>
export default {
  data() {
        return {
          alunos: [],
          name: '',
          polo: '' ,
        }
      },
      methods: {
        addAluno() {
          if (this.polo.trim() === '') {
            return;
          }
        
          this.alunos.push({
            name: this.name,
            polo: this.polo
          });

          this.name = '';
          this.polo = '';
        },
        removeMatricula(index) {
          this.alunos.splice(index, 1);
        }
      },
}
</script>

