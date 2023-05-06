<script>
export let href='';
</script>

<div class="btn">
   <div class="inner">
      <a {href}>
         <slot/>
      </a>
   </div>
</div>


<style lang="scss">
  .btn {
   border-radius: 5rem;
   background-color: rgba(255, 255, 255, .85);
   border: .15rem solid rgba(0,0,0,0);
   padding: .1rem;
   box-sizing: border-box;
   font-family: "Exo 2";
   font-size: 1.2rem;
   font-weight: 600;
   text-transform: none;
   transition-duration: .3s;

   &:hover {
      transition: ease .3s;
      background-color: rgba(255, 255, 255, .95);
      box-shadow:  #fffffff3 0px 0px 0px .2rem;
      border: .15rem solid rgba(0,0,0,.3);
      
   }

   .inner {
      border: .15rem solid rgba(0,0,0,.1);
      padding: .4rem 3rem;
      border-radius: 5rem;

      a {
         color: black;
         text-decoration: none;
      }
   }
  }
</style>