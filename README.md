# 🚀 Teste de Performance - BlazeDemo (JMeter)

Este projeto contém um teste de performance utilizando o **Apache JMeter** para simular o fluxo de compra de passagens aéreas no site BlazeDemo.

---

## 🎯 Objetivo

Validar se a aplicação suporta:

* **250 requisições por segundo (RPS)**
* **Tempo de resposta no percentil 90 (P90) menor que 2 segundos**

---

## 🌐 Sistema testado

* URL: https://www.blazedemo.com
* Cenário:

  * Acessar página inicial
  * Selecionar voo
  * Realizar compra

---

## 🧰 Tecnologias utilizadas

* Apache JMeter
* Java (JDK 8+)

---

## ⚙️ Pré-requisitos

Antes de executar, instale:

### ☕ Java

Verifique se está instalado:

```bash
java -version
```

Caso não esteja, instale o Java (JDK 8 ou superior).

---

### 🔧 Apache JMeter

1. Baixe o JMeter:
   https://jmeter.apache.org/download_jmeter.cgi

2. Extraia o arquivo `.zip` (Preferencialmente em Binaries)

---

## ▶️ Como executar o teste

### 🔹 Opção 1 — JMeter

1. Abra o JMeter:

   * Windows: `bin/jmeter.bat`
   * Linux/Mac: `bin/jmeter`

2. Vá em:

   ```
   File → Open
   ```

3. Selecione o arquivo:

   ```
   TesteTecnicoAgiBank.jmx
   ```

4. Clique em:
   ▶️ **Start**

---

### 🔹 Opção 2 — Linha de comando - Recomendado para poder gerar o relatório visual

1. Navegue até a pasta `bin` do JMeter:

```bash
cd apache-jmeter-5.6.3/bin
```

2. Execute o teste:

Sem o relatório visual:

```bash
jmeter -n -t /caminho/do/projeto/TesteTecnicoAgiBank.jmx -l resultado.jtl
```

Para gerar um relatório visual completo:

```bash
jmeter -n -t /caminho/do/projeto/TesteTecnicoAgiBank.jmx -l resultado.jtl -e -o relatorio
```

### 📁 Estrutura gerada:

```
/relatorio
  ├── index.html
  ├── content/
  └── statistics.json
```

Abra no navegador:

```
relatorio/index.html
```

---

## 📈 Interpretação dos resultados

As principais métricas a serem analisadas:

* **Throughput (req/s)** → Deve ser próximo de 250
* **90th Percentile (P90)** → Deve ser < 2000 ms
* **Error %** → Idealmente próximo de 0%

---

## 🧪 Cenários implementados

### 🔹 Load Test

* 100 usuários
* 250 req/s
* duração: 5 minutos

### ⚡ Spike Test

* 300 usuários
* 300 req/s
* duração: 2 minutos

---

## ⚠️ Observações importantes

* Este teste utiliza dados fixos (não há correlação dinâmica de voo)
* Em ambiente real, seria necessário:

  * uso de **CSV DataSet** para dados dinâmicos
  * validações com **Assertions**

---

## 🧠 Conclusão esperada

* O sistema deve suportar carga constante (Load Test)
* Pode apresentar degradação sob pico (Spike Test)
* Análise deve considerar:

  * latência
  * taxa de erro
  * estabilidade

---

## 👨‍💻 Autor

Luis Gustavo

QA Engineer | Automação de Testes
