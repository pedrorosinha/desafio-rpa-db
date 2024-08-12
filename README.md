# Projeto de Automação RPA: Relatório de Faturas

## Link Documento inicial:
[Documento do Desafio](https://drive.google.com/file/d/1m7XB7dX8JSZKjDDtoQ8txG_a5_ZP0Xwr/view?usp=sharing)
## Descrição

Este projeto utiliza UiPath para automatizar o processo de recepção de e-mails contendo faturas em PDF, extração de informações relevantes dos PDFs, preenchimento de um formulário online, geração de relatórios em Excel, e envio desses relatórios por e-mail.

## Funcionalidades

1. **Recepção de E-mails**: O robô busca por e-mails não lidos com o assunto "Nova Fatura" e baixa os PDFs anexados.
2. **Extração de Dados**: Os dados de cada fatura, como nome do fornecedor, data da fatura, valor total e data de lançamento, são extraídos usando expressões regulares.
3. **Armazenamento na Fila**: As informações extraídas são adicionadas a uma fila para processamento posterior.
4. **Preenchimento de Formulário**: Os dados armazenados na fila são usados para preencher um formulário online.
5. **Geração de Relatórios**: São gerados três relatórios em Excel, um para cada fornecedor, com um resumo das faturas processadas.
6. **Envio de Relatórios por E-mail**: Os relatórios gerados são enviados por e-mail com o assunto "Relatório de Faturas - [Mês/Ano]".

## Estrutura do Projeto

- **Main.xaml**: O fluxo principal que coordena as atividades do robô.
- **Coletor.xaml**: Contém a lógica para recepção de e-mails, download dos PDFs, e extração de dados.
- **Processo.xaml**: Responsável pelo preenchimento do formulário online e geração dos relatórios.
- **Queue Management**: Gerencia os itens na fila, processando apenas aqueles que foram tratados com sucesso.

## Pré-requisitos

- UiPath Studio instalado
- Acesso ao e-mail utilizado para receber as faturas
- Acesso ao formulário online
- Permissões para salvar arquivos no caminho especificado para os relatórios

## Configuração

1. **Configuração do E-mail**:
   - Insira as credenciais e configurações de e-mail na atividade `Use Gmail`.

2. **Configuração das Pastas**:
   - **Pasta de Invoices**: `C:\Users\pedro.rosinha\OneDrive - DBserver Assessoria em Sistemas de Informação Ltda\Documentos\UiPath\desafio-rpa-db\bot\Invoices`
   - **Pasta de Relatórios**: `C:\Users\pedro.rosinha\OneDrive - DBserver Assessoria em Sistemas de Informação Ltda\Documentos\UiPath\desafio-rpa-db\bot\Relatorios`

3. **Definição dos Campos do Formulário**:
   - Configure as variáveis necessárias para mapear os campos do formulário com as informações extraídas dos PDFs.

## Execução
1. **principal.xaml**: - Executa todo o processo.

## Notas

- Certifique-se de que os caminhos de arquivo e nomes não excedam os limites de caracteres suportados pelo sistema.
- O robô ignora registros que falharam ao processar as informações e só envia os relatórios dos registros que foram processados com sucesso.

## Fotos do projeto
![](https://github.com/user-attachments/assets/6b90c581-bcab-4ae9-97df-9fac4213e377)
![](https://github.com/user-attachments/assets/9b9eebc2-0024-43d0-9676-99fbf4a5beb8)
