# 📄 Mapeamento de Processo –  Extração e Consolidação de Índices de Mercado

---
## Fluxograma - Visão Macro do Processo

<img width="1663" height="526" alt="image" src="https://github.com/user-attachments/assets/5b848edd-0671-4d93-ae0a-327b65c31e07" />

---

## 1. Descrição Geral do Processo
O processo consiste na extração automática de índices de mercado a partir de múltiplas plataformas online e arquivos estruturados. Após a coleta, o robô consolida os dados em planilhas padronizadas, garantindo atualização diária para alimentar análises internas e dashboards gerenciais.

Este fluxo substitui a atividade manual repetitiva de acessar plataformas diversas, baixar relatórios, extrair indicadores e preencher arquivos acumulativos.

---

## 2. Fluxo TO BE – Visão Geral
1. Acessar plataformas externas para download de indicadores (financeiros, industriais e de mercado).
2. Realizar login automático (quando necessário).
3. Extrair relatórios em Excel, CSV ou PDF.
4. Capturar os índices relevantes de cada fonte.
5. Abrir planilhas internas padronizadas do diretório consolidado.
6. Preencher dados em sequência acumulativa, mantendo histórico.
7. Validar correspondência entre índices extraídos e colunas de destino.
8. Preencher colunas:
   - `id_linha`
   - `data_consulta`
   - `índice_...`
   - `dt_publ`
9. Ajustar formatação de datas e valores.
10. Salvar e manter versionamento diário das planilhas.
11. Notificar o usuário em caso de erro ou inconsistência.

---

## 3. Melhorias Implementadas
- **Padronização dos fluxos**: todos os sistemas externos seguem a mesma lógica de tentativa, extração e validação.
- **Tratamento de erros com retentativas automáticas** (até 3 vezes).
- **Comparação automática de índices**, evitando preenchimento incorreto.
- **Preenchimento acumulativo diário**, reduzindo retrabalho e eliminando risco de sobrescrita de dados.
- **Validação inteligente**: o robô identifica índices idênticos e preenche apenas quando houver correspondência.
- **Automação do formato de data**, garantindo unicidade e padronização no histórico.
- **Notificações automáticas ao usuário em caso de falhas críticas**.
- **Integração com múltiplas fontes de forma unificada**, reduzindo tempo e esforço humano.

---

## 4. Pontos de Atenção / Exceções
- Caso uma plataforma não carregue, o robô realiza até **3 tentativas** antes de seguir para a próxima.
- Se o relatório do dia for igual ao do dia anterior (ex.: relatórios semanais), o robô **não baixa novamente**, usando dados prévios.
- Diferentes plataformas podem mudar a estrutura — o robô deve validar colunas antes de preencher.
- Sites que exigem autenticação podem falhar; nesses casos o robô notifica o usuário.
- Planilhas internas são acumulativas — qualquer quebra de padrão pode interromper o preenchimento sequencial.
- Diferenciar datas nos formatos AAAA/MM/DD X DD/MM/AAAA para evitar inconsistências.
- Índices devem sempre ser preenchidos com **vírgula** como separador decimal.

---

## 5. KPI – Indicadores Sugeridos
| Indicador | Descrição | Meta |
|----------|-----------|------|
| Tempo médio por execução | Tempo total da automação até consolidar todas as planilhas | ≤ 30 min |
| Taxa de sucesso na extração | Percentual de plataformas acessadas com sucesso | ≥ 95% |
| Redução de esforço manual | Horas economizadas do time por mês | ≥ 40h/mês |
| Índices atualizados corretamente | Correspondência entre índice buscado e índice preenchido | 100% |
| Volume diário processado | Quantidade de planilhas e índices atualizados | 100% do escopo diário |

---

## 6. Observações Gerais
- As planilhas internas possuem preenchimento acumulativo — nunca apagar dados anteriores.
- A correspondência entre índices e colunas exige atenção à nomenclatura (ex.: diferenciação entre “HR Coil”, “Rebar”, etc.).
- O robô deve sempre priorizar o último dado disponibilizado na data da publicação.
- A automação cobre diversas fontes com formatos variados; ajustes futuros podem ser necessários caso padrões externos mudem.

