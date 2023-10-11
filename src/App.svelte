<script>
  import { onMount } from 'svelte'

  let count = 0

  const saveLocalStorage = () => {
    localStorage.setItem('Count', String(count))
  }

  onMount(() => {
    count = Number(localStorage.getItem('Count'))
  })
</script>

<main class="grid auto-rows-max place-content-center gap-3 h-screen">
  <span class="text-primary-500 text-center text-4xl">{count}</span>
  <section>
    <button
      class="btn text-white bg-gradient-to-br variant-gradient-secondary-tertiary"
      on:click={() => {
        count++
      }}
      on:click={saveLocalStorage}>Incrementar</button
    >
    <button
      class="btn text-white variant-soft"
      on:click={() => {
        count = 0
      }}
      on:click={saveLocalStorage}>Reiniciar</button
    >
    <button
      class="btn text-white bg-gradient-to-br variant-gradient-error-warning"
      on:click={() => {
        count--
      }}
      on:click={saveLocalStorage}>Decrementar</button
    >
  </section>
</main>

<style>
</style>
