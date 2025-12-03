# 📄 Requisitos – Extração e Consolidação de Índices de Mercado


### **1. Regras de Seleção**
- O processo deve ser executado diariamente (ou conforme agenda definida).
- Todas as fontes cadastradas devem ser verificadas, respeitando a ordem de execução.
- Caso alguma fonte esteja indisponível, registrar exceção e seguir para a próxima.

### **2. Regras de Extração**
- Cada fonte deve ser acessada respeitando seu método de captura:
- Fonte de Mercado (A, B…)
- Fonte Governamental
- ERP Corporativo
- Fontes Internacionais
- Base de Indicadores
- Fonte Interna de Consolidação
- Os dados devem ser extraídos no formato disponível (API, planilha, tabela, site, etc.).
- É obrigatório validar se o retorno contém dados atualizados.

### **3. Regras de Consolidação**
- Todas as informações extraídas devem ser unificadas em um único modelo de consolidação.
- Campos obrigatórios devem ser mapeados antes da junção.
- Divergências devem ser sinalizadas para tratamento posterior.
- A consolidação só é finalizada após todas as fontes serem processadas.

### **4. Regras de Tratamento de Dados**
- Valores devem ser convertidos para o mesmo formato (decimal, padrão monetário e data).
- Datas e índices devem ser normalizados para um padrão comum.
- Em caso de ausência parcial de informações, registrar ocorrência sem interromper o fluxo.
- Dados duplicados devem ser evitados e dedup

### **5. Regras de Disponibilização**
- O consolidado final deve seguir o padrão obrigatório de nome e estrutura.
- A disponibilização deve ocorrer no local configurado (pasta, drive, repositório interno).
- Logs de execução devem ser registrados a cada processamento.

---

##  Validações Necessárias

- Validar acesso às fontes externas e internas.
- Validar disponibilidade e retorno de cada fonte.
- Verificar se os dados extraídos correspondem ao período correto.
- Validar integridade do consolidado (quantidade mínima de registros).
- Validar tipos de dados (numéricos, datas e strings).
- Conferir se todos os campos previstos foram preenchidos.
- Verificar se não há divergências entre fontes sensíveis.

---

##  Saídas Esperadas

- Arquivo final consolidado com índices de mercado.
- Logs de execução contendo:
- Fontes processadas
- Tempo de execução
- Ocorrências/exceções
- Status final da execução
- Dados tratados e padronizados para uso pelas áreas.
- Estrutura de histórico (se configurada) com versões anteriores do consolidado.

---

##  Critérios de Sucesso

- Todas as fontes processadas com sucesso.
- Consolidado gerado sem falhas estruturais.
- Dados atualizados e correspondentes ao período esperado.
- Execução dentro do tempo estimado.
- Registros consistentes entre todas as fontes integradas.
- Baixo índice de exceções recorrentes.
- Consolidação disponível na pasta/diretório previsto ao final do fluxo.
