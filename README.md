```
#install xmake
#update it to dev
xmake update -s dev
#compile LLVM from master

xmake f --toolchain=clang --ar=llvm-ar
xmake b -vD
```

```
checking for platform ... windows
checking for architecture ... x64
[  0%]: generating.module.deps src\mod.mpp
checking for F:\llvm\bin\clang-scan-deps ... ok
checking for flags (-fvisibility-inlines-hidden) ... ok
> clang "-fvisibility-inlines-hidden" "-Qunused-arguments" "-m64"
checking for flags (-std=c++23) ... ok
> clang "-std=c++23" "-Qunused-arguments" "-m64"
checking for flags (-stdlib=libc++) ... ok
> clang "-stdlib=libc++" "-Qunused-arguments" "-m64"
checking for flags (-fexperimental-library) ... ok
> clang "-fexperimental-library" "-Qunused-arguments" "-m64"
F:\llvm\bin\clang-scan-deps --format=p1689 -- F:\llvm\bin\clang -x c++ -c src\mod.mpp -o build\.objs\test\windows\x64\release\src\mod.mpp.obj -Qunused-arguments -m64 -std=c++23 -Iinclude -fexceptions -fcxx-exceptions -stdlib=libc++ -fexperimental-library
[  0%]: generating.module.deps src\main.cpp
F:\llvm\bin\clang-scan-deps --format=p1689 -- F:\llvm\bin\clang -x c++ -c src\main.cpp -o build\.objs\test\windows\x64\release\src\main.cpp.obj -Qunused-arguments -m64 -std=c++23 -Iinclude -fexceptions -fcxx-exceptions -stdlib=libc++ -fexperimental-library
checking for flags (clang_modules_cache_path) ... ok
> clang "-fmodules-cache-path=C:\Users\arthu\AppData\Local\Temp\.xmake\231017" "-Qunused-arguments" "-m64"
[  0%]: generating.module.deps stdmodules\std.cppm
checking for flags (-Wno-reserved-module-identifier) ... ok
> clang "-Wno-reserved-module-identifier" "-Qunused-arguments" "-m64"
F:\llvm\bin\clang-scan-deps --format=p1689 -- F:\llvm\bin\clang -x c++ -c stdmodules\std.cppm -o build\.objs\stdmodules\windows\x64\release\stdmodules\std.cppm.obj -Qunused-arguments -m64 -std=c++23 -fexceptions -fcxx-exceptions -isystem C:\Dev\llvm\include\c++\v1 -stdlib=libc++ -fexperimental-library -Wno-reserved-module-identifier
checking for flags (clang_module_output) ... ok
> clang "-fmodule-output=" "-Qunused-arguments" "-m64"
[  8%]: compiling.module.release std
F:\llvm\bin\clang -c -x c++-module -fmodule-output=build\.gens\stdmodules\windows\x64\release\rules\modules\cache\a3c3afdf\std.pcm -Qunused-arguments -m64 -std=c++23 -fexceptions -fcxx-exceptions -isystem C:\Dev\llvm\include\c++\v1 -stdlib=libc++ -fexperimental-library -Wno-reserved-module-identifier -fmodules-cache-path=build\.gens\stdmodules\windows\x64\release\rules\modules\cache -o build\.objs\stdmodules\windows\x64\release\stdmodules\std.cppm.obj stdmodules\std.cppm
checking for flags (-fdiagnostics-color=always) ... ok
> clang "-fdiagnostics-color=always" "-Qunused-arguments" "-m64"
checking for flags (clang_module_file) ... ok
> clang "-fmodule-file=C:\Users\arthu\AppData\Local\Temp\.xmake\231017\_1B78F1B5A7B943708B5922614343BEE0.pcm" "-Qunused-arguments" "-m64"
[ 25%]: archiving.release stdmodules.lib
llvm-ar cr build\windows\x64\release\stdmodules.lib build\.objs\stdmodules\windows\x64\release\stdmodules\std.cppm.obj
[ 50%]: compiling.module.release foo
F:\llvm\bin\clang -c -x c++-module -fmodule-output=build\.gens\test\windows\x64\release\rules\modules\cache\574a3743\foo.pcm -fmodule-file=std=build\.gens\stdmodules\windows\x64\release\rules\modules\cache\a3c3afdf\std.pcm -Qunused-arguments -m64 -std=c++23 -Iinclude -fexceptions -fcxx-exceptions -stdlib=libc++ -fexperimental-library -fmodules-cache-path=build\.gens\test\windows\x64\release\rules\modules\cache -fmodule-file=std=build\.gens\stdmodules\windows\x64\release\rules\modules\cache\a3c3afdf\std.pcm -o build\.objs\test\windows\x64\release\src\mod.mpp.obj src\mod.mpp
error: @programdir\modules\private\async\runjobs.lua:256: @programdir\rules\c++\modules\modules_support\clang.lua:296: @programdir\modules\core\tools\gcc.lua:807: In module 'std' imported from src\mod.mpp:3:
C:\Dev\llvm\include\c++\v1\string:4319:21: error: no member named '__do_string_hash' in namespace 'std'
 4319 |         return std::__do_string_hash(__val.data(), __val.data() + __val.size());
      |                ~~~~~^
1 error generated.
stack traceback:
    [C]: in function 'error'
    [@programdir\core\base\os.lua:921]:
    [@programdir\modules\core\tools\gcc.lua:807]: in function 'catch'
    [@programdir\core\sandbox\modules\try.lua:123]: in function 'try'
    [@programdir\modules\core\tools\gcc.lua:748]:
    [C]: in function 'xpcall'
    [@programdir\core\base\utils.lua:280]:
    [@programdir\core\tool\compiler.lua:278]: in function 'compile'
    [@programdir\rules\c++\modules\modules_support\clang.lua:296]: in function '_build_modulefile'
    [@programdir\rules\c++\modules\modules_support\clang.lua:640]: in function 'jobfunc'
    [@programdir\modules\private\async\runjobs.lua:232]:
    [C]: in function 'xpcall'
    [@programdir\core\base\utils.lua:280]: in function 'trycall'
    [@programdir\core\sandbox\modules\try.lua:117]: in function 'try'
    [@programdir\modules\private\async\runjobs.lua:218]: in function 'cotask'
    [@programdir\core\base\scheduler.lua:404]:

stack traceback:
        [C]: in function 'error'
        @programdir\core\base\os.lua:921: in function 'base/os.raiselevel'
        (...tail calls...)
        @programdir\modules\private\async\runjobs.lua:256: in field 'catch'
        @programdir\core\sandbox\modules\try.lua:123: in global 'try'
        @programdir\modules\private\async\runjobs.lua:218: in upvalue 'cotask'
        @programdir\core\base\scheduler.lua:404: in function <@programdir\core\base\scheduler.lua:397>
```
