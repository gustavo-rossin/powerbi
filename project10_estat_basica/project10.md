# Projeto 10

Este projeto teve o foco em relembrar as noções de estatística básica, como ```média```, ```mediana```, ```moda```, ```desvio padrão```, ```variância``` e ```coeficiente de variância``` dentro do PowerBI.

Alguns pontos do ```Exercício 1```:

1. ```Moda```: dentro do PowerBI, não tem uma fórmula pronta, portanto foi ensinado como calcular via DAX. Como calcular moda abaixo:
~~~javascript
ModaAltura = 
VAR TabelaFrequencia =
    SUMMARIZE(
        dados_pacientes,
        dados_pacientes[altura(cm)],
        "Frequencia", COUNT(dados_pacientes[altura(cm)])
    )
VAR MaiorFrequencia =
    MAXX(
        TabelaFrequencia,
        [Frequencia]
    )
RETURN
    CONCATENATEX(
        FILTER(TabelaFrequencia, [Frequencia] = MaiorFrequencia),
        dados_pacientes[altura(cm)],
        ", "
    )
~~~

2.  ```Variância```: A variância é uma medida que indica o quanto os valores em um conjunto de dados variam  em  torno  da  média.  Uma  variância  maior  indica  uma  maior  dispersão  dos  valores, enquanto uma variância menor sugere que os valores estão mais próximos da média.

3. ```Desvio Padrão```: O desvio padrão é a raiz quadrada da variância e também mede a dispersão dos valores em um conjunto de dados. **Ele é expresso na mesma unidade de medida dos valores originais, o que o torna mais fácil de interpretar em comparação com a variância.** Um desvio padrão maior indica maior variabilidade dos valores, enquanto um desvio padrão menor sugere que os valores estão mais próximos da média. 

4. ```Coeficiente de Variância```: Um CV menor indica que os dados são menos dispersos em relação à média, enquanto um CV maior indica que os dados são mais dispersos. CV = (Desvio Padrão / Média) × 100



## Screenshots

Parte 1: jeitos de calcular a moda.
![Relatório 10 - basic statistics](https://raw.githubusercontent.com/gustavo-rossin/powerbi/main/project10_estat_basica/print_exercicio1.PNG)

Parte 2: Usando o CV.
![Relatório 10 - basic statistics](https://raw.githubusercontent.com/gustavo-rossin/powerbi/main/project10_estat_basica/print_exercicio2.PNG)
