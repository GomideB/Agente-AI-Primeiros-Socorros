# 🤖 AI - Primeiros Socorros: Seu Agente para Emergências de Saúde

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-AI-green?style=for-the-badge&logo=google)
![Google Maps API](https://img.shields.io/badge/Google%20Maps-API-red?style=for-the-badge&logo=googlemaps)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow?style=for-the-badge&logo=googlecolab)

---

## 🚑 O Problema: Emergências de Saúde e a Necessidade de Orientação Imediata

Em momentos de emergência de saúde, seja uma dor súbita no peito, um ferimento inesperado ou um mal-estar agudo, o pânico pode tomar conta. A falta de conhecimento imediato sobre os primeiros socorros adequados pode agravar a situação, e a busca por informações online muitas vezes resulta em dados dispersos, não confiáveis ou difíceis de interpretar sob pressão. Quando cada segundo conta, ter acesso a orientações claras, precisas e personalizadas é crucial, mas nem sempre uma ambulância ou um médico está disponível no exato momento.

---

## ✨ A Solução: Um Agente de IA para Primeiros Socorros

Apresentamos o **AI First Aid Assistant**, um sistema inteligente construído com o poder do **Google Gemini (via Google Agent Development Kit - ADK)** e a precisão do **Google Maps API**. Este projeto visa preencher a lacuna de informação em momentos críticos, oferecendo um guia interativo de primeiros socorros que não só orienta sobre como proceder, mas também avalia a gravidade da situação e localiza ajuda médica próxima.

Imagine ter um assistente pessoal que, ao descrever o que sente, pode:
* Realizar uma **triagem inicial** dos sintomas.
* **Consolidar informações** para um quadro completo.
* Buscar **orientações confiáveis** de primeiros socorros em tempo real.
* **Avaliar a urgência** da situação, recomendando ligar para o SAMU (192) se for uma emergência vital.
* **Localizar hospitais e clínicas** nas proximidades.
* Gerar **rotas diretas no Google Maps** para os locais de atendimento mais relevantes.

Este agente não substitui o atendimento médico profissional, mas serve como uma ferramenta de **orientação imediata** que pode salvar vidas ou minimizar danos até a chegada da ajuda especializada, transformando o pânico em ação informada.

---

## 🛠️ Como Funciona: A Orquestração de Agentes Inteligentes

O AI First Aid Assistant opera através de uma arquitetura modular, onde diferentes **Agentes de IA**, cada um com uma especialidade, colaboram sob a orquestração de uma função principal. Isso garante uma resposta estruturada, precisa e abrangente, passo a passo:

### Visão Geral da Arquitetura:

1.  **Coleta Inicial de Sintomas:** O usuário descreve o que sente.
2.  **Expansão e Consolidação:** O sistema faz perguntas adicionais para obter um quadro completo.
3.  **Busca de Informações:** Utiliza a web (Google Search) para encontrar guias de primeiros socorros.
4.  **Planejamento de Ações:** Formula um plano de ação claro.
5.  **Avaliação de Emergência:** Determina a gravidade da situação e a necessidade de acionar serviços de emergência.
6.  **Localização de Ajuda Médica:** Busca hospitais e médicos próximos.
7.  **Geração de Rotas:** Oferece links para rotas no Google Maps.
8.  **Orientação Final Detalhada:** Compila todas as informações em um guia prático para o usuário.

### Os Agentes em Ação:

* **`agente_triagem`**: Inicia a conversa, coletando a descrição inicial dos sintomas.
* **`agente_coleta_sintomas_adicionais`**: Consolida os sintomas iniciais e informações adicionais do usuário em uma descrição completa e coesa.
* **`agente_busca_primeiros_socorros`**: Especialista em pesquisa, utiliza a ferramenta `Google Search` para encontrar as melhores práticas e orientações de primeiros socorros para a condição descrita, focando em fontes confiáveis.
* **`agente_planejamento_acoes`**: Analisa os resultados da busca e elabora um plano de ação conciso e priorizado para o usuário.
* **`agente_avaliacao_emergencia`**: Avalia a gravidade da situação com base nos sintomas e no plano, instruindo o usuário a ligar para o SAMU (192) se for uma emergência grave, ou a procurar atendimento médico se for menos urgente.
* **`agente_localizacao_ajuda_medica`**: Racicína sobre a necessidade de ajuda médica e sinaliza a busca por hospitais e médicos próximos, que é executada por funções auxiliares da API do Google Maps.
* **`agente_rota_navegacao`**: Raciocina sobre a necessidade de rotas e sinaliza a geração de links para navegação, também executada por funções auxiliares do Google Maps.
* **`agente_orientacao_detalhada`**: O agente final, que compila todas as informações geradas pelos passos anteriores (sintomas, busca, plano, avaliação de emergência, locais encontrados) e as sintetiza em um guia claro e acionável de primeiros socorros para o usuário. Pode até sugerir links para vídeos explicativos.

---

## 🚀 Primeiros Passos: Configuração e Execução

Para rodar o AI First Aid Assistant, você precisará de um ambiente Google Colab e configurar algumas chaves de API.

### Pré-requisitos:

* Conta Google para acessar o Google Colab e o Google Cloud Console.
* Conexão à internet.

### 1. Instalação das Bibliotecas

Abra um novo notebook no [Google Colab](https://colab.research.google.com/) e execute a seguinte célula **separadamente**. Após a execução, o Colab pedirá para **reiniciar o ambiente de execução (runtime)**. **É crucial que você reinicie e espere o kernel estar pronto antes de prosseguir para a próxima etapa.**

```python
# CÉLULA 1: Instalação e Reinício do Ambiente
%pip -q install google-genai google-adk aiohttp
# Após a execução, o Colab irá reiniciar o kernel.
# ESPERE o Colab reiniciar ANTES de executar a próxima célula.
