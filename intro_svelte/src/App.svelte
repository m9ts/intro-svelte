<script>
  let nome = "Mateus"
  let idade = 19
  
  import Header from "../src/lib/Header.svelte"

  let contador = $state(0);
  let contadorSubtrai = $state(50);
  let mensagem = $derived(contador < 5 ? "Menor que 5" : "Menor que 10");
  let color = "blue"
  
  $effect(function(){
    if(contador == 10){
      contador = 0;
    }
  })

  function adicionarContador(){
    contador++;
  }
</script>

<main>
  <Header/>
  <h2 style = "color: {color}">Contador: {contador}</h2>
  <h2>{mensagem}</h2>

  <button onclick={adicionarContador}>Adicionar</button>
</main>

<!-- Interpolação de dados -->
<!-- <h1>Introdução ao Svelte - {@html nome} que tem {idade} anos</h1>  -->

