<!-- Script JS -->
<script>
  /* Importamos d3 para tenerlo disponible */
  import * as d3 from "d3"

  /*let data = [1000, 1500, 2000, 2500, 3000, 3500, 4000, 4500, 5000]*/
  let data = [76, 51, 57, 43, 50, 43, 50, 39, 31, 28]

  let anio = [10,20,30,40,50,60,70,80,90,100]

  let posicionAnio =[2001,2003,2006,2009,2011,2013,2015,2017,2021,2023]

  let nombrePelicula = ['The Fast and the Furious','2 Fast 2 Furious','The Fast and the Furious: Tokyo Drift',
  'Fast & Furious','Fast Five','Fast & Furious 6','Furious 7','The Fate of the Furious','F9','Fast X']

  let posicion = d3
    .scaleLinear()
    .domain([0, d3.max(anio)])
    .range([0, 100])

  let altura = d3
    .scaleLinear()
    .domain([0, d3.max(data)])
    .range([0, 120])

  let colorLightness = d3
    .scaleLinear()
    .domain([0, d3.max(data)])
    .range(['white', '#ca5d39'])

<svelte:head>
<script async type='text/javascript' src='https://public.flourish.studio/resources/embed.js' />
</svelte:head>

/*
  import { onMount } from 'svelte';
  onMount(() => {
    const script = document.createElement('script');
    script.src = 'https://public.flourish.studio/resources/embed.js';
    script.async = true;
    document.head.appendChild(script);
  }); 

*/

</script>

<!-- Estructura contenido HTML -->


<div class = 'ruedas'>
  <img src="./images/Recurso 7.png" alt="ruedas">
