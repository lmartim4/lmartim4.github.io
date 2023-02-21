# Como usar o Simulador UUV_Sim para para o Mandi2

<aside>
📖 Lendo esse arquivo você vai entender como isntalar e utilizar o simulador UUV_Sim para simular o Mandi2 em um computador com Windows 11, através do WSL rodando um  Ubuntu Focal Fossa 20.04 LTS.

</aside>

---

<aside>
📖 1. O [simulador oficial](https://uuvsimulator.github.io/) tem suporte para rodar no máximo até o Ubuntu 18.04 LTS. Entretanto, essa versão do Ubuntu é bastante antiga e a versão do ROS compatível com esse Ubuntu foi descontinuada.

</aside>

<aside>
📖 3. O WSL é o Windows Subsystem for Linux. Com ele é possível rodar uma versão do Linux como se fosse uma máquina virtual no seu Windows 11. Contando com interface gráfica e a praticidade de não precisar de um Dual boot ou um computador com essa versão tão antiga do Ubuntu.

</aside>

<aside>
📖 5. Uma solução para este problema seria utilizar o Ubuntu 20.04. Este conta com o ROS Noetic (que também conta com suporte oficial)

</aside>

<aside>
📖 2. Apesar disso, caso fossemos utilizar essa versão do Linux seria necessário uma máquina com esse Ubuntu mais antigo ou um Dual Boot (que é bem desagradavél). Para contornar esse problema, podemos utilizar o WSL, mas outros surgem pela frente.

</aside>

<aside>
📖 4. Entretando, mesmo com um WSL, a simulação no Gazebo rodaria totalmente sob o processador, pois essa versão do Ubuntu não conta com suporte a aceleração gráfica através do WSL.

</aside>

<aside>
📖 6. Uma [versão “modificada” do UUV_Sim](https://github.com/lmartim4/uuv_simulator_20.04) permite que ele seja compilado para o ROS Noetic. Isso permite o uso do Ubuntu 20.04, consquentemente permite o uso do WSL, ou seja, pode-se usar o Windows 11 para rodar o simulador de forma bastante eficiente e prática!

</aside>

---

## Instalando o WSL2 no Windows 10/11

<aside>
💡 Essa parte é necessária caso queira-se utilzar o WSL em vez do Ubuntu, conforme explicado acima!

</aside>

[Instalar o WSL](https://learn.microsoft.com/pt-br/windows/wsl/install)

<aside>
📖 Aqui está o tutorial oficial. O Intuito desta parte do tutorial é mostrar que pode-se utilizar o Windows para executar o simulador. Mas como tudo é feito no linux, essa parte é dispensável caso queira executar no Ubuntu de forma convencional.

</aside>

---

## Instalando o ROS Noetic

<aside>
📖 Para instalar o ROS Noetic existem duas opções. Pode-se instalá-lo executando comandos linha a linha ou com um script que executará os mesmos comandos de forma automatizada.

</aside>

<aside>
💡 Instale a versão completa `(ros-noetic-desktop-full)` opção 1 no caso da instalação automatica!

</aside>

[ROS/Installation/TwoLineInstall - ROS Wiki](http://wiki.ros.org/ROS/Installation/TwoLineInstall/)

Forma de instalar automaticamante. **(recomendada)**

[noetic/Installation/Ubuntu - ROS Wiki](http://wiki.ros.org/noetic/Installation/Ubuntu)

Instruções linha a linha **(prefiro a da esquerda)**

<aside>
💡 Recomanda-se a instalação automatica.

</aside>

---

## Instalando as dependencias

<aside>
📖 Com os pacotes abaixo, será possível compilar o UUV_Sim atualizado. Para instalá-los basta executar a linha de comando abaixo

</aside>

```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

---

## Instalando o simulador

<aside>
💡 O Simulador é separado em 3 sub módulos.

</aside>

- 1 - UUV Simulator 20.04
    - Esse sub módulo é encontrado em  https://github.com/lmartim4/UUV_Sim_20.04
        - Ele consiste na versão atualizada do https://github.com/uuvsimulator/uuv_simulator para fucionar no ROS Noetic
- 2 - Mandi2
    - Esse sub módulo é encontrado em https://github.com/lmartim4/Mandi2
        - Ele consiste nos arquivos de configuração capazes de descrever o Mandi2 para o simulador.
- **3 - Simulador Completo**
    - Este é, na verdade, a união dos submódulos acima necessários para executar a simulação. Ele pode ser encontrado em https://github.com/lmartim4/Mandi2-Simulador-Completo.
    - Nele está contido os dois sub módulos acima no arquivo ‘[.gitmodules](https://github.com/lmartim4/Mandi2-Simulador-Completo/blob/main/.gitmodules)’.
    - Seguindo o turorial do [README.md](https://github.com/lmartim4/Mandi2-Simulador-Completo/blob/main/README.md) é possivel sair do zero e iniciar o simulador com poucos comandos (desde que já tenha instalado o ROS Noetic e suas dependencias)

<aside>
✅ Caso tudo tenha dado certo, executar o seguinte comando executara uma simulção teste no gazebo `roslaunch uuv_gazebo_worlds ocean_waves.launch`

</aside>