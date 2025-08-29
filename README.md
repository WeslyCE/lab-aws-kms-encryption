# Laboratório: Criptografia de Arquivos com AWS KMS e Encryption CLI

Este repositório documenta a execução de um laboratório prático sobre criptografia de dados em repouso (data-at-rest) utilizando serviços da AWS. O objetivo foi proteger arquivos em uma instância EC2 usando uma chave de criptografia gerenciada pelo AWS Key Management Service (KMS).

## Visão Geral

O projeto demonstra o ciclo completo de criptografia e decriptografia de arquivos no lado do cliente, utilizando a interface de linha de comando `aws-encryption-cli`. Este processo garante que os dados sensíveis permaneçam ilegíveis, mesmo que o armazenamento seja comprometido.

## Ferramentas e Serviços Utilizados

* **AWS EC2 (Elastic Compute Cloud):** Como o servidor de arquivos onde os dados residem.
* **AWS KMS (Key Management Service):** Para criar e gerenciar a chave de criptografia.
* **AWS Encryption CLI:** A ferramenta utilizada para executar as operações de criptografia e decriptografia.
* **AWS IAM:** Para fornecer as permissões necessárias à instância EC2.

## Passo a Passo do Laboratório

### 1. Criação da Chave Criptográfica (AWS KMS)
O primeiro passo foi criar uma chave de criptografia simétrica no AWS KMS. Esta chave é o elemento central que protege os dados.

![Print da Chave KMS Criada no Console AWS](caminho/para/seu/print-1.png)

### 2. Configuração do Ambiente no EC2
Conectei-me à instância EC2 via Session Manager e instalei a AWS Encryption CLI, preparando o servidor para as operações.

![Print da Instalação da CLI](caminho/para/seu/print-2.png)

### 3. Criação dos Arquivos de Teste (Plain Text)
Foram criados arquivos de texto simples para simular os dados que precisavam de proteção.

![Print do Conteúdo dos Arquivos Originais](caminho/para/seu/print-3.png)

### 4. Processo de Criptografia
Utilizando a CLI, os arquivos de texto simples foram criptografados com a chave KMS. O comando especifica a chave a ser usada e os arquivos de entrada/saída.

![Print do Comando de Criptografia](caminho/para/seu/print-4.png)

### 5. Verificação do Arquivo Criptografado
Ao tentar visualizar o conteúdo do arquivo criptografado, o terminal exibe dados ilegíveis, confirmando o sucesso da operação.

![Print do Arquivo Criptografado Ilegível](caminho/para/seu/print-5.png)

### 6. Processo de Decriptografia
O processo inverso foi realizado, utilizando a mesma chave KMS para descriptografar os arquivos.

![Print do Comando de Decriptografia](caminho/para/seu/print-6.png)

### 7. Verificação Final
Após a decriptografia, o conteúdo do arquivo foi verificado e retornou com sucesso ao seu estado original, legível.

![Print do Arquivo Final Decriptografado](caminho/para/seu/print-7.png)

## Conclusão

Este laboratório prático demonstrou de forma eficaz a implementação de criptografia de dados em repouso na AWS. A integração entre IAM, EC2 e KMS oferece um mecanismo robusto e gerenciável para proteger informações sensíveis, uma prática essencial para a segurança em ambientes de nuvem.
