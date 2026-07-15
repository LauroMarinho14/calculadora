# calculadora
projeto de uma calculadora, com funções básicas com fullstack.
<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Calculadora</title>
        <style>
            *{
                margin: 0;
                padding: 0;
                box-sizing: border-box;
            }
            .fundo{
                background-image: linear-gradient(45deg, blue, black);
                width: 100%;
                height: 100vh;
                font-family: Arial, Helvetica, sans-serif;
                color: #fff;
                text-align: center;
            }
            .calculadora{
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                background-color: rgba(0, 0, 0, 0.8);
                padding: 15px;
                border-radius: 15px;
                box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
            }
            .botao{
                width: 50px;
                height: 50px;
                font-size: 25px;
                margin: 3px;
                border-radius: 50%;
                border: none;
                background-color: rgb(31, 30, 30);
                color: white;
                cursor: pointer;
            }
            .botao:hover{
                background-color: black;
            }
            #resultado{
                background-color:white;
                width:207px;
                height: 30px;
                margin: 5px;
                font-size: 25px;
                color: black;
                text-align: right;
                padding:5px;
            }
        </style>

    </head>
    <body>
        <div class="fundo">
            <h1>Lauro</h1>
        <div class="calculadora">
            <h1>Calculadora</h1>
            <p id="resultado"></p>
            <table>
                <tr>
                    <td><button class="botao"onclick=clean()>C</button></td>
                    <td><button class="botao" onclick="back()"><</button></td>
                    <td><button class="botao" onclick="insert('/')">/</button></td>
                    <td><button class="botao" onclick="insert('*')">*</button></td>
                </tr>

                <tr>
                    <td><button class="botao" onclick="insert('7')">7</button></td>
                    <td><button class="botao" onclick="insert('8')">8</button></td>
                    <td><button class="botao" onclick="insert('9')">9</button></td>
                    <td><button class="botao" onclick="insert('-')">-</button></td>
                </tr>

                <tr>
                    <td><button class="botao" onclick="insert('4')">4</button></td>
                    <td><button class="botao" onclick="insert('5')">5</button></td>
                    <td><button class="botao" onclick="insert('6')">6</button></td>
                    <td><button class="botao" onclick="insert('+')">+</button></td>
                </tr>

                <tr>
                    <td><button class="botao" onclick="insert('1')">1</button></td>
                    <td><button class="botao" onclick="insert('2')">2</button></td>
                    <td><button class="botao" onclick="insert('3')">3</button></td>
                    <td rowspan="2"><button class="botao" style="height: 106px;" onclick="calcular()">=</button></td>
                </tr>

                <tr>
                    <td colspan="2"><button class="botao" style="width: 106px;" onclick="insert('0')">0</button></td>
                    <td><button class="botao">,</button></td>
                </tr>
            </table>
            
        </div>
        </div>
        <script>
            function insert(num)
            {
                var numero = document.getElementById('resultado').innerHTML;
                document.getElementById('resultado').innerHTML = numero + num;

            }
            function clean()
            {
                document.getElementById('resultado').innerHTML = "";
            }
            function back()
            {
                var resultado = document.getElementById('resultado').innerHTML;
                document.getElementById('resultado').innerHTML = resultado.substring(0, resultado.length -1);
            }
            function calcular()
            {
                var resultado = document.getElementById('resultado').innerHTML;
                if(resultado)
                {
                    document.getElementById('resultado').innerHTML = eval(resultado);
                }
            }
           
        </script>
    </body>
</html>
