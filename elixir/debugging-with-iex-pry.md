# Debugging with IEx.pry

`IEx.pry` allows program execution inside `iex` interactive shell to be halted and inspecting the state at that moment.

To use:

1. Import IEx in the code with `require IEx`
2. In the code body insert `IEx.pry` call where you want the execution halted
3. Run the program in `iex`, when it reach the pry location it will prompt with
```sh
Request to pry #PID<0.85.0> at path/yourcode.ex:??. Allow? [Yn]
```
4. Press `Enter` or `Y`, then you'll back in regular `iex` state with the program execution halted.
5. You can inspect the state by REPL-ing any local binding/variable
6. To continue execution, call `respawn`

## References

* http://elixir-lang.org/docs/stable/iex/IEx.html#pry/1
