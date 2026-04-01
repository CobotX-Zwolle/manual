## Auto format settings 

* Use clang-format in your preferred editor and turn on format on save 
* Use the following preset in the .clang-format file: 

```
BasedOnStyleBy: Google 
DerivePointerAlignment: false 
PointerAlignment: Left
ReferenceAlignment: Left
```

### Auto format VSCode 
VScode has some issues due to an overriding default in the style reference

* Insall the extension [clangd](https://marketplace.visualstudio.com/items?itemName=llvm-vs-code-extensions.vscode-clangd)
* in VSCode setting:
    * Editor: Defaul Formatter -> clangD
    *  Clangd: Path -> $HOME/.vscode-server/data/User/globalStorage/llvm-vs-code-extensions.vscode-clangd/install/21.1.8/clangd_21.1.8/bin/clangd
    *  C_Cpp: Clang_format_style -> Google

### Pointer and reference alignment

Should be:

> function_name(type *var1, type &var2) {}