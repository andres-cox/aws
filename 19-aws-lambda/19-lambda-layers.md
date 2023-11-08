# Lambda Layers

Custom Runtimes:
- Ex: C++
- Ex: Rust

Externalize Dependencies to re-use them: let say an node application doesn't change frequently its node_modules, you can convert that library part as a layer, so you only zip and upload main file that references the library layer.  