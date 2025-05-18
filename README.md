# 🤖 AI Primeiros Socorros: Seu Agente Inteligente para Emergências de Saúde

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-AI-green?style=for-the-badge&logo=google)
![Google Maps API](https://img.shields.io/badge/Google%20Maps-API-red?style=for-the-badge&logo=googlemaps)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow?style=for-the-badge&logo=googlecolab)

---

## 🚑 O Problema: Emergências de Saúde e a Necessidade de Orientação Imediata

Em momentos de emergência de saúde, seja uma dor súbita no peito, um ferimento inesperado ou um mal-estar agudo, o pânico pode tomar conta. A falta de conhecimento imediato sobre os primeiros socorros adequados pode agravar a situação, e a busca por informações online muitas vezes resulta em dados dispersos, não confiáveis ou difíceis de interpretar sob pressão. Quando cada segundo conta, ter acesso a orientações claras, precisas e personalizadas é crucial, mas nem sempre uma ambulância ou um médico está disponível no exato momento.

---

## ✨ A Solução: Um Agente de IA para Primeiros Socorros

Apresentamos o **AI Primeiros Socorros**, um sistema inteligente e interativo construído com o poder do **Google Gemini (via Google Agent Development Kit - ADK)** e a precisão do **Google Maps API**. Este projeto visa preencher a lacuna de informação em momentos críticos, oferecendo um guia de primeiros socorros que não só orienta sobre como proceder, mas também avalia a gravidade da situação e localiza ajuda médica próxima.

Imagine ter um assistente pessoal que, ao descrever o que sente, pode:
* Realizar uma **triagem inicial** dos sintomas, coletando as informações essenciais.
* **Consolidar informações** adicionais para formar um quadro clínico completo e preciso.
* Buscar **orientações confiáveis** de primeiros socorros em tempo real na web.
* **Avaliar a urgência** da situação, recomendando ligar para o SAMU (192) ou procurar atendimento médico imediato em casos críticos.
* **Localizar hospitais e clínicas** nas proximidades da sua localização.
* Gerar **rotas diretas no Google Maps** para os locais de atendimento mais relevantes, facilitando o deslocamento.
* Compilar todas as informações em um **guia final de ações claro e detalhado**, formatado com tópicos e subtópicos para fácil compreensão.

Este agente não substitui o atendimento médico profissional, mas serve como uma ferramenta de **orientação imediata** que pode capacitar o usuário a tomar as primeiras ações corretas, potencialmente salvando vidas ou minimizando danos até a chegada da ajuda especializada, transformando o pânico em ação informada.

---

## 🛠️ Como Funciona: A Orquestração de Agentes Inteligentes

O AI Primeiros Socorros opera através de uma arquitetura modular, onde diferentes **Agentes de IA**, cada um com uma especialidade e objetivo específico, colaboram sob a orquestração de uma função principal. Essa colaboração garante uma resposta estruturada, precisa e abrangente, guiando o usuário passo a passo através da emergência:

### Visão Geral do Fluxo de Interação:

1.  **Coleta Inicial de Sintomas:** O usuário descreve o que está sentindo ao `agente_triagem`.
2.  **Expansão e Consolidação:** O `agente_coleta_sintomas_adicionais` pede mais detalhes e consolida todos os sintomas descritos.
3.  **Busca de Informações:** O `agente_busca_primeiros_socorros` utiliza o Google Search para encontrar as melhores práticas e tratamentos para os sintomas consolidados.
4.  **Avaliação de Emergência:** O `agente_avaliacao_emergencia` analisa a gravidade da situação com base nos sintomas e nos resultados da busca, recomendando a ação de emergência apropriada (ex: ligar 192).
5.  **Planejamento de Ações:** O `agente_planejamento_acoes` formula um plano de primeiros socorros conciso com base nas informações coletadas.
6.  **Localização de Ajuda Médica:** O `agente_localizacao_ajuda_medica` sinaliza a busca por hospitais e médicos próximos, que é executada por funções auxiliares da API do Google Maps.
7.  **Geração de Rotas:** O `agente_rota_navegacao` sinaliza a geração de links diretos para rotas no Google Maps para os locais de atendimento encontrados, também executada por funções auxiliares.
8.  **Orientação Final Detalhada:** O `agente_orientacao_detalhada` compila todas as informações e gera um guia de primeiros socorros claro, estruturado com tópicos e subtópicos, fornecendo orientações práticas e próximos passos.

### Os Agentes em Ação:

* **`agente_triagem`**: Inicia a conversa, coletando a descrição inicial dos sintomas do usuário.
* **`agente_coleta_sintomas_adicionais`**: Recebe os sintomas iniciais e as informações adicionais do usuário, consolidando-os em uma descrição completa e coesa da condição do paciente.
* **`agente_busca_primeiros_socorros`**: Especialista em pesquisa. Utiliza a ferramenta `Google Search` para encontrar informações confiáveis e atualizadas sobre como tratar a condição médica, focando em fontes oficiais de saúde, e retorna um resumo conciso dos resultados para uso dos próximos agentes.
* **`agente_avaliacao_emergencia`**: Analisa a descrição dos sintomas e os resultados da busca para determinar a gravidade da situação, instruindo o usuário a ligar imediatamente para o serviço de emergência (192 - SAMU no Brasil) se for uma emergência vital, ou a procurar atendimento médico se for uma situação menos urgente.
* **`agente_planejamento_acoes`**: Analisa os resultados da busca por primeiros socorros e elabora um plano de ações conciso e priorizado, fornecendo os passos a serem seguidos.
* **`agente_localizacao_ajuda_medica`**: Raciocina sobre a necessidade de localizar ajuda médica. Embora a busca real por hospitais e médicos seja feita por funções auxiliares da API do Google Maps, este agente orquestra essa etapa.
* **`agente_rota_navegacao`**: Raciocina sobre a necessidade de rotas para os locais de atendimento encontrados. A geração de links de rotas para navegação é feita por funções auxiliares do Google Maps.
* **`agente_orientacao_detalhada`**: O agente final e crucial. Ele compila todas as informações geradas pelos passos anteriores (sintomas, resultados da busca, plano de ações, avaliação de emergência e locais de ajuda médica) e as sintetiza em um **guia completo e acionável de primeiros socorros**. Sua saída é cuidadosamente formatada com **tópicos e subtópicos usando bullet points**, tornando a leitura intuitiva e as instruções fáceis de seguir. Este agente também pode sugerir links para vídeos explicativos para demonstrar técnicas.

---

## 🚀 Primeiros Passos: Configuração e Execução

Para rodar o AI Primeiros Socorros, você precisará de um ambiente Google Colab e configurar algumas chaves de API.

### Pré-requisitos:

* Conta Google para acessar o Google Colab e o Google Cloud Console.
* Conexão à internet.
* Chave de API do Google Gemini.
* Chave de API do Google Maps (para o serviço de Places e Directions).

### 1. Obtenha suas Chaves de API

* **Google Gemini API Key (`GOOGLE_API_KEY`):**
    * Acesse o [Google AI Studio](https://ai.google.dev/gemini-api/docs/get-started/web).
    * Siga as instruções para criar e copiar sua chave de API.
* **Google Maps API Key (`Maps_API`):**
    * Acesse o [Google Cloud Console](https://console.cloud.google.com/apis/credentials).
    * Crie um novo projeto ou selecione um existente.
    * Habilite as APIs **"Places API"** e **"Directions API"** para o seu projeto.
    * Crie uma chave de API e copie-a. Recomenda-se restringir a chave para uso apenas por suas aplicações (por exemplo, por domínio ou IP) para maior segurança.

### 2. Configure as Chaves de API no Google Colab

No seu notebook Google Colab, vá para o ícone de uma **chave/cadeado** (🔒) na barra lateral esquerda para abrir a aba "Secrets" (Segredos). Adicione suas chaves com os nomes exatos:

* **`GOOGLE_API_KEY`** (valor da sua chave Gemini)
* **`Maps_API`** (valor da sua chave do Google Maps)

Certifique-se de que a opção "Notebook access" (Acesso ao notebook) esteja ativada para ambas as chaves.

### 3. Instalação das Bibliotecas

Abra um novo notebook no [Google Colab](https://colab.research.google.com/) e execute a seguinte célula **separadamente**. Após a execução, o Colab pedirá para **reiniciar o ambiente de execução (runtime)**. **É crucial que você reinicie e espere o kernel estar pronto antes de prosseguir para a próxima etapa.**

```python
# CÉLULA 1: Instalação e Reinício do Ambiente
%pip -q install google-genai google-adk aiohttp
# Após a execução, o Colab irá reiniciar o kernel.
# ESPERE o Colab reiniciar ANTES de executar a próxima célula.

### 4. Execute o Código Principal
Após o kernel do Colab ter sido reiniciado e estar pronto, copie e cole todo o código (da seção de Configurações Iniciais até o final da função main()) em uma nova célula no seu notebook e execute-a.
