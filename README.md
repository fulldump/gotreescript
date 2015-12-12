# gotreescript
<img src="https://api.travis-ci.org/GerardoOscarJT/gotreescript.svg?branch=master">

TreeScript parser for Go

<!-- MarkdownTOC autolink=true bracket=round depth=4 -->

- [Grammar](#grammar)

<!-- /MarkdownTOC -->

## Grammar

```EBNF

treescript = text | (tag text)* ;

text = { ~begin } ;

tag = tag comment | tag named ;

tag comment = begin , { white } , ~end , end ;

tag named = begin , { ~white }, { white | pair | flag}, end ;

flag = ~( white | "=" ) ;

pair = flag , { white } , ( ":" | "=" ) , { white } , value ;

value = ~( white | end ) | ( '"' , { ~'"' } , '"') | ( "'" , { ~"'" } , "'") ;

begin = [[ ;

end = ]] ;

white = \t | \n | " " ;

```

