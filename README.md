# Explorando Práticas de Teste

Neste exercício, vamos explorar práticas de teste em sistemas reais utilizando a ferramenta [TestMiner](https://andrehora.github.io/testminer).

O TestMiner permite visualizar e analisar testes de software em repositórios do GitHub, fornecendo dados sobre como os projetos organizam seus testes, como eles evoluem entre versões e quais bibliotecas de teste são utilizadas.
Explore a ferramenta antes de começar para se familiarizar com seu funcionamento.

Mais detalhes no GitHub da ferramenta: https://github.com/andrehora/testminer.

---

## Passo 1: Selecionar DOIS repositórios

Escolha dois repositórios reais que possuam testes de software.
Abaixo estão alguns links para ajudá-lo a encontrar projetos interessantes:

- Python: https://github.com/topics/python?l=python
- JavaScript: https://github.com/topics/javascript?l=javascript
- TypeScript: https://github.com/topics/typescript?l=typescript
- Java: https://github.com/topics/java?l=java

- Tópicos: [ai](https://andrehora.github.io/testminer/#topic:ai), [llm](https://andrehora.github.io/testminer/#topic:llm), [api](https://andrehora.github.io/testminer/#topic:api), [nodejs](https://andrehora.github.io/testminer/#topic:nodejs), [android](https://andrehora.github.io/testminer/#topic:android)

- Por organização: [Google](https://andrehora.github.io/testminer/#google), [Microsoft](https://andrehora.github.io/testminer/#microsoft), [Apple](https://andrehora.github.io/testminer/#apple), [Facebook](https://andrehora.github.io/testminer/#facebook), [Netflix](https://andrehora.github.io/testminer/#netflix), 
[GitHub](https://andrehora.github.io/testminer/#github), [Apache](https://andrehora.github.io/testminer/#apache), [HuggingFace](https://andrehora.github.io/testminer/#huggingface)

## Passo 2: Explorar os repositórios selecionados

Busque os repositórios escolhidos no [TestMiner](https://andrehora.github.io/testminer) e analise os dados de teste gerados pela ferramenta.

## Passo 3: Explicar as prática de teste

Para cada repositório, escolha uma prática ou dado de teste relevante e explique com suas próprias palavras.

---

## Instruções de entrega

1. Faça um `fork` deste repositório (saiba mais sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork. Pode adicionar imagens para enriquecer sua explicação.
3. No Moodle, submeta apenas a URL do seu fork.

---

## Respostas

### Repositório 1 

Repositório: https://github.com/nodejs/node

URL TestMiner: https://andrehora.github.io/testminer/#nodejs/node

Explicação: A organização dos testes do Node.js é uma prática relevante. O TestMiner mostra um projeto muito grande, com 23.108 arquivos de código, 8.439 testes, 14.418 test helpers e 5.183 fixtures. Isso significa que, além dos casos de teste, o projeto investe bastante em código auxiliar e dados reutilizáveis para preparar cenários de forma consistente. Também aparecem 807 benchmarks, indicando preocupação com desempenho, enquanto os 17 testes E2E verificam alguns fluxos completos. A ferramenta ainda identifica 179 snapshots, 56 mocks, 9 testes de CI e 3 smoke tests, mostrando que a suíte combina diferentes estratégias de validação.

Outro dado importante é a evolução histórica: o gráfico do TestMiner mostra o crescimento de aproximadamente 3 mil testes na versão 9.7 para mais de 8 mil na versão 26.11.1. Esse aumento revela que a suíte acompanha a expansão do Node.js e funciona como parte contínua da manutenção do projeto. No TestMiner, também é possível observar a concentração dos testes em temas como `http` (529), `unit` (497), `stream` (446), `http2` (322) e `process` (295). Portanto, os números não mostram apenas quantidade: eles indicam cobertura de áreas centrais do runtime, preocupação com regressões e separação entre testes funcionais, desempenho e integração.

![Histórico de testes do Node.js](images/img1node)

![Resumo dos testes e dependências do Node.js](images/img2node)

As imagens mostram que os testes crescem à medida que o projeto cresce. O gráfico mostra que a quantidade de testes passa de aproximadamente 3 mil na versão 9.7 para mais de 8 mil na versão 26.11.1. Isso mostra que o Node.js continua adicionando testes para acompanhar as novas funcionalidades e evitar regressões. Também é possível observar que o TestMiner não detectou dependências externas de teste nesse repositório, o que indica que os testes identificados não dependem de bibliotecas externas listadas pela ferramenta.

### Repositório 2

Repositório: https://github.com/microsoft/vscode

URL TestMiner: https://andrehora.github.io/testminer/#microsoft/vscode

Explicação: O dado mais relevante é a diversidade de níveis de teste. Na consulta ao TestMiner, o VS Code aparece com 12.266 arquivos de código, 3.799 testes, 917 test helpers e 1.284 fixtures. Também aparecem 776 testes E2E, 404 snapshots, 52 mocks, 8 testes de CI e 78 smoke tests. Isso indica uma estratégia em camadas: testes menores verificam unidades e serviços; mocks e fixtures isolam dependências; snapshots ajudam a detectar alterações de saída; E2E verifica fluxos completos; e smoke tests dão uma validação rápida das funções mais importantes. O uso combinado dessas técnicas reduz o risco de depender somente de um tipo de teste.

Outro dado importante é a evolução histórica: o gráfico do TestMiner mostra que a quantidade de testes cresce junto com o projeto, passando de praticamente zero para aproximadamente 800 na versão 1.65.1 e chegando a mais de 3.700 na versão 1.141.0. Isso mostra que o VS Code continua adicionando testes à medida que novas funcionalidades são desenvolvidas, ajudando a evitar regressões. Diferente do Node.js, o VS Code possui dependências externas de teste identificadas pelo TestMiner. Entre elas aparecem dependências Maven, como `junit-jupiter-api` e `junit-jupiter-engine`, e várias dependências npm, como Mocha, Jest, Vitest, Sinon e Playwright. Essas bibliotecas são usadas para executar testes, criar mocks, verificar cobertura e testar fluxos completos. Como ponto de atenção, manter tantas categorias e dependências exige organização e manutenção para evitar duplicação e testes frágeis.

![Histórico de testes do VS Code](images/img1vscode)

![Resumo dos testes e dependências do VS Code](images/img2vscode)
