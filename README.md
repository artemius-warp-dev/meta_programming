# meta_programming

A tiny test framework written with Elixir macros, following *Metaprogramming
Elixir* by Chris McCord.

- `assertion.exs` — `use Assertion` registers an accumulating `@tests`
  attribute, the `test/2` macro turns each test into a function, and
  `@before_compile` generates `run/0`. `assert/1` pattern-matches the operator
  of the quoted expression to report readable failures.
- `math_test_import.exs` — an example test module using it (with deliberately
  failing assertions).

```sh
elixir -r assertion.exs -e "Code.require_file(\"math_test_import.exs\"); MathTest.run()"
```
