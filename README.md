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

## Principais Componentes de uma Aplicação Android

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

--- 

Agora que já sabemos o que é o Android, como funciona, entendemos a base de uma aplicação android e seus principais compenentes e também instalamos o ambiente de desenvolvimento e estudamos a estrutura do projeto estamos prontos para começarmos como o desenvolvimento de fato, com a linguagem de marcação utilizada no front end dos nossos aplicativos, o XML.

---

## XML

No desenvolvimento de aplicativos Android, o XML (eXtensible Markup Language) desempenha um papel essencial para definir a interface gráfica e organizar recursos do aplicativo. Ele é amplamente utilizado no desenvolvimento Android para descrever layouts, temas, valores, strings, cores e outros recursos de forma estruturada e separada do código-fonte em Java ou Kotlin

---

###  O Papel do XML no Desenvolvimento Android
No Android, o XML é usado principalmente para:

### **1. Definir a interface do usuário (layouts)**:

- Criação das telas do aplicativo (como botões, textos e imagens).
- O arquivo XML especifica onde os elementos aparecem na tela e suas propriedades (tamanho, posição, cor, etc.).
  
### **2. Armazenar recursos reutilizáveis**:

- Strings, cores, dimensões, estilos e temas são armazenados em arquivos XML para facilitar o gerenciamento e a tradução.
  
### **3. Separar o design do código de lógica**:

O XML permite que o design da interface seja separado da lógica implementada em Java/Kotlin.
- Isso ajuda a manter o código mais organizado e facilita mudanças no layout sem alterar o código-fonte principal.

###  Estrutura Básica de um Arquivo XML

Um arquivo XML no Android segue uma estrutura hierárquica e baseada em tags.

``` XML

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Olá, Mundo!" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Clique Aqui" />
</LinearLayout>

```

- **Declaração XML**: <?xml version="1.0" encoding="utf-8"?> define o tipo de arquivo.
- **Tag raiz**: LinearLayout é a tag principal que organiza os elementos dentro dela.
- **Elementos-filhos**: TextView e Button são elementos da interface.
- **Atributos**: Propriedades de cada elemento (ex.: android:layout_width, android:text).

Esses arquivos XMl que são as interfaces se localizam na pasta: `res/layout/`.
Muitos dos arquivos de configuração também são em XML, entre eles temos:
- Configurações do App e permissões em `AndroidManifest.xml`
- Arquivos de configuração de constantes em `res/` como `strings.xml`, `colors.xml` e `styles.xml`.
- Arquivos de configurações de arquivos de imagens ou videos, dentro da pasta `res/drawable`.

### Exemplo do código de uma activity 

**A tela:**

<div align="center">
    <img src="https://github.com/user-attachments/assets/bdfcece2-46b0-4cf0-bafd-86742c9ce156" alt="image">
</div>

**Seu código**

``` XML
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/BACK">

    <LinearLayout

        android:id="@+id/lin"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:background="@android:color/transparent"
        android:padding="8dp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent">

        <ImageView
            android:id="@+id/Road"
            android:layout_width="100dp"
            android:layout_height="100dp"
            android:src="@drawable/rua" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Solicitar Manutenção"
            android:fontFamily="@font/aclonica"
            android:textSize="30dp"
            android:layout_gravity="center_vertical"
            android:layout_marginStart="20dp"/>
    </LinearLayout>

    <!-- CardView 1 -->
    <androidx.cardview.widget.CardView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="16dp"
        android:id="@+id/first"
        android:layout_marginTop="8dp"
        app:cardCornerRadius="12dp"
        app:layout_constraintTop_toBottomOf="@id/lin"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent">

        <RelativeLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="16dp">

            <TextView
                android:id="@+id/title1"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Buraco Gigante na pista"
                android:textSize="18sp"
                android:textStyle="bold" />

            <TextView
                android:id="@+id/description1"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_below="@id/title1"
                android:layout_marginTop="8dp"
                android:text="Buraco de 4m de diametro na BR-262"
                android:textSize="14sp" />

            <CheckBox
                android:id="@+id/checkbox1"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_alignParentEnd="true"
                android:layout_centerVertical="true"/>

        </RelativeLayout>
    </androidx.cardview.widget.CardView>

    <!-- CardView 2 -->
    <androidx.cardview.widget.CardView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="16dp"
        android:layout_marginTop="8dp"
        app:cardCornerRadius="12dp"
        app:layout_constraintTop_toBottomOf="@id/first"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent">

        <RelativeLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="16dp">

            <TextView
                android:id="@+id/title2"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Encosta perto de cair"
                android:textSize="18sp"
                android:textStyle="bold" />

            <TextView
                android:id="@+id/description2"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_below="@id/title2"
                android:layout_marginTop="8dp"
                android:text="Próximo ao posto 3 corações"
                android:textSize="14sp" />

            <CheckBox
                android:id="@+id/checkbox2"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_alignParentEnd="true"
                android:layout_centerVertical="true"/>
        </RelativeLayout>
    </androidx.cardview.widget.CardView>

    <androidx.appcompat.widget.AppCompatButton
        android:id="@+id/bt_entrar"
        style="@style/Button"
        android:text="Enviar"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"

        android:layout_marginTop="400dp"

        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <!-- Adicione mais CardViews conforme necessário -->

</androidx.constraintlayout.widget.ConstraintLayout>


```

