

Reflexión ético-política sobre las noticias falsas al recontextualizarlas como literatura 
Volver a codificar las noticias falsas de modo que se muestre los mecanismos con que se construye su aparato textual 


El código es el siguiente. A este se le agregó un botón para que el usuario de la página pueda activar el algoritmo, a partir de lo cual en la pantalla se le devuelve el texto generado. Una vez creado el primer texto, el usuario puede hacer clic en el botón para seguir recibiendo distintos textos.  


<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8" />
        <title> Generador de teorías de conspiración </title>

        <style>
          body{
            text-align: center;
            font-size: 16px;
          }
          header{
            padding: 1.6em;
          }
          main{
            margin:0 auto;/* truco para centrar divisiones */
            width: 960px;
          }
          h1{
          	font-family: Georgia, serif; ;
          	font-size: 36px;
          }

          #teoria{
          	display: block;
          	margin: 10px;
          	font-family: brawler;
          	font-size: 3.6em;
            line-height: 1.7em;
            margin: 2em auto;
            padding: 2em;
            border: 2px dashed cyan;
          }
          button{
            border: none;
            color: purple;
            background-color: fuchsia;
            padding: 1em;
            font-family: Helvetica, Arial, sans-serif;
            font-size: 2.8em;
            cursor: pointer;
          }
        </style>
    </head>

    <body>
      <header>
        <h1>Generador de teorías de conspiración #1</h1>
      </header>
      <main>
        <!-- este es el elemento en el que vamos a injectar el poema -->
        <div id="teoria">
        </div>

        <form>
            <!-- con este boton llamanos a la funcion generadora de poemas -->
            <button type="button" onclick="generarTeoria()">Generar teoría de conspiración</button>
        </form>
      </main>



        <script type="text/javascript">

            //EJEMPLO 2: GENERADOR DE HAIKUS

            // estas variables son listas de términos que vamos a usar
            // mas adelante vamos a sacar elementos al azar para armar
            // la composición

            var fuenteseg = ["Un compañero de trabajo", "Una compañera de trabajo", "Un colega", "Una colega", "Una fuente confiable", "Una fuente con información de primera mano", "Una fuente por la que pongo las manos al fuego", "Una fuente intachable", "Una fuente incuestionable"];
            var verbodeclarativo = ["dijo", "contó", "confió", "indicó", "confirmó", "mencionó", "aseguró"];
            var heroe = ["un alto funcionario del gobierno", "un desertor del gobierno", "un funcionario descontento con el gobierno", "un diplomático de alto rango", "un funcionario de la Cancillería", "un trabajador del Ministerio de Exteriores", "un médico cansado de la gestión del gobierno", "una exautoridad del sector médico",  "un político cercano al presidente", "un político cercano al ministro de Salud", "una autoridad cercana al ministro de Salud", "un periodista cercano al gobierno"];
            var accionheroica = ["descubrió el secreto", "desenmascaró el secreto", "accedió a una información secreta", "descifró una comunicación encriptada", "interceptó una comunicación desconocida", "encontró un documento confidencial", "rastreó una comunicación encubierta"];
            var pandemia = ["crisis del coronavirus", "debacle del COVID", "pandemia", "catástrofe del SARS-CoV-2"];
            var simulacro = ["un simulacro hecho", "una simulación hecha", "un ensayo hecho", "un plan hecho", "una operación"];
            var mes = ["enero", "febrero", "marzo", "abril", "mayo", "junio", "julio", "agosto", "setiembre", "octubre", "noviembre", "diciembre"];
            var anio = ["2019", "2018", "2017", "2016"];
            var ciudad = ["Tokio", "Seúl", "Nueva York", "París", "Moscú", "San Petersburgo"];
            var antagonista = ["Bill Gates", "el Fondo Monetario Internacional", "el Banco Mundial", "la Organización Mundial del Comercio", "la Organización para la Cooperación y Desarrollo Económico", "Jeff Bezos", "Elon Musk", "Mark Zuckerberg", "Bernard Arnault"];
            var premeditacion = ["avaló", "aprobó", "financió", "propuso", "orquestó", "gerenció", "firmó", "apoyó", "respaldó", "garantizó", "obligó"]


            function generarTeoria(){
                console.log("Generando teoria");

                // creamos las líneas una por una, sacando elementos aleatorios de
                // cada una de nuestras listas, y sumandolos con algunos
                // artículos y conectores

                var linea1 = fuenteseg[randomInt(0, fuenteseg.length - 1)] + " me " + verbodeclarativo[randomInt(0, verbodeclarativo.length - 1)] + " que";

                var linea2 =  heroe[randomInt(0, heroe.length - 1)]+ " " + accionheroica[randomInt(0, accionheroica.length - 1 )] + ":";

                var linea3 = "La " + pandemia[randomInt(0, pandemia.length - 1)] + " estaba preparada por " + simulacro[randomInt(0, simulacro.length - 1)] + " en " + mes[randomInt(0, mes.length - 1)] + " de " + anio[randomInt(0, anio.length - 1)] + " en " + ciudad[randomInt(0, ciudad.length - 1)] + ",";

                var linea4 = " que " + antagonista[randomInt(0, antagonista.length - 1 )] + " " + premeditacion[randomInt(0, premeditacion.length - 1 )];


                //sumamos las líneas, el "<br>" es un salto de linea,
                //es para dividir el haiku en 3 renglones separado

                var teoria = linea1 + "<br>" + linea2 + "<br>" + linea3 + "<br>" + linea4


                //injectamos el resultado en la division con id = haiku01-resultado

                document.getElementById("teoria").innerHTML = teoria;
            }

            // ESTA FUNCION GENERA NUMEROS ALEATORIOS SEGUN LOS PARAMETROS
            // ej: randomInt(0, 5);
            // bajo: numero entero, el resultado no sera menor a este numero
            // alto: numero entero, el resultado no sera mayor a este numero

            function randomInt(bajo, alto){
                var result = Math.floor((Math.random() * alto) + bajo);
                return result
            }
        </script>

    </body>
</html>

De esta forma, lo que se busca es recrear el mundo de las noticias falsas desde la literatura. Y es a partir de esta recreación que se busca fijar para el lector los parámetros imaginativos desde donde se generan las noticias falsas. Estos parámetros imaginativos serían las construcciones cognitivas de lo social de las que habla Pérez Hernáiz y, para ello, se construyen mundos alternativos que ponen en escena, siguiendo el plantemiento de Gualda, las creencias que se oponen sobre un determinado tema.


 Si los conspiradores están carentes de imaginación, se puede pedir una teoría de conspiración al generador. 


# Ironía final
Una invitación a ser parte del mundo. 

Snowden
Assange 
Ponen en tela de juicio la realidad 
Hay conspiraciones y miles de teorías de la conspiración
