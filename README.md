# EDA-E-commerce-Clickstream

![image](https://github.com/user-attachments/assets/0ef4c284-42d3-44db-8648-07ea22cbfc65)


## Resumo

Neste projeto, analisei uma base de dados  de uma captura interações de usuários em uma plataforma de comércio eletrônico. O conjunto de dados inclui uma variedade de eventos como visualizações de páginas, cliques, visualizações de produtos e compras. Cada registro está associado a uma sessão de usuário.

Iniciei com uma análise univariada de cada coluna, onde explorei as distribuições e características básicas dos dados. Em seguida, conduzi análises bivariadas para responder a perguntas específicas, investigando as relações entre diferentes variáveis. Essas análises ajudaram a identificar problemas para a área responsável pela captação dos dados resolver e também gerou insights para melhoria de negócio.

Os insights obtidos podem ser utilizados para melhorar estratégias de marketing e otimizar a experiência do usuário na plataforma, visando aumentar as taxas de conversão, retenção de clientes e faturamento.

**Acesse a EDA completa, a planilha utilizada e a base de dados nos arquivos deste repositório**

## Desenvolvimento

### Dataset

O dataset utilizado contém informações detalhadas sobre as interações dos usuários com a plataforma, incluindo os seguintes campos:
- **UserID**: Identificador único para cada usuário.
- **SessionID**: Identificador único para cada sessão.
- **Timestamp**: Data e hora da interação.
- **EventType**: Tipo de evento (visualização de página, clique, visualização de produto, adição ao carrinho, compra).
- **ProductID**: Identificador único dos produtos envolvidos nas interações.
- **Valor**: Valor da transação (aplicável em casos de compras).
- **Resultado**: Evento alvo (por exemplo, compra).

### Tratamento de Dados

Inicialmente, importei o dataset no Excel e, posteriormente, realizei o tratamento dos dados. Transformei a coluna `Timestamp` para extrair informações adicionais como `Day`, `Hour`, `WeekDay`, `Month` e `Year`, permitindo uma análise mais granular.

### Análise Univariada

Realizei uma análise univariada para inspecionar cada coluna individualmente:

#### UserID
- Identifiquei 1000 usuários únicos que realizaram 74817 ações no site.
- A análise das ações por usuário mostrou uma distribuição relativamente uniforme.

#### SessionID
- Identifiquei até 10 sessões distintas por usuário.
- A maior parte das ações foi realizada entre a sétima e nona sessão.

#### Timestamp
- A transformação da coluna `Timestamp` revelou inconsistências nas datas das ações dentro das mesmas sessões, sugerindo possíveis erros na captura de dados.

#### Day
- A maioria das ações ocorre no início e na metade do mês, com uma queda no final do mês.

#### Hour
- Identifiquei picos de atividade entre 00h e 8h e uma constância de ações entre 9h e 16h, com queda significativa após as 17h.

#### WeekDay
- A maioria das ações dos usuários ocorre entre segunda-feira e quinta-feira.

#### Month
- Observei pouca variação no número de ações por mês até julho, onde a base de dados foi capturada apenas até o dia 23.

#### EventType
- Identifiquei sete tipos de eventos, sendo 14,28% das ações resultantes em compras.

#### ProductID
- Há 8748 produtos diferentes na base de dados, com alguns produtos sendo mais frequentemente envolvidos em ações dos usuários.

#### Valor
- O valor das transações varia entre aproximadamente 5,13 e 500 unidades monetárias, com um ticket médio calculado.

### Perguntas de Negócio

1. **Comportamento de compras por dia da semana**
   - Os melhores dias de venda são segunda, terça e quinta, enquanto domingo, sexta e sábado têm menos vendas.

2. **Comportamento de compras por horário do dia**
   - Os horários com mais vendas são 3h, 7h, 9h, 11h, 16h e 19h.

3. **Comportamento de compras por mês**
   - Há pouca variação mensal nas vendas, com exceção de julho devido à coleta parcial de dados.

4. **Distribuição de vendas por usuário**
   - Todos os usuários na base realizaram compras, sugerindo um possível erro na captura dos dados.

5. **Produtos com maior valor médio de transação**
   - Os produtos com maior valor médio de transação têm valores próximos entre si, sem outliers.

6. **Produtos mais vendidos**
   - Identifiquei os produtos mais vendidos na plataforma.

7. **Preço dos produtos mais vendidos**
   - Analisei o valor unitário dos produtos mais vendidos.

8. **Comportamento do Faturamento a cada mês**
   - Verifiquei o comportamento do faturamento ao longo dos meses.

## Insights Obtidos

### Recomendações de Melhoria na Captação dos Dados

1. **Verificação de Inconsistência no UserID**
   - Verificar a consistência dos UserIDs, pois todos os usuários na base já realizaram compras, o que pode indicar um erro na captura dos dados.

2. **Sessões com Ações em Datas Distintas**
   - Revisar a captura do `SessionID`, pois encontrei ações da mesma sessão em datas muito distantes, sugerindo erros de registro ou falhas na definição de sessão.

### Insights de Negócios

1. **Dias da Semana para Promoções**
   - Focar campanhas de marketing e promoções nos dias com mais vendas: segunda, terça e quinta.

2. **Horários para Promoções**
   - Agendar promoções e campanhas de marketing para horários com mais vendas: 3h, 7h, 9h, 11h, 16h e 19h.

3. **Monitorar meses de baixo desempenho**
   - Analisar fevereiro para entender as razões do desempenho ligeiramente inferior e ajustar estratégias conforme necessário.

4. **Identificar e promover produtos populares**
   - Focar em campanhas para os produtos mais vendidos e de maior valor médio de transação.

5. **Análise da dsitribuição de ações ao longo do mês**
   - Desenvolver estratégias para aumentar as ações dos usuários nos últimos dias do mês, onde há uma queda significativa.