Para mais informações detalhadas, visite a [**Documentação oficial sobre XML no Android**](https://developer.android.com/guide/topics/resources/overview).

---

Agora que já vimos o XML e como montar a estrutura visual da sua página, é hora de implementar a parte lógica e funcionl do seu aplicativo, o Back-End e para isso estudar o uso das duas linguagens mais usadas para esse fim. O Java e o Kotlin.

## Java e Kotlin 

### **Java no Desenvolvimento Android**

Java foi a linguagem oficial para o desenvolvimento Android desde o início do sistema até 2017, quando a Google introduziu Kotlin como uma alternativa. Apesar de não ser mais a linguagem principal, Java continua amplamente utilizado, com uma vasta base de código e suporte contínuo.

### **Características**
- **Fortemente tipada:** Java exige que você declare explicitamente os tipos de dados, o que ajuda na legibilidade do código.
- **Compatibilidade retroativa:** Permite que você crie aplicativos que funcionem em versões mais antigas do Android (útil para alcançar mais usuários).
- **Ampla comunidade:** Por ser mais antiga, tem uma vasta comunidade de desenvolvedores e uma infinidade de bibliotecas já prontas.
- **Simplicidade inicial:** A curva de aprendizado é um pouco mais fácil para quem já tem experiência em linguagens como C ou C++.

### **Vantagens no Desenvolvimento Mobile**
1. **Estabilidade e Maturidade:** Java é uma linguagem madura, com muitos exemplos e documentação.
2. **Base de código existente:** Projetos antigos e bibliotecas amplamente utilizam Java, tornando-a essencial para manutenção de aplicativos legados.
3. **Portabilidade:** Java é executado na JVM (Java Virtual Machine), o que facilita a reutilização de partes do código em outros contextos.

### **Desvantagens no Desenvolvimento Mobile**
1. **Verbosidade:** Programar em Java pode exigir mais código para tarefas simples, o que pode levar a arquivos grandes e repetitivos.
2. **Novas funcionalidades:** Algumas APIs mais recentes do Android foram projetadas com Kotlin em mente, o que faz o uso do Java parecer menos fluido nesses casos.

Para mais informações detalhadas, visite a [**Documentação oficial do Java**](https://docs.oracle.com/en/java/).

---

### **Kotlin no Desenvolvimento Android**

Kotlin foi introduzido pela JetBrains em 2011 e adotado oficialmente pela Google como a linguagem principal para desenvolvimento Android em 2017. Ele é totalmente interoperável com Java, permitindo que ambas as linguagens coexistam no mesmo projeto.

### **Características**
- **Sintaxe concisa:** Reduz a quantidade de código necessário para realizar tarefas comuns.
- **Segurança contra NullPointerException:** Kotlin introduz o conceito de **tipos nulos** que força o desenvolvedor a tratar situações onde variáveis podem ser nulas.
- **Compatibilidade com Java:** É possível usar bibliotecas escritas em Java diretamente no código Kotlin.
- **Orientado a desenvolvedores modernos:** Possui suporte integrado para corrotinas, que facilitam o trabalho com **tarefas assíncronas**.

### **Vantagens no Desenvolvimento Mobile**
1. **Menos código repetitivo:** Recursos como lambdas, extensões e data classes eliminam a necessidade de boilerplate code.
2. **Desempenho:** Como Kotlin é compilado para bytecode Java, ele tem o mesmo desempenho em tempo de execução.
3. **Corrotinas:** Simplificam a execução de operações assíncronas (ex.: chamadas de rede).
4. **Melhor suporte às APIs modernas:** Algumas funcionalidades, como Jetpack Compose, são projetadas diretamente com Kotlin em mente.

### **Desvantagens no Desenvolvimento Mobile**
1. **Curva de aprendizado:** Para quem vem de Java ou outra linguagem imperativa, pode levar tempo para se acostumar à sintaxe e aos conceitos mais modernos de Kotlin.
2. **Recursos avançados:** Apesar de conciso, exige entender algumas abstrações modernas que podem confundir iniciantes.

Para mais informações detalhadas, visite a [**Documentação oficial do Kotlin**](https://kotlinlang.org/docs/home.html).

## Conceitos básicos de Aplicações Mobile

O Java e o Kotlin serve para definir a lógica da aplicação, estabelecer suas regras de negócio e promover uma interação como o usuário.
Para isso é fundamental exemplos com o uso dos principais conceitos do Back-End Android:

### **1. Pegar o ID de um compontente** 

Para podermos interagir como os componentes e suas ações precisamos obter sua instância a partir de seu id.

**Java:**

``` Java

Button myButton = findViewById(R.id.my_button);
TextView myText = findViewById(R.id.my_text);


```

**Kotlin:**

``` Kotlin

val myButton: Button = findViewById(R.id.my_button)
val myText: TextView = findViewById(R.id.my_text)


```

### **2.Criar um Método para um Evento de Clique em um Botão**

Precisamo usar um Listener no objeto em que está a instância do nosso comoponente para podermos lidar como eventos.

**Java:**

``` Java

Button myButton = findViewById(R.id.my_button);
myButton.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // Ação a ser executada quando o botão for clicado
        Toast.makeText(getApplicationContext(), "Botão clicado!", Toast.LENGTH_SHORT).show();
    }
});


```

**Kotlin:**

``` Kotlin

val myButton: Button = findViewById(R.id.my_button)
myButton.setOnClickListener {
    // Ação a ser executada quando o botão for clicado
    Toast.makeText(applicationContext, "Botão clicado!", Toast.LENGTH_SHORT).show()
}


```

### **3.Abrir Outra Tela (Intent)** 

Para um App completo, precisamos de várias telas, cada um com seu propósito e para isso temos que ter a possibilidade de usar de um Intent para abrir essa nova tela.

**Java:**

``` Java

Intent intent = new Intent(CurrentActivity.this, NextActivity.class);
startActivity(intent);


```

**Kotlin:**

``` Kotlin

val intent = Intent(this, NextActivity::class.java)
startActivity(intent)


```

### **4.Modificar a Cor de um Componente em Resposta a um Evento**

Precisamos também muitas vezes interagir com nossos componentes não só recebendo seus eventos, mas também modificando algum atributo dele.

**Java:**

``` Java

Button myButton = findViewById(R.id.my_button);
myButton.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        myButton.setBackgroundColor(getResources().getColor(R.color.colorPrimary));
    }
});


```

**Kotlin:**

``` Kotlin

val myButton: Button = findViewById(R.id.my_button)
myButton.setOnClickListener {
    myButton.setBackgroundColor(resources.getColor(R.color.colorPrimary))
}


```

### **5. Exibir mesnagem com um Toast** 

É muito usual a comunicação do App com o usuário por meio de mensagem do próprio sistema operacional, como pop-ups ou avisos, para isso pode ser usado o Toast, entre outros.

**Java:**

``` Java

Toast.makeText(getApplicationContext(), "Mensagem exibida", Toast.LENGTH_SHORT).show();

```

**Kotlin:**

``` Kotlin

Toast.makeText(applicationContext, "Mensagem exibida", Toast.LENGTH_SHORT).show()

```

---

Essas são somente algumas funcionalidades básicas, mas que te permitirão ter uma noção de como o Java ou Kotlin interagem de fato com sua aplicação, permitindo de fato a interatividade e não uma tela estática.

## **Exemplo de Java e Kotlin**

Exemplo de activity de tela de login, em que o usuário digita seu E-mail e senha, essas informações são buscadas no banco de dados Firebase e se permtido o usuário é direcionado para a tela principal, além de ter a opção de se redirecionar para outra tela para criar conta:

### **Tela**: 
<div align="center">
    <img src="https://github.com/user-attachments/assets/c64f20de-3e75-4661-9cc1-cc5db5b7a985" alt="image">
</div>

### **XML** 

``` XML

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.musclemanager.Login">

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"

        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintBottom_toBottomOf="parent"
        android:layout_marginBottom="200dp"
        android:src="@drawable/gym"/>

    <ImageView
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:src="@drawable/mm"

        app:layout_constraintTop_toTopOf="parent"
        />

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Muscle Manager"
        android:textStyle="bold"
        android:textColor="@color/orange"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        android:layout_marginTop="140dp"
        android:layout_marginStart="38dp"
        android:textSize="25dp"/>

    <androidx.constraintlayout.widget.ConstraintLayout
        android:id="@+id/constraintLogin"

        android:layout_width="match_parent"
        android:layout_height="360dp"

        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"


        android:background="@drawable/backgroundconstraintlogin"
        android:backgroundTint="@color/black">

    <EditText
        android:id="@+id/emailEdit"

        android:layout_width="360dp"
        android:layout_height="60dp"

        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="30dp"
        android:hint="  Email"
        android:drawableEnd="@drawable/ic_email"
        android:paddingEnd="9dp"
        android:inputType="textEmailAddress"
        android:background="@drawable/backgroundeditlogin"
        />

    <EditText
        android:id="@+id/senhaEdit"

        android:layout_width="360dp"
        android:layout_height="60dp"

        app:layout_constraintTop_toBottomOf="@id/emailEdit"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="30dp"
        android:hint="  Senha"
        android:drawableEnd="@drawable/ic_eye"
        android:paddingEnd="9dp"
        android:inputType="textPassword"
        android:autofillHints="password"
        android:background="@drawable/backgroundeditlogin"
        />

        <Button
            android:id="@+id/butLogin"

            android:layout_width="360dp"
            android:layout_height="60dp"

            android:text="Entrar"
            android:textSize="20dp"
            app:layout_constraintTop_toBottomOf="@id/senhaEdit"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            android:layout_marginTop="50dp"
            android:background="@drawable/backgroundeditlogin"
            android:backgroundTint="@color/orange"/>

        <Button
            android:id="@+id/butCriarconta"

            android:layout_width="360dp"
            android:layout_height="wrap_content"

            app:layout_constraintTop_toBottomOf="@id/butLogin"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            android:layout_marginTop="10dp"
            android:background="@android:color/transparent"

            android:text="Criar conta"
            android:textColor="@color/orange"
            android:textSize="20dp"/>

    </androidx.constraintlayout.widget.ConstraintLayout>

</androidx.constraintlayout.widget.ConstraintLayout>

````


### **Código em Java**:

``` Java 

package com.example.musclemanager;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

import androidx.activity.EdgeToEdge;
import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
import com.google.firebase.auth.AuthResult;
import com.google.firebase.auth.FirebaseAuth;
import com.google.firebase.auth.FirebaseUser;
import com.google.firebase.firestore.FirebaseFirestore;

public class Login extends AppCompatActivity {

    // Objeto responsável por autenticar usuários no Firebase
    private FirebaseAuth mAuth;

    // Objeto para acessar o Firestore, um banco de dados na nuvem
    private FirebaseFirestore db;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        // Configuração para tornar a interface adaptada às bordas da tela
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_login);

        // Configura os preenchimentos (padding) na tela para evitar sobreposição com barras do sistema
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });

        // Botão para criar uma conta. Ao clicar, abre a tela de criação de conta
        Button butCriarConta = findViewById(R.id.butCriarconta);
        butCriarConta.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Inicia a activity CriarConta ao clicar no botão
                Intent intent = new Intent(Login.this, CriarConta.class);
                startActivity(intent);
            }
        });

        // Inicializa o objeto de autenticação do Firebase
        mAuth = FirebaseAuth.getInstance();

        // Verifica se já existe um usuário logado
        FirebaseUser currentUser = mAuth.getCurrentUser();

        // Inicializa o objeto para acessar o Firestore
        db = FirebaseFirestore.getInstance();

        // Caso exista um usuário logado, ele pode ser redirecionado ou ter alguma ação específica
        if (currentUser != null) {
            // Neste caso, a ação está comentada
            // reload();
        }

        // Obtém as referências para os campos de texto e o botão da tela de login
        TextView email = findViewById(R.id.emailEdit); // Campo para o e-mail
        TextView senha = findViewById(R.id.senhaEdit); // Campo para a senha
        Button button = findViewById(R.id.butLogin);   // Botão de login

        // Configura o comportamento do botão de login
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Verifica se os campos de e-mail ou senha estão vazios
                if (String.valueOf(email.getText()).isEmpty() || String.valueOf(senha.getText()).isEmpty()) {
                    // Mostra uma mensagem pedindo para preencher os campos
                    Toast.makeText(Login.this, "Preencha os campos!", Toast.LENGTH_SHORT).show();
                } else {
                    // Faz o login com os dados informados pelo usuário
                    mAuth.signInWithEmailAndPassword(String.valueOf(email.getText()), String.valueOf(senha.getText()))
                            .addOnCompleteListener(Login.this, new OnCompleteListener<AuthResult>() {
                                @Override
                                public void onComplete(@NonNull Task<AuthResult> task) {
                                    // Verifica se o login foi bem-sucedido
                                    if (task.isSuccessful()) {
                                        // Se o login foi bem-sucedido, obtém o usuário logado
                                        FirebaseUser user = mAuth.getCurrentUser();

                                        // Abre a tela principal (MainActivity)
                                        Intent intent = new Intent(Login.this, MainActivity.class);
                                        startActivity(intent);

                                    } else {
                                        // Caso o login falhe, exibe uma mensagem de erro
                                        Toast.makeText(Login.this, "Usuário ou senha inválidos", Toast.LENGTH_SHORT).show();
                                    }
                                }
                            });
                }
            }
        });
    }
}

