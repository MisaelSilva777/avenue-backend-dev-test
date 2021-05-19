# File Uploader

Precisamos de um serviço que seja capaz de receber arquivos e armazena-los em um lugar seguro. Depois de salvos, precisamos ler esses arquivos em chunks, determinando o tamanho do chunck que queremos ler.

## Instruções

1. Faça um `fork` __privado__ desse repositório
2. Desenvolva o projeto em seu repositório
3. Quando terminar, dê acesso à pessoa do nosso time que irá revisar o código
4. Avise ao Recruiter que você terminou

_Oberservações_

Se tiver dúvida durante o teste ou quiser tirar dúvidas, fique à vontade para procurar a pessoa que irá revisar seu código (LinkedIn/e-mail).

## Problema

Dado um arquivo (data/nasdaq_symbols.csv), faça o upload para algum backend de armazenamento (GCS, S3, local filesystem). Em um segundo momento, vamos ler esse arquivo chuncks.

_Oberservações_

Não se preocupe em manter estado de arquivos anteriores. Você pode manter o estado dos arquivos em memória.

## Requisitos

1. O upload deve ser realizado através de uma chamda HTTP
2. O upload deve gerar um identificador, que será utilizado para requisições futuras
3. O arquivo deve ser lido pelo seu identificator através de chamadas HTTP, especificando o `offset` e o `length` do chunk que deve ser retornado.


_Oberservações_

Não se preocupe com indentação/formatação ao retornar as linhas, assuma que o arquivo que vamos trabalhar sempre será um CSV. Então o esperado é que cada linha retornada seja uma linha do CSV.

## Good to have

1. Ser possível rodar através de um container
2. Eventuais scripts para algum tipo de configuração
3. Não depender de nenhuma núvem para subir o arquivo:  
  a. [Fake GCS](https://github.com/fsouza/fake-gcs-server)  
  b. [Fake S3](https://github.com/jubos/fake-s3)  
  c. Existem outras opções, fique à vontade para escolher  
4. `docker-compose` para subir a stack completa
5. `README` explicando sobre padrões e decisões de implementação 
6. Multiplos backends de armazenamento. Qual backend utilizar pode ser uma configuração.

## Avaliação

Esperamos que esse seja um desafio que você precise investir no máximo 2h. Entendemos que nem tudo estará da forma que você gostaria.

1. Requisitos e Good to Haves são levados em consideração
2. A eficiência do seu serviço deve ser o foco
3. Código organizado, limpo e legível. Isso facilita entender suas decisões.
4. Testes unitários (não foque em 100% de code coverage)
5. Explicações sobre as decicões que você tomou e porquê.
6. Seu serviço será testado com diferentes arquivos
