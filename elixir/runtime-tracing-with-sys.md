# Run-time tracing with :sys

BEAM (Erlang) has built in features to do functions tracing in runtime and also collect statistics. The neat thing about the built in features are they can be turn on and off arbitrarily during runtime, which can be useful for debugging production code.

### Basic tracing

To turn on basic tracing, pass in extra parameters when calling GenServer.start_link/3

```
iex> {:ok, pid} = GenServer.start_link(Sequence.Server, 100, [debug: [:trace]])
iex> GenServer.call(pid, :next_number)
*DBG* <0.69.0> got call next_number from <0.25.0>
*DBG* <0.69.0> sent 100 to <0.25.0>, new state 101
101
iex>
```

### Basic tracing

```
iex> {:ok, pid} = GenServer.start_link(Sequence.Server, 100, [debug: [:statistics]])
iex> GenServer.call(pid, :next_number)
101
iex> GenServer.call(pid, :next_number)
102
iex> :sys.statistics pid, :get
{:ok,
 [start_time: {{2016, 4, 26}, {6, 57, 45}},
  current_time: {{2016, 4, 26}, {6, 57, 59}}, reductions: 48, messages_in: 2,
  messages_out: 0]}
```

### Run-time tracing

If we have the pid of the application, we can turn it on and off during runtime using `:sys`

```
iex> :sys.trace pid, true
iex> :sys.statistics pid, true
```

To turn off
```
iex> :sys.trace pid, false
iex> :sys.statistics pid, false
```
