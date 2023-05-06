<script>
   import {page} from '$app/stores';
</script>

<nav>
   <a href="/">
      <img alt="IA" src="/favicon.png"/>
      Interstellar Archives
   </a>
   <div class="links">
      <a class:active={$page.url.pathname === "/directory"}  href="/directory">Directory</a>
      <a class:active={$page.url.pathname === "/card-builder"} href="/card-builder">Card Builder</a>
   </div> 
</nav>

<style lang="scss">
   nav {
      position:fixed;
      display: flex;
      width: 100%;
      box-sizing: border-box;
      padding: 35px 50px;
      justify-content: space-between;
      align-items: center;
      a {
         font-size: 13px;
         text-transform: uppercase;
         letter-spacing: 10px;
         color:#fff;
         text-shadow: #fff 1px 0 10px;
         background: none;
         text-decoration: none;
         display: flex;
         gap: 20px;
         align-items: center;   
         transition-duration: .4s;
         img {
         background: none;
         width: 4em;
         }

         

         &:hover {
            color:#FFD070;
            transition: ease .4s;
            transform:scale(1.1);
            text-shadow: #fff 1px 0 10px;
         }
      }
      div.links {
         background: none;
         display: flex;
         gap: 60px;
      }

      .active {
         color:#FFD070;
      }
   }
</style>