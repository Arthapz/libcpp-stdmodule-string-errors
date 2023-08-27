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
[  0%]: generating.module.deps src\main.cpp
checking for clang-scan-deps ... ok
checking for flags (-fvisibility-inlines-hidden) ... ok
> clang "-fvisibility-inlines-hidden" "-Qunused-arguments" "-m64"
checking for flags (-std=c++23) ... ok
> clang "-std=c++23" "-Qunused-arguments" "-m64"
checking for flags (-stdlib=libc++) ... ok
> clang "-stdlib=libc++" "-Qunused-arguments" "-m64"
checking for flags (-fexperimental-library) ... ok
> clang "-fexperimental-library" "-Qunused-arguments" "-m64"
clang-scan-deps --format=p1689 -- clang -x c++ -c src\main.cpp -o build\.objs\test\windows\x64\release\src\main.cpp.obj -Qunused-arguments -m64 -std=c++23 -Iinclude -fexceptions -fcxx-exceptions -stdlib=libc++ -fexperimental-library
checking for flags (clang_modules_cache_path) ... ok
> clang "-fmodules-cache-path=C:\Users\arthu\AppData\Local\Temp\.xmake\230818" "-Qunused-arguments" "-m64"
[  0%]: generating.module.deps stdmodules\std.cppm
checking for flags (-Wno-reserved-module-identifier) ... ok
> clang "-Wno-reserved-module-identifier" "-Qunused-arguments" "-m64"
clang-scan-deps --format=p1689 -- clang -x c++ -c stdmodules\std.cppm -o build\.objs\stdmodules\windows\x64\release\stdmodules\std.cppm.obj -Qunused-arguments -m64 -std=c++23 -fexceptions -fcxx-exceptions -isystem C:\Dev\llvm\include\c++\v1 -stdlib=libc++ -fexperimental-library -Wno-reserved-module-identifier
checking for flags (clang_module_output) ... ok
> clang "-fmodule-output=" "-Qunused-arguments" "-m64"
[  9%]: compiling.module.release std
clang -c -x c++-module -fmodule-output=build\.gens\stdmodules\windows\x64\release\rules\modules\cache\a3c3afdf\std.pcm -Qunused-arguments -m64 -std=c++23 -fexceptions -fcxx-exceptions -isystem C:\Dev\llvm\include\c++\v1 -stdlib=libc++ -fexperimental-library -Wno-reserved-module-identifier -fmodules-cache-path=build\.gens\stdmodules\windows\x64\release\rules\modules\cache -o build\.objs\stdmodules\windows\x64\release\stdmodules\std.cppm.obj stdmodules\std.cppm
checking for flags (-fdiagnostics-color=always) ... ok
> clang "-fdiagnostics-color=always" "-Qunused-arguments" "-m64"
error: @programdir\modules\private\async\runjobs.lua:256: @programdir\rules\c++\modules\modules_support\clang.lua:300: @programdir\modules\core\tools\gcc.lua:797: In file included from stdmodules\std.cppm:23:
stdmodules/std/ctime.inc:21:14: error: using declaration referring to 'ctime' with internal linkage cannot be exported
   21 |   using std::ctime;
      |              ^
C:\Program Files (x86)\Windows Kits\10\Include\10.0.22621.0\ucrt\time.h:501:41: note: target of using declaration
  501 |         static __inline char* __CRTDECL ctime(
      |                                         ^
In file included from stdmodules\std.cppm:23:
stdmodules/std/ctime.inc:22:14: error: using declaration referring to 'difftime' with internal linkage cannot be exported
   22 |   using std::difftime;
      |              ^
C:\Program Files (x86)\Windows Kits\10\Include\10.0.22621.0\ucrt\time.h:509:42: note: target of using declaration
  509 |         static __inline double __CRTDECL difftime(
      |                                          ^
In file included from stdmodules\std.cppm:23:
stdmodules/std/ctime.inc:23:14: error: using declaration referring to 'gmtime' with internal linkage cannot be exported
   23 |   using std::gmtime;
      |              ^
C:\Program Files (x86)\Windows Kits\10\Include\10.0.22621.0\ucrt\time.h:518:46: note: target of using declaration
  518 |         static __inline struct tm* __CRTDECL gmtime(
      |                                              ^
In file included from stdmodules\std.cppm:23:
stdmodules/std/ctime.inc:24:14: error: using declaration referring to 'localtime' with internal linkage cannot be exported
   24 |   using std::localtime;
      |              ^
C:\Program Files (x86)\Windows Kits\10\Include\10.0.22621.0\ucrt\time.h:525:46: note: target of using declaration
  525 |         static __inline struct tm* __CRTDECL localtime(
      |                                              ^
In file included from stdmodules\std.cppm:23:
stdmodules/std/ctime.inc:25:14: error: using declaration referring to 'mktime' with internal linkage cannot be exported
   25 |   using std::mktime;
      |              ^
C:\Program Files (x86)\Windows Kits\10\Include\10.0.22621.0\ucrt\time.h:541:42: note: target of using declaration
  541 |         static __inline time_t __CRTDECL mktime(
      |                                          ^
In file included from stdmodules\std.cppm:23:
stdmodules/std/ctime.inc:28:14: error: using declaration referring to 'time' with internal linkage cannot be exported
   28 |   using std::time;
      |              ^
C:\Program Files (x86)\Windows Kits\10\Include\10.0.22621.0\ucrt\time.h:548:42: note: target of using declaration
  548 |         static __inline time_t __CRTDECL time(
      |                                          ^
In file included from stdmodules\std.cppm:23:
stdmodules/std/ctime.inc:29:14: error: using declaration referring to 'timespec_get' with internal linkage cannot be exported
   29 |   using std::timespec_get;
      |              ^
C:\Program Files (x86)\Windows Kits\10\Include\10.0.22621.0\ucrt\time.h:556:39: note: target of using declaration
  556 |         static __inline int __CRTDECL timespec_get(
      |                                       ^
7 errors generated.
```