# reminder-erlang

Compile from erlang shell with: `make:all([load])`

# Run application

Without supervisor (0.0.1)

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
