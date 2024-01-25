Python UFRJ
===========

Este é o repositório do curso de Computação I em Python.

**Website:** https://python.ic.ufrj.br

Instalação
----------

O primeiro passo é clonar este repositório.

```
git clone https://github.com/ic-ufrj/python
```

O segundo passo é instalar o Hugo. O tema que estamos usando exige uma versão
muito recente do Hugo. No Linux eu baixei o executável (prebuilt-binary) pois
a versão no gerenciador de pacotes era muito antiga. Como é um arquivo só, dá
pra salvá-lo na raiz do repositório. Veja https://gohugo.io/installation/

Rodando o site
--------------

Para testar o site localmente, rode `./hugo serve` e abra o seu web-browser
em https://localhost:1313/. Ele monitora a pasta com os arquivos markdown e
atualiza o browser automáticamente quando você modificar um deles.

Você também pode rodar só `./hugo` para gerar arquivos HTML na pasta public,
porém não dá pra abrir esses htmls direto no browser (a página fica quebrada,
sem os menus e sem o CSS adequado)


Editando
--------

As duas pastas que você precisa mexer são a pasta `content` e a `static`.
A content contém o texto do site em markdown e a static contém imagens, etc.

Para criar uma nova postagem, use use "./hugo new content/aulas/aula-NN.md"
ou copie uma postagem existente. É importante que o arquivo tenha um cabeçalho
com "title:" e que você preencha este title.


Publicando
----------

Para publicar uma postagem, faça o commit e dê push no repositório.
Em primeiro lugar, solicite ao administrador do repositório para adicionr
você como contribuinte. Em sequida, faça os passos de sempre:

```
git status
git add arquivos-editados
git commit
git push
```

Após o Push, [o site](https://python.ic.ufrj.br) será recompilado
e atualizado automaticamente. Este processo demora por volta de 1-2 minutos.
Você pode conferir este andamento na aba
[Actions](https://github.com/ic-ufrj/python/actions) do Github.


Não use URLs absolutos
----------------------

Hugo (o software) não lida bem com URLs absolutos caso a raiz to website seja
um subdiretório, que é o caso do Github Pages caso você ainda não tenha DNS de
domínio próprio. Por exemplo, ele põe "/images" em "github.io/images" em vez de
"github.io/seurepositorio/images", como gostaríamos.

1. Dentro de postagens markdown, sempre use URLs relativos.
   Salve as imagens na mesma pasta
2. Em templates HTML, pode ser que você realmente precise de URLs absolutos.
   Use a função absURL do Hugo. Não coloque "/" no começo! (é um bug do Hugo).
   Descrição do pepino: https://github.com/gohugoio/hugo/issues/10606
