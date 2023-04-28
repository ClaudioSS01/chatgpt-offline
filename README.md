# chatgpt-offline
<h1>Execute um LLM semelhante ao ChatGPT localmente sem Internet (privado e seguro)</h1>
<br>
Atualmente, existem vários players de IA no mercado, incluindo ChatGPT , Google Bard , Bing AI Chat e muitos mais. No entanto, todos eles exigem que você tenha uma conexão com a Internet para interagir com a IA. E se você quiser instalar um LLM (Large Language Model) semelhante em seu computador e usá-lo localmente? Um chatbot AI que você pode usar de forma privada e sem conectividade com a Internet. Bem, com o novo modelo Alpaca lançado pela Stanford, você pode chegar perto dessa realidade. Sim, você pode executar um modelo de linguagem semelhante ao ChatGPT no seu PC offline. Então, falando nisso, vamos aprender como usar um LLM localmente sem a internet.
<br>
<h1>O que é Alpaca e LLaMA?</h1>
<br>
Alpaca é um pequeno modelo de linguagem AI desenvolvido por um grupo de cientistas da computação na Universidade de Stanford. O que há de único na Alpaca é que ela é pequena e econômica . Com apenas 7 bilhões de parâmetros, o Alpaca é tão bom quanto o modelo text-davinci-003 da OpenAI. E você pode executá-lo em seu computador local sem precisar de uma conexão com a Internet. Isso é muito legal,
<br>
Mas como foi treinado? Surpreendentemente, o Alpaca está ajustado no LLaMa , o grande modelo de linguagem do Meta que recentemente vazou online. E para treinar esse modelo de linguagem, os cientistas usaram o modelo “text-davinci-003” da OpenAI para gerar 52K de dados de autoinstrução de alta qualidade. Com esse conjunto de dados, eles ajustaram o modelo LLaMA usando a estrutura de treinamento do HuggingFace e lançaram o Alpaca 7B . Você também pode usar o modelo LLaMA da Meta, mas em meus testes, o Alpaca LLM de Stanford teve um desempenho muito melhor e também é bastante rápido.
<br>
<h1>Que tipo de hardware você precisa para executar o Alpaca?</h1>
<br>
Você pode usar o Alpaca 7B em qualquer máquina decente. Instalei o Alpaca 7B no meu PC básico e funcionou muito bem. Para se ter uma ideia, meu PC é alimentado por um processador Intel i3 de 10ª geração com 256 GB de SSD e 8 GB de RAM. Para GPU, estou usando a GPU GeForce GT 730 de nível básico da Nvidia com 2 GB de VRAM.
<br>
Mesmo sem uma GPU dedicada , você pode executar o Alpaca localmente. No entanto, o tempo de resposta será lento. Além disso, existem usuários que conseguiram executar o Alpaca mesmo em um computador minúsculo como o Raspberry Pi 4 . Portanto, você pode inferir que o modelo de linguagem Alpaca também pode ser executado muito bem em computadores básicos.
<br>
<h1>Configurar o ambiente de software para executar Alpaca e LLaMA</h1>
<br>
<h3>Windows</h3>
<br>No Windows, você precisa instalar Python, Node.js e C++ para começar a usar um grande modelo de linguagem offline em seu computador. Aqui está como fazer isso.

<b>1.</b> Primeiro, baixe o Python 3.10 (ou inferior) aqui . Role para baixo e clique em “Instalador do Windows (64 bits)” para baixar o arquivo de instalação.
<br>
<b>2.</b>  Inicie o arquivo de configuração e ative a caixa de seleção ao lado de “ Add Python.exe to PATH ”. Agora, instale o Python com todas as configurações padrão.
<br>
<b>3.</b> Depois disso, instale o Node.js versão 18.0 (ou superior) daqui . Mantenha tudo padrão durante a instalação do programa.
<br>
<b>4.</b> Finalmente, baixe a edição “Community” do Visual Studio neste <a href="https://visualstudio.microsoft.com/pt-br/downloads/">link</a> gratuitamente.
<br>
<b>5.</b>  Inicie o arquivo de instalação do Visual Studio 2022 e, inicialmente, ele baixará alguns arquivos. Depois disso, uma nova janela será aberta. Aqui, certifique-se de que “ desenvolvimento de desktop com C++ ” esteja habilitado.
<br>
<b>6.</b>  Por fim, clique em “ Instalar ” e aguarde até que a instalação seja concluída.
<br>
<b>7.</b>  Recomendo reiniciar o computador assim que tudo estiver instalado. Em seguida, abra o “ Prompt de Comando ” e execute os comandos abaixo para verificar se o Python e o Node.js foram instalados com sucesso. Ambos devem retornar o número da versão. Agora você está pronto para ir.
<br>
<pre><code>
python --version
node --version
</code>
</pre>
<br>
<h1>Linux and ChromeOS</h1>
<br>
<b>1.</b> Open the Terminal and run the below command to check the Python version. If it’s Python 3.10 or below, you are all set.
<br>
<pre><code>
python3 --version
</code></pre>
<br>
<b>2.</b> In case you have a higher version, you can use the below commands to install Python 3.10 on Linux and ChromeOS.
<br>
<pre><code>
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
sudo apt-get install python3.10
</code>
</pre>
<br>
<b>3.</b> After Python, install Node.js by running the below command.
<br>
<pre><code>
sudo apt install nodejs
</code>
</pre>
<br>
<b>4.</b> After the installation, run the below command to check the Node.js version. It should be 18.0 or higher.
<br>
<pre><code>
node --version
</code></pre>
<br>
<h1>
Install Alpaca and LLaMA Models On Your Computer
</h1>
<br>
Once you have set up Python and Node.js, it’s time to install and run a ChatGPT-like LLM on your PC. Make sure the Terminal detects both python and node commands before you proceed.
<br>
<b>1.</b> Open the Terminal (in my case, Command Prompt) and run the below command to install the Alpaca 7B LLM model (around 4.2GB disk space required). If you want to install the Alpaca 13B model, replace 7B with 13B. The larger model needs 8.1GB of space.
<br>
<pre>
<code>
npx dalai alpaca install 7B
</code>
</pre>
<br>
<b>2.</b> Now, type “y” and hit Enter. This will start installing the Alpaca 7B model. The whole process will take 20 to 30 minutes, depending on your internet connectivity and model size.
<br>
<b>3.</b> After the installation is complete, you will see a screen like this.
<br>
<b>4.</b> You can choose to install LLaMA models as well or move to the next step to test the Alpaca model instantly. Remember, LLaMA is much larger in size. Its 7B model takes up to 31GB of space. To install it, run the below command. You can replace 7B with 13B, 30B, and 65B. The largest model takes up to 432GB of space.
<br>
<pre><code>
npx dalai llama install 7B
</code>
</pre>
<br>
<b>5.</b> Finally, run the below command, and it will start the webserver instantly.
<br>
<pre>
<code>
npx dalai serve
</code>
</pre>
<br>
<b>6.</b> Use a web browser on your PC and open the below address. This will take you to the web UI where you can test Alpaca and LLaMA models locally and without the internet.
<br>
 http://localhost:3000
<br>


















