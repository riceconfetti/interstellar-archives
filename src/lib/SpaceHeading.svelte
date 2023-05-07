<script>
   export let title="";
   export let subtitle="";
</script>

<div id="page-heading">
      <h1>{title}</h1>
      <h2>{subtitle}</h2>
</div>

<style lang="scss">
   #page-heading {
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      color: #fff;
      text-transform: uppercase;
      gap: 1rem;
      h1 {
         font-size: 2rem;
         font-family: Audiowide;
         letter-spacing: 10px;
         text-shadow: #EECC65 1px 0px 10px;
      }

      h2 {
         font-family: "Exo 2";
         font-weight: 300;
         font-size: 1.2rem;
         letter-spacing: 10px;
      }
   }
   
</style>