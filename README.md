# lua-web

## About

This is an emscripten compiled version of Lua 5.3.6.

## How this Library Was Built

Run the following command in the lua-x.x.x/src folder:

```shell
make generic CC='emcc -s WASM=1' AR='emar rcu' RANLIB='emranlib'
```

## How to Use this with CMAKE and Emscripten

Link as library for emscripten using cmake:

```cmake
if (${CMAKE_SYSTEM_NAME} MATCHES "Emscripten")
  set_target_properties(${PROJECT_NAME} PROPERTIES LINK_FLAGS "... -L${PROJECT_SOURCE_DIR}/lua-web/src -s ...")
endif ()
```
