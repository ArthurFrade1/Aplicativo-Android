# Aplicativo-Android
Roteiro prático para o desenvolvimento de um aplicativo Android nas linguagens Java ou Kotlin
Esse repositório é um guia de como criar seu primeiro Aplicativo Android, apresentando o ambiente de desenvolvimento e duas linguagens: Java e Kotlin.

O objetivo é que esse roteiro permita introduzir a apresentar os principais conceitos do desenvolvimento Mobile, servindo como uma possível porta de entrada pra os estudos desse ramo da Engenharia de Software.

---

## A arquitetura do Sistema Operacional Android

O Android é um sistema operacional projetado principalmente para dispositivos móveis, como smartphones e tablets. Ele é baseado em um kernel Linux modificado e foi otimizado para atender às necessidades de dispositivos com recursos limitados, como bateria, memória e potência de processamento. Ele é desenvolvido a partir de uma arquitetura modular, é estruturado em camadas que trabalham juntas para oferecer uma experiência fluida ao usuário, sendo elas:

- **Kernel Linux**: Gerencia hardware, segurança e drivers de dispositivos (CPU, memória, bateria, sensores, etc.).
- **Bibliotecas Nativas**: Proporcionam funcionalidades específicas, como gráficos (OpenGL), banco de dados (SQLite), e criptografia (SSL).
- **Android Runtime (ART)**: Executa os aplicativos Android, convertendo o código de alto nível (Java/Kotlin) para instruções compreendidas pelo hardware.
- **Framework de Aplicação**: Oferece APIs para que os desenvolvedores criem aplicativos, fornecendo acesso ao hardware e funcionalidades do sistema.
- **Interface de Usuário e Aplicativos**: A camada que o usuário interage diretamente, composta pela interface gráfica e pelos aplicativos.
