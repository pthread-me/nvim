# Set-up Notes

## Elixir-ls
- Make sure to install a global PLT table for the dialyzer:

    ```sh
    mix archive.install hex dialyxir --force && mix dialyzer --plt
    ```
- We can put a scheduler limit on the lsp if the above didn't work
    1. create a .config/elixir_ls/setup.sh file
    2. The file content should include: (replace 2:2 to use more cpu power, i think
    this limits the number of processes allocated to it but don't quote me on that. It just worked)
    
    ```sh
    #!/bin/bash 
    export ERL_FLAGS="$ERL_FLAGS +S 1:1"
    ```
- Also everything should be installed via asdf. So : erlang, elixir and 
    elixir-ls (search for their asdf gitguh repos)

## Clangd

- lspconfig assumes that it's installed locally. 
- The apt version is old, i'd use asdf but havent yet so cant say all c++23 functions are 
    now included the newer versions.
