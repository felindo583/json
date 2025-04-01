# Manipulação de JSON em PHP

Este documento descreve o processo de leitura, modificação e salvamento de um arquivo JSON em PHP.

## Passos

1. **Ler o conteúdo do arquivo JSON**
   ```php
   $json = file_get_contents("dados.json");
   ```
   Este comando lê o conteúdo do arquivo `dados.json` e o armazena na variável `$json`.

2. **Converter JSON para um array em PHP**
   ```php
   $dados = json_decode($json, true);
   ```
   O `json_decode(..., true)` converte a string JSON em um array associativo.

3. **Garantir que `$dados` seja um array válido**
   ```php
   if (!is_array($dados)) {
       $dados = [];
   }
   ```
   Esta verificação assegura que `$dados` seja um array antes de manipulá-lo.

4. **Capturar dados do formulário**
   ```php
   $novoDado = [
       "nome" => $_POST["nome"],
       "idade" => $_POST["idade"]
   ];
   ```
   Os dados enviados via `POST` são capturados e armazenados no array `$novoDado`.

5. **Adicionar novo dado ao array existente**
   ```php
   $dados[] = $novoDado;
   ```
   O novo dado é adicionado ao array existente `$dados`.

6. **Converter o array PHP de volta para o formato JSON**
   ```php
   $jsonAtualizado = json_encode($dados, JSON_PRETTY_PRINT);
   ```
   O array atualizado é convertido novamente para JSON, com formatação legível.

7. **Salvar o novo JSON no arquivo**
   ```php
   file_put_contents("dados.json", $jsonAtualizado);
   ```
   O JSON atualizado é salvo de volta no arquivo `dados.json`.

## Observação
Certifique-se de que o arquivo `dados.json` tem permissões adequadas para leitura e escrita pelo servidor PHP.

