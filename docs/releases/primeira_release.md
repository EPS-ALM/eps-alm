# Documento de Release - Assets and Liability Management (ALM)

## Visão Geral
Este documento descreve as funcionalidades entregues, dificuldades encontradas, melhorias e pendências do projeto. Além disso, apresenta uma explicação de cada repositório associado ao projeto.

## O Produto - Link para o MVP

O ALM é um sistema de gestão de ativos e passivos que visa auxiliar na tomada de decisões financeiras. A plataforma oferece funcionalidades como previsão de preço de ação, alocação ideal da carteira, análise de risco país, monitoramento de risco de ativos digitais, gestão de risco de investimento, gerenciamento de risco de taxa de juros, entre outros.

> **Para acessar a plataforma, clique** [aqui](https://alm-frontend.onrender.com/).

## Funcionalidades e Serviços
Liste as funcionalidades implementadas nesta release:
- Previsão de preço de ação utilizando LSTM
- Previsão de preço de ação utilizando VAR
- ⁠Alocação ideal da carteira usando Teoria do Portfólio Moderno de Markowitz
- Alocação ideal da carteira usando Índice de Sharpe
- Análise de Risco País
- Monitoramento de Risco de Ativos Digitais
- Gestão de Risco de Investimento
- Gerenciamento de Risco de Taxa de Juros
- Análise de crescimento vegetativo com população economicamente ativa X aposentados
- Mostragem de liquidez da carteira, com entradas e saídas do fluxo de caixa
- Análise de sensibilidade de carteira, com taxas SELIC, dos planos oferecidos e de cenário exagerado

## Repositórios do Projeto

### 1. [alm-risk-manager](https://github.com/EPS-ALM/alm-risk-manager)
- **Objetivo**: Gestão de riscos.
- **Principais Componentes**:
    - Análise de Risco País;
    - Gerenciamento de Risco de Taxa de Juros;
    - Gestão de Risco de Investimento;
    - Monitoramento de Risco de Ativos Digitais;

### 2. [alm-service](https://github.com/EPS-ALM/alm-service)
- **Objetivo**: Repositório destinado para o serviço que estabelecerá a comunicação com o front end.
- **Principais Componentes**:
    - Centralizador de serviços;

### 3. [alm-assets](https://github.com/EPS-ALM/alm-assets)
- **Objetivo**: Gestão de ativos.
- **Principais Componentes**:
    - Integração de dados em tempo real;
    - Otimização de Portifólio;
    - Modelagem de derivativos (Hedge).

### 4. [alm-liability](https://github.com/EPS-ALM/alm-liability)
- **Objetivo**: Gestão de passivos.
- **Principais Componentes**:
    - Simulação de Cenários Econômicos;
    - Gerenciamento de Liquidez;
    - Análise de Sensibilidade da carteira;
    - Previsão de Fluxo de Caixa.

### 5. [stocks-forecasting](https://github.com/EPS-ALM/stocks-forecasting)
- **Objetivo**: Rede neural para o forecast do valor dos ativos definidos.
- **Principais Componentes**:
    - Predições curto prazo de preços de ações utilizando diversos modelos de redes neurais.


## Continuous Integration

Devido a natureza do projeto, a integração contínua é realizada apenas na camada `service`. A integração contínua é realizada através do GitHub Actions, que executa testes automatizados e verifica a qualidade do código a cada push realizado no repositório.

- **alm-service**: [workflow](https://github.com/EPS-ALM/alm-service/blob/main/.github/workflows/ci.yml)

## Continuous Deployment

O projeto está configurado para realizar o deploy automático no Heroku. Abaixo estão listados os links para os serviços disponíveis:

- **Service**: [alm-service](https://alm-service-eae21cd8fb32.herokuapp.com/portfolio-allocation)
- **Assets**: [alm-assets](https://alm-assets-898cc81ff044.herokuapp.com/)
- **Risk Manager**: [alm-risk-manager](https://almriskmanager-16e9ecd81666.herokuapp.com/)
- **Liability**: [alm-liability](http://187.84.176.16:10100/docs)
- **Docs**: [alm-docs](https://eps-alm.github.io/alm-docs/) - [workflow](https://github.com/EPS-ALM/alm-docs/blob/main/.github/workflows/main.yml)

## Pendências
Descreva as pendências conhecidas que precisam ser resolvidas:
- Dados reais de entradas e saídas do fluxo de caixa
- Estudo para definição das taxas dos planos oferecidos pela plataforma


## Links Úteis  

- **Repositórios**:  
  - [alm-risk-manager](https://github.com/EPS-ALM/alm-risk-manager)  
  - [alm-service](https://github.com/EPS-ALM/alm-service)  
  - [alm-assets](https://github.com/EPS-ALM/alm-assets)  
  - [alm-liability](https://github.com/EPS-ALM/alm-liability)  
  - [stocks-forecasting](https://github.com/EPS-ALM/stocks-forecasting)  
- **Documentos**:
  - [Documento de Arquitetura](https://eps-alm.github.io/alm-docs/artefatos/arquitetura/)
  - [Protótipo de Interface](https://eps-alm.github.io/alm-docs/artefatos/arquitetura/)
 - Abertura do Projeto
    - [Termo de Abertura do Projeto](https://eps-alm.github.io/alm-docs/artefatos/tap/)  
    - [Termo de Acordo de Serviço](https://eps-alm.github.io/alm-docs/artefatos/ts/)
    - [Termo de Acordo de Serviço Individual](https://eps-alm.github.io/alm-docs/acordo-servico-individual/acordos-servico/)
  - Acordos de Serviço
    - [Termo de Acordo de Serviço (Equipe Gestão de Ativos)](https://eps-alm.github.io/alm-docs/artefatos/acordo-equipe_ativos/)
    - [Termo de Acordo de Serviço (Equipe Gestão de Passivos)](https://eps-alm.github.io/alm-docs/artefatos/acordo-equipe_passivos/)
    - [Termo de Acordo de Serviço (Equipe Gestão de Riscos)](https://eps-alm.github.io/alm-docs/artefatos/acordo-equipe_riscos/)
  - Story map
    - [Personas](https://eps-alm.github.io/alm-docs/artefatos/storymap/personas/)
    - [Elicitação de requisitos](https://eps-alm.github.io/alm-docs/artefatos/storymap/elicitacao-requisitos/)
    - [Histórias de usuário](https://eps-alm.github.io/alm-docs/artefatos/storymap/historias-usuario/)
    - [Épicos](https://eps-alm.github.io/alm-docs/artefatos/storymap/epicos/)
    - [Priorização](https://eps-alm.github.io/alm-docs/artefatos/storymap/priorizacao/)

- **Issues**:  
  - [Ativos](https://github.com/EPS-ALM/alm-docs/labels/ativos)
  - [Passivos](https://github.com/EPS-ALM/alm-docs/labels/passivos)
  - [Riscos](https://github.com/EPS-ALM/alm-docs/labels/riscos)
  - [Features](https://github.com/EPS-ALM/alm-docs/labels/Feature) 

## Versionamento

| Versão | Data       | Descrição                      | Responsável     |
| ------ | ---------- | ------------------------------ | --------------- |
| 1.0    | 16/12/2024 | Criação da Página              | Fernando Vargas |
| 1.1    | 17/12/2024 | Adiciona CI/CD e link para MVP | Arthur Ferreira |