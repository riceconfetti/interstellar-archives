<script>
   import Button from "../lib/Button.svelte";
</script>

<div class="hero">
   <h2>Welcome to the</h2>
   <h1>Interstellar <br> Archives</h1>
   
   <div>
      <Button href='/directory'>Directory</Button>
      <Button href='/card-builder'>Card Builder</Button>
   </div>
</div>

<style lang="scss">
   .hero {
      display: flex;
      height: 100vh;
      text-transform: uppercase;
      color: #fff;
      gap: 3em;
      flex-direction:column;
      align-items: center;
      justify-content: center;
      h2 {
         font-family: Bai Jamjuree;
         font-weight: lighter;
         font-size: 1.5rem;
         letter-spacing: .4em;
      }
      h1 {
         font-size: 2.8rem;
         text-align: center;
         letter-spacing: .6em;
         text-shadow: #fff 1px 0 10px;
      }
      div {
         display: flex;
         gap: 3em;
      }
      
   }
</style>