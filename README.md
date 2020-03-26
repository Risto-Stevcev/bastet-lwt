# bastet_lwt

Lwt implementations for bastet


## Installation

```
opam install bastet_lwt
```


## Example

```ocaml
# #require "bastet";;
# #require "bastet_lwt";;

# let foo = Bastet_lwt.Monad.pure "foo"
  and bar = Bastet_lwt.Monad.pure "bar"
  and baz = Bastet_lwt.Monad.pure "baz";;
val foo : string Lwt.t = <abstr>
val bar : string Lwt.t = <abstr>
val baz : string Lwt.t = <abstr>

# let list_of_promises = [foo; bar; baz];;
val list_of_promises : string Lwt.t list = [<abstr>; <abstr>; <abstr>]

# Bastet_lwt.List.Traversable.sequence;;
- : 'a Lwt.t list -> 'a list Lwt.t = <fun>

# Bastet_lwt.List.Traversable.sequence list_of_promises;;
- : string list = ["foo"; "bar"; "baz"]
```


## License

See [LICENSE][1]

[1]: https://github.com/Risto-Stevcev/bastet-lwt/blob/master/LICENSE
