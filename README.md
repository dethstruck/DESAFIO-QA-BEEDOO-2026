# Desafio QA Beedoo - 2026 🐝

Repositório destinado à entrega do desafio técnico para a vaga de Qualidade (QA) da Beedoo. O objetivo deste projeto é analisar, planejar e executar testes no módulo de cadastro e listagem de cursos de uma aplicação web.

---

## 🔍 1. Análise Inicial da Aplicação

Durante a fase de exploração da aplicação (hospedada no Netlify), realizei um mapeamento mental e técnico para entender o comportamento do sistema e definir a melhor estratégia de qualidade.

### Objetivo da aplicação
A aplicação tem como objetivo principal atuar como um catálogo ou painel administrativo para o gerenciamento de cursos. Ela permite que usuários (provavelmente administradores ou produtores de conteúdo) insiram novos conteúdos educacionais na base de dados e visualizem o portfólio de cursos já disponíveis de forma rápida e centralizada.

### Principais fluxos disponíveis
Focando no escopo do desafio, mapeei os seguintes fluxos essenciais:
1. **Fluxo de Cadastro (Create):** Preenchimento de formulário com dados do curso (título, descrição, carga horária, etc.) e submissão para persistência.
2. **Fluxo de Listagem (Read):** Carregamento e renderização em tela dos cursos previamente cadastrados, exibindo as informações em formato de *cards* ou tabela.

### Pontos críticos para teste
Com base na arquitetura de aplicações web (Front-end consumindo uma API), considero os seguintes pontos como os mais críticos e suscetíveis a falhas:
* **Validações de Fronteira no Formulário:** Campos numéricos aceitando letras/valores negativos, ou campos de texto sem limite de caracteres, o que pode corromper a base de dados ou quebrar o layout da listagem.
* **Comportamento Assíncrono e Estado de UI:** Como a interface reage durante o tempo de resposta da API (ex: falta de *loading*, permitindo que o usuário clique várias vezes em "Salvar" e crie cursos duplicados).
* **Tratamento de Exceções:** O que acontece na listagem se a aplicação não conseguir se comunicar com o servidor (falha de rede ou API fora do ar). O usuário recebe um feedback amigável?

---

## 🧠 2. Explicação do Raciocínio e Decisões Tomadas

### Raciocínio durante a análise
Minha linha de raciocínio foi baseada em **Shift-Left Testing** e **Análise Heurística**. Em vez de olhar apenas para o "caminho feliz" (onde o usuário faz tudo certo), foquei em como a aplicação se defende de comportamentos inesperados. 
Sendo estudante de Análise e Desenvolvimento de Sistemas, sei que o Front-end e o Back-end precisam ter contratos bem definidos. Portanto, meu raciocínio foi tentar quebrar esse contrato: enviar dados nulos, forçar tipos de dados incorretos e testar os limites da interface gráfica.

### Decisões tomadas para a criação dos testes
1. **Modelagem de Cenários:** Optei por cobrir 4 pilares: Fluxo Principal, Cenários Negativos (exceções e erros), Validações de Campos (limites e obrigatoriedades) e Fluxos Alternativos.
2. **Formato de Escrita:** Utilizei o formato passo a passo estruturado e BDD/Gherkin (Dado, Quando, Então) para garantir que qualquer pessoa (técnica ou de negócios) consiga ler, entender e reproduzir o teste sem ambiguidades.
3. **Foco no Usuário vs. Foco Técnico:** Cada bug reportado foi pensado não apenas na falha do código, mas no impacto da severidade para a experiência do usuário final.

---

## 📂 3. Artefatos de Teste e Entregáveis

Todo o planejamento, execução e registro de inconformidades foram documentados e organizados nos links abaixo:

* 📊 **[Planilha de Cenários, Casos de Teste e Report de Bugs]** *(Clique aqui para acessar o Google Sheets com a modelagem completa)* -> `[https://docs.google.com/spreadsheets/d/1aoznC5q4D-yxufB6gl04Rkg3Qf_jcVyV-xv-lFBtlEA/edit?usp=sharing]`

* 📁 **[Evidências de Execução]** *(Clique aqui para acessar a pasta no Google Drive contendo os prints e gravações dos testes executados e dos bugs encontrados)* -> `[https://drive.google.com/drive/folders/1jPSFx4ajq80W9j9bA4kTBjTTLd0MvbMw?usp=sharing]`

---
*Desenvolvido com foco em Qualidade, Resiliência e Experiência do Usuário.*
