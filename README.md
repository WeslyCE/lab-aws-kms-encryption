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

![Print da Chave KMS Criada no Console AWS](https://github.com/WeslyCE/lab-aws-kms-encryption/blob/main/imagens/Key%20ARN.png)

### 2. Configuração do Ambiente no EC2
Conectei-me à instância EC2 via Session Manager e instalei a AWS Encryption CLI, preparando o servidor para as operações.

![Print da Instalação da CLI](https://github.com/WeslyCE/lab-aws-kms-encryption/blob/main/imagens/cliinstalation.png)

### 3. Criação dos Arquivos de Teste (Plain Text)
Foram criados arquivos de texto simples para simular os dados que precisavam de proteção.

![Print do Conteúdo dos Arquivos Originais](https://github.com/WeslyCE/lab-aws-kms-encryption/blob/main/imagens/cria%C3%A7%C3%A3o%20do%20arquivo%20de%20texto.png
)

### 4. Processo de Criptografia
Utilizando a CLI, os arquivos de texto simples foram criptografados com a chave KMS. O comando especifica a chave a ser usada e os arquivos de entrada/saída.

![Print do Comando de Criptografia](https://github.com/WeslyCE/lab-aws-kms-encryption/blob/main/imagens/criptografando%20comando.png)

### 5. Verificação do Arquivo Criptografado
Ao tentar visualizar o conteúdo do arquivo criptografado, o terminal exibe dados ilegíveis, confirmando o sucesso da operação.

![Print do Arquivo Criptografado Ilegível](https://github.com/WeslyCE/lab-aws-kms-encryption/blob/main/imagens/verifica%C3%A7%C3%A3o%20de%20arquivo.png)

### 6. Processo de Decriptografia
O processo inverso foi realizado, utilizando a mesma chave KMS para descriptografar os arquivos.

![Print do Comando de Decriptografia](https://github.com/WeslyCE/lab-aws-kms-encryption/blob/main/imagens/texto%20descriptografado.png)

### 7. Verificação Final
Após a decriptografia, o conteúdo do arquivo foi verificado e retornou com sucesso ao seu estado original, legível.

![Print do Arquivo Final Decriptografado](https://github.com/WeslyCE/lab-aws-kms-encryption/blob/main/imagens/texto%20descriptografado.png)

## Conclusão

Este laboratório prático demonstrou de forma eficaz a implementação de criptografia de dados em repouso na AWS. A integração entre IAM, EC2 e KMS oferece um mecanismo robusto e gerenciável para proteger informações sensíveis, uma prática essencial para a segurança em ambientes de nuvem.

