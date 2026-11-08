# Painel de Evidências

Uma ferramenta pessoal, feita em HTML, CSS e JavaScript puros, para transformar o que eu faço (estágios, projetos, estudos) em **evidências que outra pessoa consegue avaliar**. Ela me ajuda a organizar a busca por uma vaga de **Engenharia de Software (backend, Java)** e a reduzir a incerteza que uma empresa tem sobre mim.

Não precisa de servidor, instalação nem conta: é um único arquivo que roda no navegador.

## Por que criei isso

Uma pessoa recrutadora ou um time técnico decide com informação incompleta. Meu objetivo é diminuir essa incógnita com material concreto:

- **Histórias reais** de trabalho em equipe, resolução de problemas e comunicação, em vez de adjetivos no currículo.
- **Projetos explicados por decisões**, não só por código. O repositório mostra o que eu fiz, e a conversa mostra como eu penso.
- **Um processo visível**: compartilhar o que estou construindo e aprendendo, com constância e sem texto genérico.
- **Rede de relacionamentos**, não uma lista de conexões.

## O que tem em cada aba

| Aba | Para que serve |
|---|---|
| **Painel** | Contagem de dias até a meta, checklist semanal, meta mensal de post, cobertura das competências, próximas ações sugeridas e os principais lembretes. |
| **Lembretes** | Alertas calculados a partir dos meus registros (diário parado, post do mês, contatos esquecidos, vagas sem retorno, checklist e backup). Cada um pode ser adiado por 3 dias. |
| **Evidências** | Histórias no formato STAR (Situação, Tarefa, Ação, Resultado) com aprendizado e competências provadas. Filtro por competência. |
| **Projetos** | Problema que resolve, decisões técnicas e trade-offs, o que o projeto mostra sobre mim e um pitch de 30 segundos. Permite marcar projetos sob sigilo. |
| **Diário e posts** | Registro do que fiz, onde travei e o que aprendi. Gera um rascunho de post a partir da entrada (meta: 1 post por mês). |
| **Rede** | Contatos com contexto, o que já troquei com cada pessoa, próximo gesto e alerta de mais de 30 dias sem contato. |
| **Vagas** | Quadro por etapa, com arrastar e soltar, e anotação dos requisitos que ainda não consigo evidenciar. |
| **Entrevista** | Banco de perguntas comportamentais e técnicas (Java/backend), com esqueleto de resposta e marcação de treino em voz alta. |
| **Evolução** | Gráfico de atividade dos últimos 6 meses (evidências, diário, posts, contatos e candidaturas) e gráfico de adesão ao checklist nas últimas 8 semanas. |

### Ideias que guiam o design

- **Cobertura de competências**: o painel mostra quantas evidências completas existem para cada competência e aponta lacunas.
- **Sigilo por padrão**: evidências, projetos e entradas de diário podem ser marcados como sigilosos. O gerador de posts avisa para generalizar antes de publicar.
- **Qualidade acima de frequência**: um post por mês, escolhido entre as melhores entradas do diário.
- **Constância visível**: os gráficos de evolução mostram o ritmo ao longo do tempo, que importa mais do que um pico isolado.

## Lembretes

Os lembretes são gerados automaticamente a partir dos dados:

- diário sem registro há 4 dias ou mais;
- nenhuma evidência nova há 14 dias, ou evidências com menos de 3 campos STAR preenchidos;
- post do mês ainda não publicado (aviso a partir do dia 10 e prioridade alta a partir do dia 20);
- contatos há mais de 30 dias sem interação;
- vagas aplicadas, em triagem ou em entrevista paradas há 7 dias ou mais;
- checklist semanal incompleto, de sexta a domingo;
- backup com mais de 14 dias.

Também é possível ativar **avisos do navegador** (no máximo um por dia). Eles só aparecem quando a página é aberta, porque ela não roda em segundo plano. Podem não funcionar abrindo o arquivo direto do computador e costumam funcionar quando a página é servida por https, como no GitHub Pages.

## Como usar

1. Baixe o arquivo `index.html` (ou clone o repositório).
2. Abra no navegador com duplo clique.
3. Comece pela aba **Evidências** e escreva a primeira história.

Para publicar como página, ative o **GitHub Pages** nas configurações do repositório (Settings → Pages) apontando para a branch principal.

## Dados e privacidade

- Tudo é salvo no `localStorage` do navegador. **Nenhum dado é enviado para servidor.**
- Os dados ficam no navegador e no dispositivo em que o arquivo foi aberto. Limpar os dados do site apaga tudo.
- Use **Painel → Exportar backup** para gerar um `.json` e **Importar backup** para restaurar ou levar para outro dispositivo.
- Se a página for publicada no GitHub Pages, os dados continuam sendo de quem a abre: cada pessoa vê só o que registrou no próprio navegador.
- Não suba seu backup para um repositório público: ele contém suas anotações pessoais.

## Tecnologias

- HTML, CSS e JavaScript (sem frameworks e sem dependências)
- `localStorage` para persistência
- Gráficos em SVG gerados no próprio código
- Tema em roxo e branco

## Estrutura

```
.
├── index.html   # aplicação completa (HTML + CSS + JS)
└── README.md
```

## Próximos passos

- [ ] Exportar evidências selecionadas para um documento de preparação de entrevista
- [ ] Lembretes configuráveis (definir os prazos de cada alerta)
- [ ] Testes automatizados para as regras de cobertura, lembretes e cadência de posts
- [ ] Capturas de tela neste README

## Licença

Defina a licença do repositório (por exemplo, MIT) antes de publicar, ou remova esta seção se preferir deixá-lo sem licença.
