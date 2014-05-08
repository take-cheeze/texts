* Squirrel is a lightweight object oriented programming language.

## sq
* very simple stand alone interpreter
* can compile or run squirrel script
* has interactive interface
* getting arguments passed
  * 2.x.x: ARGV variable
  * 3.x.x: vargv(used in variable length arguments) value
* options
  * -c: compiles the file to bytecode(default output 'out.cnut')
    * if this option is passed only compiles the passed files
  * -o: specifies output file for the -c option
  * -d: generates debug infos
  * -v: displays version infos
  * -h: prints help

## Link 
* [Home Page](http://www.squirrel-lang.org/)
* [Squirrel 3.0 Reference Manual](http://www.squirrel-lang.org/doc/squirrel3.html)
* [Squirrel Standard Library 3.0](http://www.squirrel-lang.org/doc/sqstdlib3.html)

## Binder 
* Sqrat
  * [Project Page](http://sourceforge.net/projects/scrat/)
  * [Home Page](http://scrat.sourceforge.net/)
  * Problem with autotools build. Somehow the author forgot the header generating?

## Virtual Machine Internal 
* stack based machine.
* coroutine == lightweight thread
  * Suspend just returns SQ_SUSPEND_FLAG
  * when CallNative receives SQ_SUSPEND_FLAG it will go out the vm loop immediatlly
  * created by newthread
  * suspend/wakeup
* SQVM::Execute
  * ExecutionType
    * By default ET_CALL
    * ET_RESUME_VM: if raise error is false
    * ET_RESUME_THROW_VM: if raise error is true
    * ET_RESUME_GENERATOR: used in generator