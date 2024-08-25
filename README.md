# HackBahia - Offensive recon with GitHub Actions

## Configuração

Criar os seguintes secrets no repositório:

- `CRIBL_HOST`: hostname para a instância do [Cribl](https://cribl.io/) Stream configurado para Splunk/HEC
- `CRIBL_API_KEY`: API KEY criada na configuração do Splunk/HEC

## Workflows

Workflows existentes e sua breve descrição

### 1. hednsextractor

source: `.github/workflows/hednsextractor.yaml`

Executa o `hednsextractor` salva a saída da aplicação como sumário e envia dados para o `cribl`

### 2. httpx

source: `.github/workflows/httpx.yaml`

Executa o `httpx` salva a saída da aplicação como sumário e envia dados para o `cribl`

### 3. nuclei

source: `.github/workflows/nuclei.yaml`

Executa o `nuclei` salva a saída da aplicação como sumário e envia dados para o `cribl`

### 4. subfinder

source: `.github/workflows/subfinder.yaml`

Executa o `subfinder` salva a saída da aplicação como sumário e envia dados para o `cribl`

### 5. Mass

source: `.github/workflows/mass.yaml`

Executa o `httpx` tendo como uma entrada um arquivo com várias URLs, a saída do httpx é uma lista de endereços online que é então utlizado como entrada para o `nuclei`. Como observação o nuclei utiliza o httpx internamente podendo ser habilitado/desabilitado através de parâmetros na linha comando, logo esse fluxo é apenas um exemplo.

## Links e aplicações utilizadas

Segue abaixo links de aplicações utilizadas e mencionadas na apresentação.

* https://github.com/HuntDownProject/HEDnsExtractor
* https://github.com/HuntDownProject/logme
* https://github.com/neriberto/bloodhound
* https://github.com/projectdiscovery/subfinder
* https://github.com/projectdiscovery/httpx
* https://github.com/projectdiscovery/nuclei
* https://cribl.io/
* https://www.splunk.com/