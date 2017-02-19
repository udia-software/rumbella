# Rumbl/Rumbella

Rumbl application from `Programming Phoenix Productive |> Reliable |> Fast` by Chris McCord, Bruce Tate, and José Valim
* Refactored into an umbrella application as of Chapter 12

## Development && Production Configuration Secrets
Before your app will function correctly, you need to create two files:

  * `apps/rumbl/config/dev.secret.exs`
  Make a file that looks like the following containing a Wolfram Alpha App ID
  ```text
  use Mix.Config

  config :rumbl, :wolfram, app_id: "12345-1234567890"
  ```

  * `apps/rumbl/config/prod.secret.exs` (for production)
  Values are changed and do not reflect actual production strings
  ```text
  use Mix.Config

  config :rumbl, Rumbl.Endpoint,
    secret_key_base: "super-secret-key-base"

  # Configure your database
  config :rumbl, Rumbl.Repo,
    adapter: Ecto.Adapters.Postgres,
    username: "postgres",
    password: "postgres",
    database: "rumbl_prod",
    pool_size: 20

  config :rumbl, :wolfram, app_id: "12345-1234567890"
  ```


## Development:
  * Set your mix environment variable `export MIX_ENV=dev`
  * Install dependencies with `mix deps.get`
  * Create and migrate your database with `mix ecto.create && mix ecto.migrate`
  * Install Node.js dependencies with `cd apps/rumbl`, `npm install`
  * Back at root, start Phoenix endpoint with `mix phoenix.server`
  * Start Phoenix interactively with `iex -S mix phoenix.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

## Testing
  * Set your mix environment variable `export MIX_ENV=test`
  * Run the tests `mix test`

## Production Deploy
Ready to run in production? Please [check our deployment guides](http://www.phoenixframework.org/docs/deployment).

  * Set your mix environment variable `export MIX_ENV=prod`
  * Install dependencies with `mix deps.get`
  * Compile your code with `mix compile`
  * Create and migrate your database with `mix ecto.create && mix ecto.migrate`
  * Set your port `export PORT=8080`
  * Run your application `mix phoenix.server`

## Learn more

  * Official website: http://www.phoenixframework.org/
  * Guides: http://phoenixframework.org/docs/overview
  * Docs: https://hexdocs.pm/phoenix
  * Mailing list: http://groups.google.com/group/phoenix-talk
  * Source: https://github.com/phoenixframework/phoenix

## License

```text
MIT License

Copyright (c) 2017 Udia

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