```

### **Código em Kotlin**:

``` Kotlin

package com.example.musclemanager

import android.content.Intent
import android.os.Bundle
import android.view.View
import android.widget.Button
import android.widget.TextView
import android.widget.Toast
import androidx.activity.EdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.graphics.Insets
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat
import com.google.firebase.auth.FirebaseAuth
import com.google.firebase.auth.FirebaseUser
import com.google.firebase.firestore.FirebaseFirestore

class Login : AppCompatActivity() {

    // Objeto responsável por autenticar usuários no Firebase
    private lateinit var mAuth: FirebaseAuth

    // Objeto para acessar o Firestore (banco de dados na nuvem)
    private lateinit var db: FirebaseFirestore

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // Configuração para tornar a interface adaptada às bordas da tela
        EdgeToEdge.enable(this)
        setContentView(R.layout.activity_login)

        // Configura os preenchimentos (padding) na tela para evitar sobreposição com barras do sistema
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars: Insets = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets
        }

        // Botão para criar uma conta
        val butCriarConta: Button = findViewById(R.id.butCriarconta)
        butCriarConta.setOnClickListener {
            // Inicia a activity CriarConta ao clicar no botão
            val intent = Intent(this, CriarConta::class.java)
            startActivity(intent)
        }

        // Inicializa o objeto de autenticação do Firebase
        mAuth = FirebaseAuth.getInstance()

        // Verifica se já existe um usuário logado
        val currentUser: FirebaseUser? = mAuth.currentUser

        // Inicializa o Firestore
        db = FirebaseFirestore.getInstance()

        // Se o usuário já estiver logado, pode redirecioná-lo para outra tela
        if (currentUser != null) {
            // Neste caso, está comentado
            // reload()
        }

        // Referências para os campos de entrada e o botão de login
        val email: TextView = findViewById(R.id.emailEdit) // Campo para o e-mail
        val senha: TextView = findViewById(R.id.senhaEdit) // Campo para a senha
        val button: Button = findViewById(R.id.butLogin)   // Botão de login

        // Configura o comportamento do botão de login
        button.setOnClickListener {
            // Verifica se os campos estão vazios
            if (email.text.isNullOrEmpty() || senha.text.isNullOrEmpty()) {
                // Mostra uma mensagem pedindo para preencher os campos
                Toast.makeText(this, "Preencha os campos!", Toast.LENGTH_SHORT).show()
            } else {
                // Faz o login com os dados informados
                mAuth.signInWithEmailAndPassword(email.text.toString(), senha.text.toString())
                    .addOnCompleteListener(this) { task ->
                        if (task.isSuccessful) {
                            // Se o login foi bem-sucedido, redireciona para a tela principal
                            val intent = Intent(this, MainActivity::class.java)
                            startActivity(intent)
                        } else {
                            // Caso o login falhe, exibe uma mensagem de erro
                            Toast.makeText(this, "Usuário ou senha inválidos", Toast.LENGTH_SHORT).show()
                        }
                    }
            }
        }
    }
}

