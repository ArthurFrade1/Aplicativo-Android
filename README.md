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

## 1. Principais Componentes de uma Aplicação Android

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

---
  
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

# Ambiente de Desenvolvimento para Aplicativos Android

Agora que já viu os principais componentes de uma aplicação Android esta na hora de conhecer o mais popular e completo ambiente de desenvolvimento, o Android Studio

## 1. Ferramentas Necessárias
Antes de começar, você precisará instalar as ferramentas básicas:

- **Android Studio**:  
  É o IDE oficial para desenvolvimento Android, baseado no IntelliJ IDEA. Ele oferece:
  - Editor de código para Kotlin e Java.
  - Designer de interface gráfica.
  - Ferramentas de depuração.
  - Integração com o Gradle (sistema de build).

- **JDK (Java Development Kit)**:  
  Necessário para compilar e executar código Java/Kotlin. O Android Studio já inclui o JDK.

- **Android SDK (Software Development Kit)**:  
  Inclui ferramentas para desenvolvimento Android, como:
  - Bibliotecas do Android.
  - Ferramentas para criar APKs (pacotes do app).
  - ADB (Android Debug Bridge) para comunicação com dispositivos.

- **Emulador Android ou Dispositivo Físico**:  
  O emulador simula um dispositivo Android no seu computador, já vem incluso no Android Studio. Você pode usar também um celular real para testes.

---

## 2. Instalação do Android Studio
**Passo a passo**:

1. **Baixe o Android Studio** no [site oficial](https://developer.android.com/studio).
2. Durante a instalação:
   - Escolha as configurações padrão.
   - Certifique-se de que o Android SDK, emulador e JDK estão selecionados.
3. Abra o Android Studio e faça o download das ferramentas SDK recomendadas.

---

## 3. Criando Seu Primeiro Projeto
**Passo a passo para criar um projeto:**

1. Abra o Android Studio e clique em **"New Project"**.
2. Escolha um template inicial, como **No Activity**.
3. Configure os detalhes:
   - **Nome do Aplicativo**: Por exemplo, `MeuApp`.
   - **Nome do Pacote**: Ex.: `com.exemplo.meuapp`.
   - **Linguagem**: Escolha entre **Kotlin** ou **Java**.
   - **Minimum SDK**: Escolha o nível mínimo de API que o app suportará (recomenda-se Android 6.0 ou superior).

4. Clique em **Finish**. O Android Studio criará automaticamente a estrutura do projeto.

<div align="center">
    <img src="https://github.com/user-attachments/assets/d9919ec9-9fe4-43c2-9377-e0cc8a6f9dda" alt="image" width="650px">
</div>

## Estrutura de um Projeto Android

Ao criar um projeto Android, a estrutura do diretório pode parecer complexa para iniciantes. No entanto, cada pasta e arquivo desempenha um papel importante no desenvolvimento de aplicativos Android. Aqui está uma explicação detalhada das principais pastas e seus propósitos:

---

### **1. Pasta `app`**
A pasta mais importante do projeto. Contém todo o código-fonte do aplicativo, recursos e arquivos de configuração. Dentro dela, temos:

#### **a) `manifests/`**
- Contém o arquivo **`AndroidManifest.xml`**.
- **Função**:
  - Define informações essenciais sobre o aplicativo, como:
    - Nome do pacote do app.
    - Permissões (como acesso à internet ou localização).
    - Declaração de componentes (Activities, Services, Broadcast Receivers, etc.).
  - Ponto de entrada do app (`<intent-filter>`).

#### **b) `java/`**
- Contém o código-fonte Java ou Kotlin do aplicativo.
- **Função**:
  - Inclui o código de:
    - **Activities**: Gerenciam telas do app.
    - **ViewModels** e **Controladores** (opcional): Parte lógica do app.
    - **Serviços**: Processos em segundo plano.

#### **c) `res/` (Resources)**
- Contém recursos usados no aplicativo, como layouts, imagens e strings.
- Subpastas principais:
  - **`layout/`**: Arquivos XML que definem a interface gráfica do aplicativo.
  - **`drawable/`**: Imagens e gráficos (como PNG, JPG, etc.).
  - **`values/`**: Arquivos XML com valores reutilizáveis:
    - **`strings.xml`**: Textos (como rótulos de botões).
    - **`colors.xml`**: Definições de cores.
    - **`styles.xml`**: Temas e estilos do app.

#### **d) `assets/` (opcional)**
- Contém arquivos brutos, como fontes personalizadas, arquivos JSON, etc.
- **Função**: Permite acessar diretamente os arquivos via código.

---

### **2. Pasta `build/`**
- Diretório gerado automaticamente durante a compilação.
- Contém os arquivos necessários para executar o aplicativo no emulador ou dispositivo real.
- **Função**: Não é preciso modificar ou interagir diretamente com essa pasta.

---

### **3. Arquivo `build.gradle` (nível do módulo)**
- Configurações específicas para o módulo `app`.
- Exemplos de configurações:
  - Dependências do aplicativo (como bibliotecas externas).
  - Versão mínima e máxima do SDK.

---

### **4. Pasta `gradle/`**
- Contém arquivos relacionados ao sistema de automação de compilação do Gradle.
- **Função**: Gerencia dependências e processos de build.

---

### **5. Pasta `.idea/`**
- Contém arquivos de configuração do Android Studio.
- **Função**: Configurações do ambiente de desenvolvimento (como atalhos e organização do projeto).
- **Obs.:** Não afeta o funcionamento do aplicativo.

---

### **6. Arquivo `settings.gradle`**
- Configura o ambiente de construção do projeto como um todo.
- **Função**:
  - Indica quais módulos (ex.: `app`) pertencem ao projeto.

---

### **Resumo Visual da Estrutura**

```plaintext
MyApplication/
│
├── app/
│   ├── manifests/
│   │   └── AndroidManifest.xml
│   ├── java/
│   │   └── com.example.myapp/
│   │       ├── MainActivity.java (ou .kt)
│   │       └── OutrosArquivos.java
│   ├── res/
│   │   ├── drawable/
│   │   │   └── ic_launcher.png
│   │   ├── layout/
│   │   │   └── activity_main.xml
│   │   ├── values/
│   │   │   ├── strings.xml
│   │   │   ├── colors.xml
│   │   │   └── styles.xml
│   │   └── assets/
│   │       └── dados.json
│
├── build/
│   └── (Arquivos de build gerados automaticamente)
│
├── gradle/
│   └── wrapper/
│
├── build.gradle (nível do projeto)
├── settings.gradle
└── .idea/
    └── (Configurações do Android Studio)

```

Essa estrutura é padrão em todos os projetos Android criados no Android Studio, seja com **Java** ou **Kotlin**. Para iniciantes, as pastas mais importantes são `manifests`, `java` e `res`.




  
