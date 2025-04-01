1. 1. file_get_contents("dados.json")
 Lê conteudos do arquivo Json
2. 2. json_decode(...,true)
  converte o json para um array em php
3.3 is_array($dados)
  garante que $dados seja um array valido.
4.4. $_post["nome"] e $post["idade"]
  captura dados do formulario
5.5$dados[]= $novoDado
  adciona novo dado num array existente
6.6 json_encode($dados, json_pretty_print)
  converte o array php de volta para o formato json
7.7 file_put_contents("dados.jason",...)
salva o novo json no arquivo
