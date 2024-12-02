# Aplicativo-Android
Roteiro prático para o desenvolvimento de um aplicativo Android nas linguagens Java ou Kotlin
Esse repositório é um guia de como criar seu primeiro Aplicativo Android, apresentando o ambiente de desenvolvimento e duas linguagens: Java e Kotlin.

O objetivo é que esse roteiro permita introduzir a apresentar os principais conceitos do desenvolvimento Mobile, servindo como uma possível porta de entrada pra os estudos desse ramo da Engenharia de Software.

## A arquitetura do Sistema Operacional Android

O Android é um sistema operacional projetado principalmente para dispositivos móveis, como smartphones e tablets. Ele é baseado em um kernel Linux modificado e foi otimizado para atender às necessidades de dispositivos com recursos limitados, como bateria, memória e potência de processamento. Ele é desenvolvido a partir de uma arquitetura modular, é estruturado em camadas que trabalham juntas para oferecer uma experiência fluida ao usuário, sendo elas:

- **Kernel Linux**: Gerencia hardware, segurança e drivers de dispositivos (CPU, memória, bateria, sensores, etc.).
- **Bibliotecas Nativas**: Proporcionam funcionalidades específicas, como gráficos (OpenGL), banco de dados (SQLite), e criptografia (SSL).
- **Android Runtime (ART)**: Executa os aplicativos Android, convertendo o código de alto nível (Java/Kotlin) para instruções compreendidas pelo hardware.
- **Framework de Aplicação**: Oferece APIs para que os desenvolvedores criem aplicativos, fornecendo acesso ao hardware e funcionalidades do sistema.
- **Interface de Usuário e Aplicativos**: A camada que o usuário interage diretamente, composta pela interface gráfica e pelos aplicativos.

## Como Funciona uma Aplicação Android

Uma aplicação Android é composta por uma série de componentes que trabalham juntos para oferecer funcionalidade e interatividade ao usuário. Esses componentes estão organizados em uma arquitetura que facilita o desenvolvimento modular e a reutilização de código. Vamos detalhar os principais componentes:

# 1. Principais Componentes de uma Aplicação Android

### a) Activities (Atividades)
- **O que é uma Activity?**  
  É o ponto de entrada para a interação do usuário com um aplicativo. Representa uma única tela com uma interface visual (UI).  
  Exemplo: No WhatsApp, a tela de chat é uma Activity, e a tela de configurações é outra Activity.

- **Funções principais da Activity**:  
  - Gerenciar o ciclo de vida da tela.  
  - Exibir elementos visuais (Views) para o usuário interagir.  
  - Responder a eventos de toque, clique e navegação.

- **Ciclo de vida de uma Activity**:  
  O ciclo de vida gerencia os estados de uma Activity, garantindo que o sistema otimize os recursos. Ele é controlado por callbacks, como:
  1. `onCreate()`: Chamado quando a Activity é criada pela primeira vez. Aqui configuramos a interface (UI) da tela.
  2. `onStart()`: Chamado quando a Activity se torna visível.
  3. `onResume()`: Chamado quando a Activity está em primeiro plano e interativa.
  4. `onPause()`: Chamado quando outra Activity fica parcialmente visível (ex.: um diálogo).
  5. `onStop()`: Chamado quando a Activity não está mais visível.
  6. `onDestroy()`: Chamado quando a Activity é finalizada pelo sistema ou pelo usuário.

---

### b) Views e ViewGroups
- **O que são Views?**  
  Uma View é o bloco básico da interface do usuário. Pode ser um botão, texto, imagem, campo de entrada, etc.
  - Exemplos de Views:
    - `TextView`: Exibe texto.
    - `Button`: Botão clicável.
    - `ImageView`: Exibe imagens.
    - `EditText`: Campo de entrada de texto.

- **O que são ViewGroups?**  
  Um ViewGroup é um contêiner que organiza e agrupa outras Views (ou ViewGroups). Ele define como os elementos da interface serão dispostos na tela.
  - Exemplos de ViewGroups:
    - `LinearLayout`: Organiza as Views em linha ou coluna.
    - `RelativeLayout`: Posiciona Views em relação a outras Views ou ao contêiner.
    - `ConstraintLayout`: Um layout mais flexível que permite posicionar elementos com base em restrições.

- **Interação entre Views e Activity**:  
  - As Views são instanciadas e controladas dentro da Activity.  
  - Cada View possui um **ID**, permitindo que o desenvolvedor interaja com ela no código.  
  Exemplo:
  ```java
  Button meuBotao = findViewById(R.id.botao);
  meuBotao.setOnClickListener(new View.OnClickListener() {
      @Override
      public void onClick(View v) {
          // Lógica para o clique do botão
      }
  });
### c) Fragments
- **O que é um Fragment?**  
  É uma parte reutilizável de interface de usuário que pode ser incorporada dentro de uma Activity.
  - Permite criar interfaces dinâmicas para telas maiores (ex.: tablets).
  - Pode ser adicionado, substituído ou removido de uma Activity em tempo de execução.

- **Por que usar Fragments?**  
  - Melhor organização e reutilização do código.  
  - Facilita a adaptação de layouts para diferentes tamanhos de tela.

---

### d) Intents
- **O que é um Intent?**  
  É um objeto usado para comunicação entre componentes da aplicação (ou até entre diferentes aplicativos). Pode ser usado para:  
  - Abrir outra Activity.  
  - Iniciar um Service.  
  - Compartilhar dados com outro app.

- **Tipos de Intents**:  
  - **Explícito**: Indica diretamente qual componente será acionado.  
    Exemplo: Abrir uma Activity específica.  
    ```java
    Intent intent = new Intent(this, SegundaActivity.class);
    startActivity(intent);
    ```  
  - **Implícito**: Delega a ação a um componente que possa lidar com a tarefa.  
    Exemplo: Compartilhar texto.  
    ```java
    Intent intent = new Intent(Intent.ACTION_SEND);
    intent.setType("text/plain");
    intent.putExtra(Intent.EXTRA_TEXT, "Olá, mundo!");
    startActivity(intent);
    ```



  
