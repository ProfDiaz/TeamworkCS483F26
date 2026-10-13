# Dev Patel

## Debugging tips for Python

pdb — The Python Debugger
The module pdb defines an interactive source code debugger for Python programs. It supports setting (conditional) breakpoints and single stepping at the source line level, inspection of stack frames, source code listing, and evaluation of arbitrary Python code in the context of any stack frame

The typical usage to break into the debugger is to insert:
import pdb; pdb.set_trace() or breakpoint()

You can also invoke pdb from the command line to debug other scripts. For example:
python -m pdb [-c command] (-m module | -p pid | pyfile) [args ...]

-c, --command <command>
To execute commands as if given in a .pdbrc file
-m <module>
To execute modules similar to the way python -m does. As with a script, the debugger will pause execution just before the first line of the module.
-p, --pid <pid>
Attach to the process with the specified PID.