```

## **Comparação Java x Kotlin**

| **Aspecto**             | **Java**                                   | **Kotlin**                                 |
|--------------------------|--------------------------------------------|--------------------------------------------|
| **Verbosidade**          | Mais verboso                               | Código mais conciso                        |
| **Null Safety**          | Precisa de verificações manuais            | Suporte nativo para tipos nulos            |
| **Interoperabilidade**   | Totalmente compatível com Kotlin           | Totalmente compatível com Java             |
| **Comunidade**           | Ampla e madura                            | Crescendo rapidamente                     |
| **Modernidade**          | APIs mais antigas e estáveis               | APIs modernas e orientadas a produtividade|
| **Uso com Jetpack Compose** | Suporte completo, mas menos fluido         | Feito para Kotlin                          |

---

## **Quando escolher Java ou Kotlin?**

### **Use Java quando:**
- Você está trabalhando em um projeto legado que já utiliza Java.
- Sua equipe tem mais experiência em Java.
- O aplicativo precisa de compatibilidade com dispositivos muito antigos.

### **Use Kotlin quando:**
- Está criando um novo projeto.
- Deseja escrever menos código e evitar bugs relacionados a nulos.
- Vai trabalhar com APIs mais modernas, como **Jetpack Compose**.

---

**Ambas as linguagens são poderosas e podem ser usadas juntas em um mesmo projeto, permitindo a migração gradual de um código legado em Java para Kotlin. Essa interoperabilidade facilita a escolha baseada em necessidades específicas do projeto.**

## **Conclusão** 

  Esse é somente o começo do seu caminho no Desenvolvimento Android e Mobile num geral, pois a maioria dos conceitos vistos aqui, se aplicam também ao desenvolvimento em IOS, ou Híbrido.  
  Esperamos ter sido de ajuda em seus estudos em Engenharia de Software.  


  
Seguem links para estudo: 

- [**Guia desenvolvimento Android Google**](https://developer.android.com/develop?hl=pt-br).
- [**Documentação oficial sobre XML no Android**](https://developer.android.com/guide/topics/resources/overview).
- [**Documentação oficial do Java**](https://docs.oracle.com/en/java/).
- [**Documentação oficial do Kotlin**](https://kotlinlang.org/docs/home.html).

Exemplos de Aplicativos simples desenvolvidos por nós:

- [**Aplicativo Muscle Manager**](https://github.com/ArthurFrade1/MuscleManager/tree/master).
- [**Aplicativo Muscle Manager**](https://github.com/GuilhermeADev/Aplicativo-Inclusao).

Autores:

- **Arthur Afonso Frade de Aquino**
- **Arthur Miranda Moreira**
- **Caio Rangel Nunes**
- **Luís Felipe de Paula Mendes**
