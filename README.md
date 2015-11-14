# reminder-erlang

Compile from erlang shell with: `make:all([load])`

# Run application

Without supervisor
------------------

```erlang
> evserv:start().
<0.49.0>
> evserv:subscribe({self()).
{ok,#Ref<0.0.3.212>}
> evserv:add_event("Hey there", "test", {{2099,1,1},{0,0,0}}).
ok
> evserv:listen(5).
[{done,"Hey there","test"}]
```

With supervisor
---------------

```erlang
1> SupPid = sup:start(evserv, []).
<0.35.0>
2> whereis(evserv).
<0.36.0>
3> exit(whereis(evserv), die).
Process <0.36.0> exited for reason die
true
4> exit(whereis(evserv), die).
Process <0.39.0> exited for reason die
true
5> exit(SupPid, shutdown).
true
6> whereis(evserv).
undefined
```
