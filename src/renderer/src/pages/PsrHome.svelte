<script lang="ts">
  import 'node-snackbar/dist/snackbar.min.css';
  import Snackbar from 'node-snackbar';
  import PsrButton from "../components/PsrButton.svelte";

  /* URL ou perfil do Instagram do usuário */
  let value: string = "";

  /**
   * Inicializa o download do material
   */
  function startDownload() {
    if (!value) return Snackbar.show({ text: 'Informe uma URL', pos: 'bottom-center' })
  }
</script>

<div class="flex justify-center flex-col gap-4 h-[max-content] items-center w-full">
  <input type="text" placeholder="Informe a URL ou o perfil do usuário" bind:value={value} />
  <PsrButton text="DOWNLOAD" on:click={startDownload} />
</div>

<style>
  input {
    border-radius: 15px;
    color: #333;
    height: 52px;
    padding: 16px 14px;
    width: 508px;
  }

  input::placeholder {
    color: #333;
    font-size: 1rem;
  }

  input:focus-visible {
    outline: none;
  }
</style>
