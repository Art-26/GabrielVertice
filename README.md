# PROJETO: WAR ROOM — COBERTURA DE VÉRTICES (Vertex Cover)

* Este projeto foi realizado em Java
* **JDK** utilizado no projeto: JDK 21

---

## Visão geral
Este programa resolve, de forma **aproximada (heurística)**, o problema **Vertex Cover (Cobertura de Vértices)** em grafos **não direcionados**.

A aplicação:
1. Lê do console uma rede (vértices/dispositivos e arestas/conexões).
2. Executa uma heurística baseada em **graus** para construir uma cobertura de vértices.
3. Exibe a lista de dispositivos escolhidos (aproximação), o tamanho da cobertura e o tempo de execução.

---

## Estrutura do projeto
- **`src/Main.java`**: interface com o usuário (leitura do grafo) e impressão do resultado.
- **`src/Grafo.java`**: estrutura do grafo e operações como adicionar aresta, obter vizinhos, grau e remover arestas de um vértice.
- **`src/VertexCover.java`**: implementação da heurística que monta a cobertura.

---

## Pré-requisitos
- Java instalado (JDK)
- IDE Java recomendada (IntelliJ/Eclipse ou Visual Studio Code)

---

## Como executar o projeto

### 1) Como executar no IntelliJ
1. Abra o IntelliJ.
2. Clique em **Open** e selecione a pasta do projeto.
3. Execute o arquivo **`src/Main.java`** clicando no botão verde de Play (current file).

---

### 2) Como executar no Eclipse
1. Abra o Eclipse IDE.
2. Vá em **File > Import... > General > Existing Projects into Workspace** (ou similar).
3. Selecione a pasta do projeto.
4. Clique em **Finish**.
5. Em **Package Explorer**, abra **`src/Main.java`** e execute pelo botão **Run** (ou botão verde).

---

### 3) Como executar no Visual Studio Code
1. Abra o VS Code.
2. Clique em **Abrir pasta** e selecione a pasta do projeto.
3. Abra **`src/Main.java`**.
4. Execute pelo botão de **Play** no canto superior.

>[!NOTE]
> Instale as extensões **Extension Pack for Java** e **Portuguese (Brazil) Language Pack** (opcional, apenas para PT-BR).

---

### 4) Como executar via Prompt de Comando (Windows)
1. Abra o **Prompt de Comando** (Windows + R > digite `cmd` > Enter).
2. Entre na pasta do projeto.
   - Exemplo (ajuste o caminho):
   ```bash
   cd C:\Users\SEU_USUARIO\Downloads\GabrielVertice
   ```
3. Compile os arquivos Java:
   ```bash
   javac -d bin src/*.java
   ```
4. Execute:
   ```bash
   java -cp bin Main
   ```
>[!TIP]
> Se você rodar novamente, a pasta `bin` provavelmente já existe, então o passo de compilação (passo 3) pode ser necessário apenas quando houver mudanças no código.

---

## Como usar (entrada do console)
Durante a execução, o programa solicitará:

1. **Quantidade de dispositivos (vértices)**: informe `n`.
2. **Nome de cada dispositivo**: informe os nomes (um por linha).
3. **Quantidade de conexões (arestas)**: informe `m`.
4. Para cada conexão, informe os índices `u` e `v`:
   - `u` = dispositivo de origem (índice de `0` a `n-1`)
   - `v` = dispositivo de destino (índice de `0` a `n-1`)

---

## Saída esperada
Ao final, o programa imprime:
- **Ponto de partida** (vértice escolhido inicialmente)
- Logs durante a execução (vértices adicionados e mudanças de estratégia)
- **RESULTADO FINAL**:
  - Dispositivos na cobertura mínima **aproximada**
  - Tamanho da cobertura
  - Tempo de execução em milissegundos
- **ANÁLISE DE COMPLEXIDADE** (conforme reportado pelo programa)

---

## Observações sobre a heurística
- O algoritmo escolhe vértices para cobrir arestas de forma gulosa/heurística.
- Ele remove arestas incidentes ao vértice selecionado à medida que avança.
- Quando não há um “próximo” melhor entre os vizinhos, ocorre um **reinício** para o vértice de maior grau global no grafo restante.

---
