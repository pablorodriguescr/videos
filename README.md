// amigos me ajudem ae..

//esse codigo gera um nodelist dos videos selecionados atraves do checkbox com o querySelectAll. preciso fazer o seguinte, antes do //primeiro video preciso colocar um texto concatenado com o id do primeiro video dizendo que e o usuario escolheu o determinado video e //explicando como sera o video, depois do texto reproduzir o video o final e antes do segundo video tambem preciso apresentar um texto //concatenado com o segundo video. e preciso fazer isso com todos os videos selecionados no checkbox..
// aceito sugestão de como fazer isso da melhor maneira, outra linguagem outro estilo. me ajudem..



<html>
    <head>
    <meta charset="utf8">
    <meta content-type="text/html">

    <title>Farmacia Principium</title>
    <link rel="stylesheet" type="text/css" href="stylepablok.css">


    </head>
    <body>
         
<div id ="demotexto">
                   <b> <p id="demo" style="font-size: 25px; color: black; margin-top: 1%" ></p></b>
</div>


<div id ="teto2"style="display: none" >




</div>

    <div id="videoDiv" style="display: none">


       
            <video id="video" width="720" height="480" autoplay controls>
                <source id="source" src="" type="video/mp4">
            </video>

     </div> 
        
        
      

    <div calss="row" style ="margin-top:370px;">

         <input type="checkbox" id="capsula" name="Pacote" value="./videos/video1.mp4">
        <label for="pacotei">CAPSULA</label>
        <br>
        <input type="checkbox" id="creme" name="Pacote" value="./videos/video2.mp4">
        <label for="pacoteii">CREME</label>
        <br>
        <input type="checkbox" id="sache" name="Pacote" value="./videos/video3.mp4">
        <label for="pacoteiii">SACHE</label>

        <br><input type="checkbox" id="SHAMPOO" name="Pacote" value="./videos/video4.mp4">
        <label for="pacoteiiii">SHAMPOO</label>

        <br><input type="checkbox" id="FLORAL" name="Pacote" value="./videos/video4.mp4">
        <label for="pacoteiiiii">FLORAL</label>

        <br><input type="checkbox" id="HOMEOPATIA" name="Pacote" value="./videos/video5.mp4">
        <label for="pacoteiiiiii">HOMEOPATIA</label>
    </div>
        
        <div class="nomeC">
           
            <input id ="cliente"type="text"  name="salvar" value="" style="display: none" >
        </div>

        <h1>
            

        </h1>
        <div class = "videoS">
         <button onClick="executa()"> EXECUTA DEMOSTRAÇÃO</button> 
        </div>


    

        <script type="text/javascript">
            function show(){   
                //para selecionar uma ou mais checkboxes, use querySelectAll
                //será retornado um nodelist, similar a um array, com todos
                //os cehckbox que foram selecionados pelo usuario, veja com //console.log(pacotes);
                //pequena mudanca no nome da variavel
                let pacotes = document.querySelectorAll('[name="Pacote"]:checked')
                console.log(pacotes);
                           
                let source = document.querySelector('#source');

                document.querySelector('#videoDiv').style.display = 'block'
        
            //agora você precisa carregar o primeiro video (se houver) 
                //a partir do nodelist pacotes
                
            if(pacotes.length > 0){
                    let pacote_indice = 0;
                    let video = document.querySelector('#video');
                    //seta o atributo src do primeiro video 
                    //primeiro indice do nodelist, obtido a partir do atributo value
                    source.setAttribute('src', pacotes[pacote_indice].value);              
                video.load()

                    //nesse ponto você deve usar o evento onended no elemento #video
                //que é disparado quando o video termina de rodar
                    video.addEventListener('ended', function(){
                        pacote_indice++;
                        //tocara até o ultimo indice do array pacotes
                        if(pacote_indice < pacotes.length){
                            source.setAttribute('src', pacotes[pacote_indice].value);              
                        video.load();                        
                        }
                    });
                }
            }
      
              var executa = function(){

                
                show();
                nomepopup();
                botao.onClick = executa;
              }


                  function nomepopup() {
        var txt;
        var person = prompt("Por favor digite o nome do cliente");
        if (person == null || person == "") {
            txt = "você cancelou.";
        } else {
            txt = "Ola " + person +" e um prazer ter você conosco, que bom que voce ira fazer um medicamento conosco.<br/>vou lhe amostra neste breve video como e feito de forma individualizada o seu medicamento!<br/><br/>A VIDA E A NOSSA MAIOR INSPIRAÇÃO ";
        }
        document.getElementById("demo").innerHTML = txt;
    }



        
    



        </script>
    
    </body>
    </html>




    