</div>



  <h1>RÁPIDOS Y FURIOSOS <br> La popularidad a lo largo de los años </h1>
  <p class ='subtitulo'>A lo largo de más de dos décadas, la franquicia Rápidos y Furiosos ha capturado la atención de millones de fanáticos alrededor del mundo. Desde carreras callejeras hasta misiones internacionales, cada película ha dejado su huella en el cine de acción y en plataformas como Letterboxd, donde los usuarios registran sus visualizaciones y opiniones. A través de este análisis visual, exploramos la evolución de la popularidad de la saga, utilizando como variables los años de cada película, y las vistas y likes de los propios usuarios de la plataforma Letterboxd.</p>


  <div class="container">
  
    {#each data as num, index}
      <div class="item_wrapper">
        
        <div class="column" style="
        height: {altura(num)}px;
        width:{altura(num)}px;
        background-color: {colorLightness(num)};
        ">
        
      </div>
    </div>
    {/each}

    <div class ='linea'>
    </div>

  </div>



  <div class="container3">
  {#each posicionAnio as nu, index}
  <div class="item_wrapper">

  <p class="anio">{nu}</p>
      </div>
  {/each}
  </div>
  <div class="container4">
    {#each nombrePelicula as n, index}
    <div class="item_wrapper">
    
        <p class="titulo">{n}</p>
    </div>
    {/each}
    </div>

  <div class = 'referencias'>
    <img src="./images/referencias.jpg" alt="referencias">
  </div>

  <br />
  <br />

  <div class= "container2">
    <div class="content">
      <h2>Caos automovilístico</h2>
      <p class='subtitulo'> Este gráfico muestra la evolución de la cantidad de autos destruidos en cada película de la saga Rápidos y Furiosos. Desde la primera del 2001, que destruyó 78 vehículos, el número ha aumentado considerablemente a medida que avanzaban las películas, alcanzando su punto máximo en Fast & Furious 6 con más de 350 autos destruidos. A lo largo de la saga, se observa un incremento constante en la destrucción de vehículos, reflejando el aumento en la magnitud de las escenas de acción.</p>
      <iframe src='https://flo.uri.sh/visualisation/4441475/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/4441475/?utm_source=embed&utm_campaign=visualisation/4441475' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
    </div>
  
    <div class="linea-vertical"></div>

    <div class="content">
      <h2>El tributo</h2>
      <p class = 'subtitulo'>Este gráfico muestra la recaudación total de cada película. A partir de la quinta película, Fast Five, la saga empieza a generar cifras millonarias a nivel global, consolidándose como una de las franquicias más exitosas del cine. La película más taquillera, Furious 7, recaudó más de 1.5 mil millones de dólares, impulsada por el homenaje a Paul Walker y escenas de acción a gran escala.</p>

      <div class="flourish-embed flourish-taquilla" 
      data-src="visualisation/19413320"><script async src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/19413320/thumbnail" width="100%" alt="chart visualization" /></noscript></div>
  </div>
</div>

<p class = 'fuentes'>Fuentes: 
  <a href="https://www.thedrive.com/news/39425/heres-how-many-cars-have-been-destroyed-in-the-fast-furious-movies" target="_blank">TheDrive</a> | <a href="https://gurugamer.com/movies/how-many-cars-destroyed-fast-furious-franchise-9810" target="_blank">GuruGamer</a> | <a href="https://www.boxofficemojo.com/franchise/fr3628568325/" target="_blank">Box Office Mojo</a> | <a href="https://www.syfy.com/syfy-wire/fast-furious-franchise-zooms-past-7-billion-at-global-box-office" target="_blank">SYFY Official Site</a></p>

<div class = 'finish'>
  <img src="./images/Recurso 3.png" alt="finish">
</div>

<footer> De Luca, Martín  |  Jarque, Abril Rocío  </footer>

<!-- Estilos CSS -->
<style>
  /* Estilos CSS */


@font-face {
  font-family: 'DrukWideMedium';
  src: url('/public/tipografia/drukwidemedium.otf') format('opentype');
}

@font-face {
  font-family:'RobotoCondensed-Black';
  src: url('/public/tipografia/RobotoCondensed-Black.ttf') format('truetype');
}

.ruedas{
  z-index: -1; 
  position: absolute; 
  top: 0;
  left: 0;
  width: 100vw; 
  height: 100vh; 
  
}

.referencias{  
  margin-left: 420px;
  margin-top: -20px;
  width: 30%;
  height: 30%;
}

.finish{
  margin-top: 50px;
  margin-left: 420px;
  margin-bottom: -50px;
  width: 30%;
  height: 30%;
  display: flex;
}

.container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 200px;
  border: 1px ;
  max-width:1200px;
  margin-bottom: -20px;
}

.container3 { 
  font-family: 'RobotoCondensed-Black';
  color: #d35939;
  font-size: 25px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  height: 40px;
  border: 2px ;
  border-style: solid;
  border-color: #d35939;
  border-radius: 10px;
    /* son los años */
}

.linea {
  width: 90%;
  height: 2px;
  z-index: -1;
  background-color: #d35939;
  align-items: center;
  position: absolute;
}
  .container4 {
    font-family: 'Bahnschrift';
    letter-spacing: -0.5px;
    font-size: 15px;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    max-width: 1200px;
    height: 100px;
    border: 1px ;
   /* son los titulos */
  }

  p,h1{
    text-align: center;
  }
 
  h1{
    padding-bottom: 10px;
    font-family: 'DrukWideMedium', sans-serif;
    font-size: 36px
    
  }

  h2{
    font-family: 'Bahnschrift';
    letter-spacing: -0.5px;
    padding-bottom: 20px ;
    width: 80%; 
    max-width: 950px; 
    margin: 0 auto;
    font-size: 30px;
  }

  .subtitulo {
    font-family: 'Bahnschrift';
    letter-spacing: -0.5px;
    padding-bottom: 20px ;
    width: 80%; 
    max-width: 950px; 
    margin: 0 auto;
    font-size: 15px;
  }

.fuentes{
  font-family: 'Bahnschrift';
  letter-spacing: -0.5px;
  font-size: 10px;
  color: #d35939;
}
  .item_wrapper {
    display: flex;
    width: 120px;
    flex-direction: column;
    align-items: center;
    gap: 50px;
  }

  .column {
    
    width: 80px;
    height: 100%;
    background-color: #ee0001;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

.linea-vertical {
  border-left: 1.5px dashed #d35939;
  height: 600px; 
  width: 0; 
  margin: 20px; 
  justify-content: center;
  align-items: center;
  
}

  .titulo {
    max-width: 100px;
    text-align: center;
  }
 
  .container2 { 
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  max-width: 1200px;
  padding: 20px;
  border: 2px solid #d35939;
  border-radius: 15px;
  background-color: #fdf7f5;
  
}

.content {
  flex: 5;
  text-align: center;
  justify-content: space-between;
  align-items: center;
}

.flourish-embed {
  width: 100%; 
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  
}

.flourish-chart{
  width: 80%;
  height: 100%;
  margin-left: 60px;
}

.flourish-taquilla {
  margin-top: 60px;
}

footer{
  font-family: 'Bahnschrift';
  letter-spacing: -0.5px;
  font-size: 15px;
  color: #ffffff;
  margin-top: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #d35939;
  position: absolute; 
  left: 0;
  width: 100vw; 
  height: 15vh; 
  text-align: center;
}

</style>
