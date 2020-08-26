## Filtro FIR
Projeto para a VF
#Descrição do Projeto

O objetivo desse projeto é utilizar o microcontrolador STM32F746 para
receber uma amostra de aúdio, para então filtra-lo e devolver a amostra resultante.
Para realizar a pré-filtragem do sinal de entrada ruidoso, quatro elementos filtrantes do tipo resposta ao impulso finita (Finite Impulse Response - FIR) serão implementados, com as seguintes características:

* Filtro 0: passa-alta (> 12kHz);
* Filtro 1: passa-baixa para AM (<6kHz);
* Filtro 2: passa-baixa para SSB (<3kHz);
* Filtro 3: passa-banda para CW (500 Hz).

Será implementado também um Filtro Adaptativo (Least Mean Square - LMS). Na filtragem convencional do tipo resposta ao impulso finita (FIR) ou do tipo resposta ao impulso infinita (IIR), geralmente assume-se que os parâmetros do processo estocástico de entrada são conhecidos, tais parâmetros determinam as características do sinal de entrada. No entanto, em nosso problema prático, alguns parâmetros de entrada podem mudar, ou ainda, o sistema pode não conhecer exatamente o comportamento destes parâmetros. Desse modo, é altamente desejável um filtro que possua o atributo de auto-aprendizado, de maneira que este possa ajustar-se automaticamente de acordo com cada situação. O algoritmo clássico LMS utilizado constitui uma das técnicas mais conhecidas para a implementação de um filtro adaptativo. O LMS utiliza um algoritmo de gradiente estocástico para adaptar a carga de um filtro. Esta adaptação consiste no ajuste contínuo (e adaptativo) dos valores dos coeficientes do filtro, tendo como métrica a minimização do erro no sentido da média dos quadrados.

Além disso, será utilizada a funcionalidade da FFT (Direta e Inversa), pois a partir do valor de módulo (magnitude) do sinal pode-se aplicar a técnica de subtração espectral de magnitude, a fim de restaurar o espectro de magnitude do sinal em presença do ruído aditivo. Em seguida, a informação de fase contaminada com o ruído é novamente combinada ao sinal, e então passada para o domínio do tempo, via FFT inversa. Este processo está representado no diagrama de blocos do redutor de ruído digital (Digital Noise Reduction-DNR)



#Fluxograma

#Diagrama de blocos

