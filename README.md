# Dashboard executivo Porsche

Dashboard comercial interativo criado como projeto de conclusão de curso, com publicação pelo GitHub Pages.

## Dashboard

- **Repositório:** https://github.com/Oberdan1984/dashboard-porsche-executivo
- **Dashboard publicado:** https://Oberdan1984.github.io/dashboard-porsche-executivo/

Os endereços acima serão substituídos pelos links finais após a criação e publicação do repositório.

## Perguntas de negócio

1. **Quais produtos e mercados geram a maior parte do faturamento?** O mix por modelo, a concentração de receita (Pareto), a receita por estado e o ticket médio ajudam a identificar os principais produtos e territórios.
2. **Quais vendedores apresentam a melhor performance?** Ranking de receita, relação entre receita e quantidade de veículos e ticket médio ajudam a comparar volume e valor por vendedor.
3. **Quanto da receita está efetivamente garantida?** Status de entrega, receita realizada e pipeline distinguem vendas entregues de vendas ainda em andamento; a série mensal mostra a evolução.

## Prompt e evolução

### Prompt inicial

> Utilize esse arquivo. Crie um arquivo HTML único (sem dependências locais) contendo um dashboard executivo premium inspirado no design da Porsche Brasil, usando HTML, CSS, JavaScript e Plotly.js em tema dark luxury e responsivo. Inclua filtros por estado, modelo, vendedor e status. Responda às três perguntas de negócio sobre produtos/mercados, performance dos vendedores e receita garantida. Inclua Pareto por modelo, receita por estado, ticket médio por modelo, ranking de faturamento, scatter receita × quantidade, ticket médio por vendedor, funil e receita por status, evolução mensal, seis KPIs (receita total, ticket médio, veículos vendidos, receita realizada, receita em pipeline e taxa de cancelamento) e cards de insights automáticos. Gere `dashboard_porsche_executivo.html`.

### Mudanças até a versão final

- Foi adicionada uma imagem panorâmica de um Panamera no cabeçalho. Esse modelo aparece com maior frequência na base (quatro registros); o tratamento visual usa imagem e sobreposição escura para manter a leitura do título.
- Os gráficos de ticket e de evolução mensal foram revistos após a observação de espaço visual pouco aproveitado. Os tickets usam pontos com valores e volume indicados; a evolução mensal usa colunas empilhadas para separar realizado e pipeline.
- A base completa foi mantida no HTML e disponibilizada em uma tabela recolhível, preservando os 76 registros que alimentam as análises.
- Foram adicionados filtros de data inicial e final, limitados ao intervalo disponível na base; os filtros existentes e a organização geral foram mantidos.

## Preparação da base

O arquivo de origem continha uma única planilha com **76 registros e 12 campos**, de março de 2024 a outubro de 2027. A planilha foi entregue à IA sem pré-tratamento. Durante a preparação, a estrutura e a completude foram verificadas; não havia valores vazios. As datas foram normalizadas para `AAAA-MM-DD` para habilitar filtro e agrupamento mensal, e os valores de venda foram tratados como números. A base também foi exportada como CSV UTF-8 em [`data/base_porsche_ficticia.csv`](data/base_porsche_ficticia.csv).

O usuário confirmou que os dados são fictícios. Por isso, os registros completos — incluindo nomes, vendedores e valores de venda — permanecem embutidos no HTML para que os gráficos e filtros possam ser reproduzidos. Não foi feita anonimização. A moeda não constava no arquivo; o dashboard apresenta valores como US$, inferência baseada nos valores e nas localidades dos Estados Unidos.

Os status são exibidos em português. `Delivered` é tratado como receita realizada; os demais status, exceto `Cancelled`, compõem o pipeline ativo. Cancelamentos são excluídos do ticket médio e do total de veículos vendidos. A receita total mantém o valor bruto de todos os registros, inclusive cancelados. A tabela integral preserva o conteúdo de origem, independentemente dos filtros.

## Ferramenta de IA

Foi usado o **Codex com a skill de planilhas** para inspecionar e interpretar a base, além de construir o HTML. O ChatGPT Canvas não foi usado; o arquivo foi editado diretamente no ambiente de trabalho do Codex. Plotly.js e as fontes são carregados por CDN, portanto o dashboard precisa de acesso à internet.

## Arquivos

- [`index.html`](index.html): dashboard completo, com dados incorporados.
- [`data/base_porsche_ficticia.csv`](data/base_porsche_ficticia.csv): cópia CSV da base fictícia, com datas normalizadas.
- `screenshots/dashboard.png`: captura do dashboard publicado.
- `screenshots/filtro-aplicado.png`: exemplo publicado com um filtro aplicado.

## Imagem

A foto do Panamera é carregada de um recurso da [Porsche Rocklin](https://rocklin.porsche.com/en/blog/new-2025-porsche-panamera-rocklin-ca-overview). A imagem, as fontes e o Plotly.js são externos; não há dependências locais.
