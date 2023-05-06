<div class="hero">
   <h2>Welcome to the</h2>
   <h1>Interstellar <br> Archives</h1>
   
   <div>
      <a class="btn light" href="/directory">Directory</a>
      <a class="btn dark" href="/card-builder">Card Builder</a>
   </div>
</div>

<style lang="scss">
   .hero {
      display: flex;
      height: 100vh;
      text-transform: uppercase;
      color: #fff;
      gap: 2em;
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
         
         .btn {
            display: flex;
            font-family: "Exo 2";
            font-weight: 600;
            letter-spacing: .1em;
            font-size: 1.2em;
            align-items: center;
            justify-content: center;
            border-radius:5em;
            padding: 1em 2em;
            text-decoration: none;
         }

         .light {
               background-color: #fff;
               color: #000;   
               transition: ease-in-out .5s;
               &:hover {
                  opacity: 50%;
               }
         }

         .dark {
               background-color: #000;
               color: #fff;   
         }
      }
      
   }
</style>