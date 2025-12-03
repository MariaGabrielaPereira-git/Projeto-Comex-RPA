# Projeto-Comex-RPA
Automação para extração e atualização diária de índices de mercado, com validação e preenchimento automático das planilhas consolidadas, gerando a base utilizada pelo BI.Este projeto implementa uma automação responsável por coletar, tratar e consolidar diariamente diversos índices de mercado provenientes de múltiplas fontes externas. O robô acessa sites, APIs e arquivos disponibilizados em diferentes formatos (Excel, CSV e PDF), realiza autenticação quando necessário e executa uma série de extrações estruturadas para alimentar planilhas internas padronizadas.

Após a coleta, os dados passam por validações que garantem integridade, correspondência entre índices e colunas, padronização de datas e preenchimento acumulativo sem sobrescrever informações históricas. O robô compara nomenclaturas, identifica valores mais recentes e registra as informações seguindo uma lógica sequencial (id_linha, data_consulta, índice_..., dt_publ), permitindo rastreabilidade total do processo.

O resultado final é uma base consolidada, completa e atualizada, utilizada pelo BI para geração de dashboards e análises gerenciais.
Esta automação reduz drasticamente o esforço manual, elimina erros de transcrição, padroniza informações oriundas de diferentes plataformas e assegura uma atualização diária confiável, mesmo em cenários onde há instabilidade nos portais ou mudanças de estrutura dos relatórios.

O processo também conta com mecanismos de tratamento de exceções, retentativas automáticas e notificações ao usuário em casos de falha, garantindo robustez e continuidade operacional.
