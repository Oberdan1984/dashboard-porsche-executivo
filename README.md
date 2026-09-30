# Dashboard executivo Porsche

Dashboard comercial interativo criado como projeto de conclusão de curso, publicado pelo GitHub Pages.

## Dashboard

- **Repositório:** https://github.com/Oberdan1984/dashboard-porsche-executivo
- **Dashboard publicado:** https://Oberdan1984.github.io/dashboard-porsche-executivo/

## Perguntas de negócio

1. **Quais produtos e mercados geram a maior parte do faturamento?** O mix por modelo, a concentração de receita (Pareto), a receita por estado e o ticket médio ajudam a identificar os principais produtos e territórios.
2. **Quais vendedores apresentam a melhor performance?** Ranking de receita, relação entre receita e quantidade de veículos e ticket médio ajudam a comparar volume e valor por vendedor.
3. **Quanto da receita está efetivamente garantida?** Status de entrega, receita realizada e pipeline distinguem vendas entregues de vendas ainda em andamento; a série mensal mostra a evolução.

Essas perguntas foram escolhidas para resumir as decisões centrais de uma operação comercial: onde concentrar o esforço de produto e mercado, como comparar desempenho da equipe e quanto da carteira já se converteu em entrega.

## Prompt e evolução

### Prompt inicial

> Utilize esse arquivo. Crie um arquivo HTML único (sem dependências locais) contendo um dashboard executivo premium inspirado no design da Porsche Brasil, usando HTML, CSS, JavaScript e Plotly.js em tema dark luxury e responsivo. Inclua filtros por estado, modelo, vendedor e status. Responda às três perguntas de negócio sobre produtos/mercados, performance dos vendedores e receita garantida. Inclua Pareto por modelo, receita por estado, ticket médio por modelo, ranking de faturamento, scatter receita × quantidade, ticket médio por vendedor, funil e receita por status, evolução mensal, seis KPIs (receita total, ticket médio, veículos vendidos, receita realizada, receita em pipeline e taxa de cancelamento) e cards de insights automáticos. Gere `dashboard_porsche_executivo.html`.

### Mudanças até a versão final

- Foi adicionada uma imagem panorâmica de um Panamera no cabeçalho, com sobreposição escura para preservar o contraste do título.
- Os gráficos de ticket e de evolução mensal foram revistos para usar melhor o espaço visual: os tickets usam pontos com valores e volume indicados; a evolução mensal usa colunas empilhadas para separar realizado e pipeline.
- A base completa foi mantida no HTML e disponibilizada em uma tabela recolhível, preservando os 76 registros que alimentam as análises.
- Foram adicionados filtros de data inicial e final, limitados ao intervalo disponível na base; os filtros existentes e a organização geral foram mantidos.

## Preparação da base

O arquivo de origem continha uma única planilha com **76 registros e 12 campos**, de março de 2024 a outubro de 2027. A planilha foi entregue à IA sem pré-tratamento. Durante a preparação, a estrutura e a completude foram verificadas; não havia valores vazios. As datas foram normalizadas para `AAAA-MM-DD` para habilitar filtro e agrupamento mensal, e os valores de venda foram tratados como números. A base também foi exportada como CSV UTF-8 em [`base_porsche_ficticia.csv`](base_porsche_ficticia.csv).

O usuário confirmou que os dados são fictícios. Por isso, os registros completos — incluindo nomes, vendedores e valores de venda — permanecem embutidos no HTML para que os gráficos e filtros possam ser reproduzidos. Não foi feita anonimização. A moeda não constava no arquivo; o dashboard apresenta valores como US$, inferência baseada nos valores e nas localidades dos Estados Unidos.

Os status são exibidos em português. `Delivered` é tratado como receita realizada; os demais status, exceto `Cancelled`, compõem o pipeline ativo. Cancelamentos são excluídos do ticket médio e do total de veículos vendidos. A receita total mantém o valor bruto de todos os registros, inclusive cancelados. A tabela integral preserva o conteúdo de origem, independentemente dos filtros.

## Ferramenta de IA

Foi usado o **Codex com a skill de planilhas** para inspecionar e interpretar a base, além de construir o HTML. O ChatGPT Canvas não foi usado; o arquivo foi editado diretamente no ambiente de trabalho do Codex. Plotly.js e as fontes são carregados por CDN, portanto o dashboard precisa de acesso à internet.

## Arquivos

- [`index.html`](index.html): dashboard completo, com dados incorporados.
- [`base_porsche_ficticia.csv`](base_porsche_ficticia.csv): cópia CSV da base fictícia, com datas normalizadas.

## Imagem

A foto do Panamera é carregada de um recurso da [Porsche Rocklin](https://rocklin.porsche.com/en/blog/new-2025-porsche-panamera-rocklin-ca-overview). A imagem, as fontes e o Plotly.js são externos; não há dependências locais.


## Evidências visuais

As capturas abaixo mostram a dashboard publicada e os resultados depois de aplicar Estado = CA e período iniciado em 2025-01-01.

### Dashboard e filtros disponíveis

![Dashboard publicada com filtros por estado, modelo, vendedor, status e período](https://github.com/user-attachments/assets/95009bc1-66ca-4f93-a03d-e44de3f50747)

### Resultado do filtro aplicado

![KPIs e gráficos atualizados com o filtro Estado = CA e período iniciado em 2025-01-01](https://github.com/user-attachments/assets/47e65e48-3c22-45eb-bd41-574a98ec5fc1)
