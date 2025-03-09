---
date: 2024-11-08 
tags: 
    - c
---

# auto complete c nvim header

If you’re using `clangd` as your Language Server Protocol (LSP) in Neovim, here’s how you can configure it to recognize the include directory (`include/`) where `graph.h` is located. This should help `clangd` properly resolve the header file and recognize the functions in your code.

### Use a `.clangd` Configuration File

You can create a `.clangd` file in the root of your project directory with the following content to ensure `clangd` knows about the `include` directory:

1. **Create `.clangd` in Your Project Root:**
   ```bash
   touch .clangd
   ```

2. **Add Include Path Configuration:**
   Add the following content to `.clangd`:
   ```yaml
   CompileFlags:
     Add: [-Iinclude]
   ```
   This tells `clangd` to add the `include` directory as an additional path to search for header files.

3. **Restart `clangd` in Neovim:**
   After creating and editing the `.clangd` file, you may need to restart the LSP server in Neovim:

   - Run `:LspRestart` in Neovim or close and reopen Neovim to ensure `clangd` picks up the new configuration.

> [!IMPORTANT]
> to get it work use include <../include/nameofheader.h> (without this lsp do not work but code yes)

