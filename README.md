<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OBJ MATH</title>
</head>
<body>
    <h1>Operações com Math em JavaScript</h1>

    <h2>Calcular a área de um círculo</h2>
        <label for="raio">Digite o raio:</label>
        <input type="number" id="raio" step="any">
        <button onclick="calcularArea()">Calcular Área</button>
        <p id="resultadoArea"></p>

    <h2>Encontrar o valor máximo</h2>
        <label for="numeros">Digite uma lista de números separados por vírgula:</label>
        <input type="text" id="numeros" placeholder="Ex: 10, 25, 37, 49, 55">
        <button onclick="encontrarMaximo()">Encontrar Máximo</button>
        <p id="resultadoMaximo"></p>

    <script>
        function calcularArea() {
            const raio = parseFloat(document.getElementById("raio").value);
            if (!isNaN(raio) && raio > 0) {
                const area = Math.PI * Math.pow(raio, 2);
                document.getElementById("resultadoArea").textContent = `A área do círculo com raio ${raio} é: ${area.toFixed(2)}`;
            } else {
                document.getElementById("resultadoArea").textContent = "Por favor, insira um valor válido para o raio.";
            }
        }
        function encontrarMaximo() {
            const numerosInput = document.getElementById("numeros").value;
            const numerosArray = numerosInput.split(',').map(num => parseFloat(num.trim()));

            if (numerosArray.every(num => !isNaN(num))) {
                const maximo = Math.max(...numerosArray);
                document.getElementById("resultadoMaximo").textContent = `O valor máximo na lista [${numerosArray.join(", ")}] é: ${maximo}`;
            } else {
                document.getElementById("resultadoMaximo").textContent = "Por favor, insira uma lista válida de números.";
            }
        }
    </script>
</body>
</html>
