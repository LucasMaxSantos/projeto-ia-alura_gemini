# 🍜 Receita Inteligente com Gemini: Seu Chef Pessoal com IA

![Banner do Projeto](https://img.odcdn.com.br/wp-content/uploads/2024/08/inteligencia-artificial-alimentos-1920x1080.png)

## 🚀 Visão Geral do Projeto

Bem-vindo ao **Receita Inteligente com Gemini**! Este é um chatbot inovador desenvolvido durante a imersão de IA da Alura em parceria com o Google Gemini. Nosso objetivo é simplificar a sua vida na cozinha, ajudando você a encontrar receitas deliciosas usando **apenas** os ingredientes que você já tem em casa.

Cansado de olhar para a geladeira e não saber o que cozinhar? Com o Receita Inteligente, basta dizer o que você tem e nossa orquestração de agentes de IA fará o resto!

## ✨ Funcionalidades

* **Processamento Inteligente de Ingredientes:** Entende sua lista de ingredientes em texto livre e extrai nomes e quantidades.
* **Geração de Consultas Otimizadas:** Cria consultas de busca inteligentes para encontrar as melhores receitas no Google.
* **Busca de Receitas em Tempo Real:** Utiliza a ferramenta Google Search para encontrar receitas relevantes.
* **Validação Rigorosa de Ingredientes:** Filtra receitas para garantir que utilizem APENAS os ingredientes fornecidos (com exceção de itens básicos como sal, água, etc.).
* **Apresentação Clara e Formatada:** Exibe as receitas encontradas de forma legível, com ingredientes, modo de preparo e link original.
* **Estratégia de Busca Flexível:** Realiza múltiplas tentativas de busca, flexibilizando as consultas caso não encontre resultados na primeira rodada.

## ⚙️ Como Funciona? (A Orquestração Mágica por Trás)

Este projeto é um excelente exemplo de como a orquestração de múltiplos Agentes de IA pode resolver problemas complexos. Veja como nosso sistema trabalha nos bastidores:

1.  **Agente 1: Coleta e Processamento de Ingredientes**
    * Recebe a entrada do usuário (ex: "2 bananas, farinha de aveia, gotas de chocolate").
    * Normaliza os ingredientes (singular, minúsculas) e extrai quantidades.
    * Saída: Lista JSON de ingredientes processados.

2.  **Agente 2: Geração de Consulta**
    * Recebe os ingredientes processados.
    * Gera diversas consultas de busca para o Google, adaptando a flexibilidade da busca a cada tentativa (mais restritiva para menos restritiva).
    * Saída: Lista JSON de strings de consulta.

3.  **Agente 3: Buscador de Receitas**
    * Recebe as consultas geradas.
    * Utiliza a ferramenta `Google Search` para buscar receitas.
    * Extrai título, URL e um resumo detalhado da receita dos resultados.
    * Saída: Lista JSON de receitas encontradas.

4.  **Agente 4: Validador de Receitas**
    * Recebe os ingredientes originais do usuário e as receitas encontradas.
    * **Ponto Crucial:** Valida rigorosamente se cada receita utiliza *apenas* os ingredientes do usuário (ignorando básicos como sal, água, fermento).
    * Descarta receitas que contenham qualquer ingrediente significativo não fornecido.
    * Saída: Lista JSON das receitas validadas.

5.  **Agente 5: Apresentador de Receitas**
    * Recebe as receitas validadas.
    * Formata as informações de maneira amigável em Markdown para o usuário, destacando ingredientes, modo de preparo e o link original.
    * Saída: Texto Markdown exibido ao usuário.

## 🛠️ Tecnologias Utilizadas

* **Google Gemini API:** O coração da inteligência artificial, fornecendo os modelos para os agentes.
* **Google ADK (Agent Development Kit):** Framework para orquestração e construção dos agentes de IA.
* **Python:** Linguagem de programação principal.
* **Google Colab:** Ambiente de desenvolvimento para prototipagem rápida.
