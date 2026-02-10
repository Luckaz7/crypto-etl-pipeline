# 🪙 Crypto Data Pipeline: Extract, Transform & Load

## 📝 Descrição do Projeto

Este projeto implementa um pipeline de dados automatizado para monitorar preços de criptomoedas em tempo real. O script realiza o scraping de dados do CoinMarketCap, processa as informações para um formato estruturado e gerencia a persistência dos dados de forma incremental, garantindo que o histórico seja preservado sem sobrescritas.

Originalmente desenvolvido para Google Colab com integração ao Google Drive, o projeto é facilmente adaptável para execução de jobs agendados em ambientes como Databricks ou instâncias EC2.

## 🚀 Funcionalidades

    Extração: Captura de preços em tempo real via Web Scraping.

    Transformação: Limpeza de strings (moeda/símbolo) e padronização de fuso horário (BRT - UTC-3).

    Carga Incremental: Lógica que verifica a existência de um histórico prévio e concatena novos dados.

    Persistência: Armazenamento resiliente em CSV com suporte a sistemas de arquivos em nuvem.

## 🛠️ Tecnologias Utilizadas

    Linguagem: Python

    Bibliotecas de Dados: Pandas para manipulação e estruturação.

    Web Scraping: BeautifulSoup4 e requests.

    Time Management: pytz e datetime para gestão de fuso horário brasileiro.

    Cloud Storage: Integração com Google Drive (adaptável para DBFS/S3).

## 📁 Estrutura do Código

O projeto é dividido em funções modulares seguindo os princípios de clean code:

    extract_dados(): Acessa a URL e isola o elemento HTML contendo o preço.

    trans_dados(): Formata os dados crus em um dicionário estruturado.

    data_atual() / hora_atual(): Garante o registro temporal correto no fuso America/Sao_Paulo.

    carga_dados(): Gerencia a inteligência do pipeline (Leitura -> Concatenação -> Persistência).

## 📈 Exemplo de Dados Capturados

|moeda|simbolo|preco|data|hora|
|Bitcoin|BTC|52140.50|09-02-2026|14:00:05|
|Ethereum|ETH|2850.12|09-02-2026|14:00:05|

## 🔧 Como Executar

  **Clone o repositório:**

    git clone https://github.com/seu-usuario/nome-do-repositorio.git

  **Instale as dependências:**

    pip install pandas requests beautifulsoup4 pytz

  **Configure o caminho do arquivo no script (path) para o seu diretório local ou cloud.**

  **Execute o script principal para iniciar a coleta.**
