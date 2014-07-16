* small embed purpose programming language
* After Lua 5.0 they use semi-register based vm.
* [luajit](http://luajit.org/) is jit based Lua implementation
  * It's little buggy compared to the official implementation.
  * [Unofficial DynASM Document](http://corsix.github.io/dynasm-doc/)
* [LuaDist repository](https://github.com/LuaDist/lua)
* [luvit](https://github.com/luvit/luvit)

## Document
* [Lua 5.2 Reference](http://www.lua.org/manual/5.2/manual.html)
* [Lua 5.1 Reference](http://www.lua.org/manual/5.1/manual.html)

## [luvit](http://luvit.io/)
* node.js like library on lua
* [Repository](https://github.com/luvit/luvit)

## [luv](https://github.com/richardhundt/luv)
* Coroutine based libuv binding in lua.
* [Development is stopped.](https://github.com/richardhundt/luv/issues/24)
  * [Ray](https://github.com/richardhundt/ray)

## luabind
* Lua C++ binder.
* [Repository](https://github.com/luabind/luabind)
* [Document](http://www.rasterbar.com/products/luabind/docs.html)
* [About current most developed luabind fork](https://sourceforge.net/p/luabind/mailman/luabind-user/thread/12976453.uLFjAm3qha@ernie/)
  * [The latest stable luabind.](https://github.com/rpavlik/luabind)

## LuaBridge
* Another Lua binder.
* [Repository](https://github.com/vinniefalco/LuaBridge)

## [luajit-lang-toolkit](https://github.com/franko/luajit-lang-toolkit)
* Lua bytecode compiler written in lua.
* Can be used as luajit frontend.

## Co-Routine
* [tutorial](http://lua-users.org/wiki/CoroutinesTutorial)
* [example](http://stackoverflow.com/questions/7206411/lua-co-routines)
* [Pass co-routine running thread it self to lua_resume](http://lua-users.org/lists/lua-l/2005-02/msg00302.html)
```C
extern "C" {
#include <lua.h>
}
#include <cstdlib>

int lua_sleep(lua_State *L) {
  printf("lua_sleep called\n");
  return lua_yield(L,0);
}

int main() {
  lua_State* L = lua_open();
  luaL_openlibs(L);
  lua_register(L, "sleep", lua_sleep);

  lua_State* cL = lua_newthread(L);
  luaL_loadfile(cL, getenv("LUA_SCRIPT"));

  while (true) {
    int status = lua_resume(cL,0);
    if (status == LUA_YIELD) {
      printf("loop yielding\n");
    } else {
      if (status != 0 && lua_isstring(L, -1)) {
        printf("isstring: %s\n", lua_tostring(L, -1));
        lua_pop(cL, 1);
      }
      break;
    }
  }
  lua_close(L);
  return EXIT_SUCCESS;
}
```
