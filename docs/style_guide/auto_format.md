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
Similarily too the above format settings but with:

```
BasedOnStyleBy: Google 
DerivePointerAlignment: false 
PointerAlignment: Right
ReferenceAlignment: Right
```

* in VSCode setting:
    * Editor: Defaul Formatter -> C/C++
    *  C_Cpp: Clang_format_style -> file

### Pointer and reference alignment

Should be:

> function_name(type *var1, type &var2) {}

Test with:

> clang-format -i file_name