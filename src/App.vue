<template>
  <div class="container">
    <MatriculaForm />
    <SegundaTela />
  </div>
</template>

<script>
import MatriculaForm from './components/MatriculaForm';
import SegundaTela from './components/SegundaTela';

export default {
  name: 'app',
  components: {
    MatriculaForm, 
    SegundaTela
  }
}
</script>

<style>
</style>
