<script>
  let nome = "Mateus";
  let idade = 19;

  import Header from "../src/lib/Header.svelte";
  import Botao from "./lib/Botao.svelte";

  let contador = $state(0);
  let contadorSubtrai = $state(50);
  let mensagem = $derived(contador < 5 ? "Menor que 5" : "Menor que 10");
  let color = "blue";

  $effect(function () {
    if (contador == 10 || contador == -1) {
      contador = 0;
    }
  });

  function adicionarContador() {
    contador++;
  }

  function subtrairContador() {
    contador--;
  }
</script>

<main>
  <Header nome="Mateus" />
  <h2 style="color: {color}">Contador: {contador}</h2>
  <h2>{mensagem}</h2>

  <button onclick={adicionarContador}>Adicionar</button>
  <button onclick={subtrairContador}>Subtrair</button>

  <Botao texto="Adicionar" cor ="blue" />
  <Botao texto="Adicionar2" cor ="grey" />
  <Botao texto="Adicionar3" cor ="green" />
</main>

<!-- Interpolação de dados -->
<!-- <h1>Introdução ao Svelte - {@html nome} que tem {idade} anos</h1>  -->
