{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "name": "Entrega parcial 1 CC6204-Pablo Lemus",
      "provenance": [],
      "collapsed_sections": [],
      "toc_visible": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    }
  },
  "cells": [
    {
      "cell_type": "code",
      "metadata": {
        "id": "Yx6v1wz59hjg",
        "colab_type": "code",
        "colab": {}
      },
      "source": [
        ""
      ],
      "execution_count": 0,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "8_JujZrk9iwe",
        "colab_type": "text"
      },
      "source": [
        "#Mantenimiento presctiptivo de antenas de telecomunicaciones\n",
        "\n",
        "##Entrega 1 proyecto aplicación CC6204 - Deep Learning, 2019\n",
        "\n",
        "### Pablo Lemus\n",
        "\n",
        "1.  Descripción del problema\n",
        "\n",
        "El servicio que ofrece una empresa de telecomunicaciones depende del funcionamiento de sus antenas de transmisión, por lo que se deben realizar sus mantenciones respectivas para asegurar la calidad del servicio.\n",
        "Sin embargo, para planificar un mejor uso de los recursos y disminuir los costos operacionales de realizar mantenciones (mover a los teams, repuestos necesarios, etc.) es que busco realizar un modelo de predicción de fallas de las antenas.\n",
        "\n",
        "El input del modelo correpsonden a mediciones de estatus de cada antena  (cerca de 130 variables) que se registran cada una hora.\n",
        "\n",
        "Dado que busco mejorar la forma de utilizar los recursos de mantención de las antenas, el output corresponde a la predicción de la probabilidad de que falle la antena al día siguiente con los datos obtenidos en el día hasta las 23:00 horas.\n",
        "\n",
        "2. Descripción detallada de la métrica \n",
        "\n",
        "Las medidas que se usarán en este caso para determinar la calidad de predicción de la red son el valor del AUC (curva ROC) y el valor del test KS.\n",
        "\n",
        "* Área bajo al Curva ROC o AUC:\n",
        "\n",
        "En la Teoría de detección de señales, una curva ROC (acrónimo de Receiver Operating Characteristic, o Característica Operativa del Receptor) es una representación gráfica de la sensibilidad frente a la especificidad para un sistema clasificador binario según se varía el umbral de discriminación. Otra interpretación de este gráfico es la representación de la razón o ratio de verdaderos positivos (en el eje y del gráfico) frente a la razón o ratio de falsos positivos (en el eje x del gráfico) también según se varía el umbral de discriminación.\n",
        "\n",
        "Cada resultado de predicción o instancia de la matriz de confusión representa un punto en el espacio ROC.\n",
        "\n",
        "A modo de guía para interpretar las curvas ROC se han establecido los siguientes intervalos para los valores de AUC:\n",
        "\n",
        "[0.5]: Es como lanzar una moneda.\n",
        "\n",
        "[0.5, 0.6): Test malo.\n",
        "\n",
        "[0.6, 0.75): Test regular.\n",
        "\n",
        "[0.75, 0.9): Test bueno.\n",
        "\n",
        "[0.9, 0.97): Test muy bueno.\n",
        "\n",
        "[0.97, 1): Test excelente.\n",
        "\n",
        "Utilizaré esta medida debido a que permite medir el riesgo de cada antena según su probabilidad de falla para cada día y tomar decisiones enfocadas en aquellas antenas más riesgosas. Además es la unidad de medida que actualmente utiliza la compañía para comparar los resultados de sus modelos predictivos.\n",
        "\n",
        "Actualmente, usan otro modelo de Machine Learning para realizar sus predicciones, pero este tiene un valor de 0,67, por lo que se busca obtener un valor AUC mayor al valor actual ya que significaría una mejora en su predicción.\n",
        "\n",
        "3. Descripción de los datos de entrenamiento\n",
        "\n",
        "Como ya indiqué anteriormente, los datos corresponden a registros de estatus de funcionamiento de un conjunto de antenas (con aproximadamente 130 variables) realizados por la compañía de telecomunicaciones. Son cerca de 24.000 registros, de los cuales aproximadamente el 2% corresponde a casos positivos (casos de falla).\n",
        "\n",
        "Lamentablemente por motivos de confidencialidad con la empresa, no puedo entregar más información al respecto de los datos obtenidos.\n",
        "\n",
        "4. Descripción inicial de una arquitectura de Deep Learning\n",
        "\n",
        "Dado que modelaré el problema en base a series de tiempo de los datos registrados, la literatura recomienda utilizar una arquitectura de Redes Neuronales Recurrentes. Y en particular pienso utilizar una red LTSM (Long Short Term Memory).\n",
        "\n",
        "![Diagrama de red LTSM](LTSM.JPG)\n",
        "\n",
        "\n",
        "\n",
        "\n",
        "5. Repositorio de código\n",
        "\n",
        "https://github.com/plemush/plemush"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "_12u9FIRUhJs",
        "colab_type": "code",
        "colab": {}
      },
      "source": [
        ""
      ],
      "execution_count": 0,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "FEYGGy-HSkn3",
        "colab_type": "code",
        "colab": {}
      },
      "source": [
        ""
      ],
      "execution_count": 0,
      "outputs": []
    }
  ]
}