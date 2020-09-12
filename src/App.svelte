<center>
 <div style="margin-top: {margin_top}">
  <h1>{angka}</h1>
 </div>
 <div class="full" on:click={tambah}></div>
</center>
<button on:click={reset} class="reset btn btn-danger btn-sm">Reset</button>

<script>
 import {onMount} from "svelte"
 let angka = 0
 let margin_top = `${window.innerHeight / 2 - 40}px`
 onMount(() => {
  if (localStorage.tasbih){
   angka = localStorage.tasbih
  }
 })
 const tambah = () => {
  angka++
  localStorage.setItem("tasbih", angka)
 }
 const reset = () => {
  const tanya = confirm("Reset?")
  if (tanya){
  	angka = 0
  	localStorage.setItem("tasbih", angka)
  }
 }
</script>

<style>
 .full {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
 }
 .reset {
  position: absolute;
  top: 10px;
  left: 10px;
 }
</style>
