# INSTALLATION 

## Prerequisites

you need:

* perl (an interpreter for the perl language, see
  http://www.perl.com)

* ghostscript (an interpreter/raster image processor for the
                 PostScript language, see
                 https://www.ghostscript.com/)

* maybe an ANSI-C compiler if the provided binaries for bbox do not
  work for you. Sorry for the inconvenience, but I tried to write a
  bbox equivalent in perl and it was terribly slow. Therefore I stick
  to C, because of much better performance.  *Alternatively* you can
  use ps2eps option -g, then no bbox binary is required.

## How to install

  Please check that you have working
  <kbd>perl</kbd> and <kbd>ghostscript</kbd> packages.

### Linux/UNIX-based platform

1. install bbox

   If a bbox binary is included for your platform you simply move it
   into any directory of the system search path. Otherwise, you have
   to compile bbox.c first by invoking 

   ```
   cc -o bbox bbox.c. 
   ```

   (sometimes "make bbox" also works).
   Please make sure that bbox is executable (chmod a+x bbox).
   If you already have a working perl and a working ghostscript, you're 
   finished here, else you have to install them first.

2. install ps2eps
  
   On Unix platforms you simply move the perl script ps2eps into a
   directory which is included in the system or personal search path
   (e.g., /usr/local/bin, $home/bin). Please make sure that ps2eps is
   executable (chmod a+x ps2eps).

### Windows-based platform

Use the command line interpreter:
Copy bbox.exe into a directory that is 
in your's or the system's search path for executables. Please try 
to invoke bbox -h afterwards.

The best possibility is to use associated file types under 
Windows:
  
1. rename ps2eps to ps2eps.pl and 

2. SET PATHEXT=.pl;%PATHEXT% or use the 
   settings -> control panel -> system -> "advanced" tab -> environment variables
   and edit the PATHEXT entry accordingly.

3. then simply typing ps2eps should invoke ps2eps correctly 

  Another option is to call perl directly:
```
  perl ps2eps ...
```
  
The script assumes that you have "gswin32c" as 
postscript interpreter in your path. Under Windows ps2eps
can perform wildcard expansion on its own.

