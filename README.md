# File Uploader

Precisamos de um serviço que seja capaz de receber arquivos e armazená-los em um lugar seguro. Depois de salvos, precisamos ler esses arquivos em chunks, determinando o tamanho do chunk que queremos ler.

## Instruções

1. Crie um repositório no seu GitHub
2. Desenvolva o projeto em seu repositório
3. Quando terminar, dê acesso à pessoa do nosso time que irá revisar o código
4. Avise ao Recruiter que você terminou

## Problema

Dado um arquivo (data/nasdaq_symbols.csv), faça o upload para algum backend de armazenamento (GCS, S3, local filesystem). Em um segundo momento, vamos ler esse arquivo em chunks.

## Requisitos

1. O código deve ser escrito utilizando Go
2. O upload deve ser realizado através de uma chamada HTTP
3. O upload deve gerar um identificador, que será utilizado para requisições futuras
4. O arquivo deve ser lido pelo seu identificador através de chamadas HTTP, especificando o `offset` e o `length` do chunk que deve ser retornado.
6. Utilizar dois backends de amarzenamento. Qual backend utilizar deve uma configuração. Ex: GCS e FS, S3 e GCS, etc... 
7. Não utilizar nenhuma conexão directa com o cloud provider, utilize serviços de mock como:  
  a. [Fake GCS](https://github.com/fsouza/fake-gcs-server)  
  b. [Local Stack](https://github.com/localstack/localstack)  
  c. Existem outras opções, fique à vontade para escolher  
  d. Iremos testar o seu serviço utilizando o mesmo mock que você

## Good to have

1. Ser possível rodar através de um container
2. Eventuais scripts para algum tipo de configuração
3. `docker-compose` para subir a stack completa
4. `README` explicando sobre padrões e decisões de implementação 

## Avaliação

Esperamos que esse seja um desafio que você precise investir poucas horas. Entendemos que nem tudo estará da forma que você gostaria.

1. Requisitos e Good to Haves serão levados em consideração
2. A eficiência do seu serviço deve ser o foco
3. Código organizado, limpo e legível. Isso facilita entender suas decisões.
4. Testes unitários (não foque em 100% de code coverage)
5. Explicações sobre as decicões que você tomou e porquê.
6. Seu serviço será testado com diferentes arquivos

## Observações

1. Se tiver dúvida durante o teste ou quiser tirar dúvidas, fique à vontade para procurar a pessoa que irá revisar seu código (LinkedIn/e-mail).  
2. Se criar um repositório privado, dê acesso à quem irá revisar o código.
3. *Não se preocupe em manter estado de arquivos anteriores*. Você pode manter o estado dos arquivos em memória.
4. Não se preocupe com indentação/formatação ao retornar as linhas, assuma que o arquivo que vamos trabalhar sempre será um CSV. Então o esperado é que cada linha retornada seja uma linha do CSV.
