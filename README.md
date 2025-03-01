# Java Decompiler

# NOTICE!!!

This project would be deprecated, now this repo would be archived, the new Java Decompiler application would based on [JTQDF](https://github.com/evalexp/Java-Tool-Quick-Develop-Framework).

## Dependencies

* Python 3

## Usage

> use `py -3 java-decompiler.py -h` to show help docs.

Full Help:

```bash
usage: java-decompiler.py [-h] (-c | -w | -j | -f | -jf | -ndcp) -i INPUT -o OUTPUT [-T THREAD] [-cp] [-dp DECOMPILE_PACKAGE [DECOMPILE_PACKAGE ...]]

Java Decompile

options:
  -h, --help            show this help message and exit
  -c, --Class           Class input, decompile single class
  -w, --war             War input, decompile single war without lib jar decompilation
  -j, --jar             Jar input, decompile single jar
  -f, --folder          Folder input, would decompile all classes in the folder
  -jf, --jar-folder     Jar Folder input, would only decompile the jar which contains the specific package
  -ndcp, --no-decompile-copy
                        Only copy the resources file, would not decompile
  -i INPUT, --input INPUT
                        The input object, folder path or file name
  -o OUTPUT, --output OUTPUT
                        The output src folder
  -T THREAD, --thread THREAD
                        Decompile thread count
  -cp, --copy           Copy resources file(without class extension) to the destination, only work on -f/--folder
  -dp DECOMPILE_PACKAGE [DECOMPILE_PACKAGE ...], --decompile-package DECOMPILE_PACKAGE [DECOMPILE_PACKAGE ...]
                        Specify the package name to be decompiled
```

### Decompile a single class

```bash
py -3 java-decompiler.py -c -i test.class -o ./src
```

### Decompile a jar

```bash
py -3 java-decompiler.py -j -i test.jar -o ./src
```

### Decompile a Class Folder

```bash
py -3 java-decompiler.py -f -i tomcat/webapps/ROOT -o ./src
```

### Decompile a Jar Folder

> `-dp/--decompile-package` support `*` to match any word
```bash
py -3 java-decompiler.py -jf -i tomcat/webapps/ROOT/WEB-INF/lib -o ./src -dp com.*.test
```

```bash
py -3 java-decompiler.py -jf -i tomcat/webapps/ROOT/BOOT-INF/lib -o ./src -dp com.testa com.testb
```

### Decompile a War

```bash
py -3 java-decompiler.py -w -i tomcat/webapps/app.war -o ./src
```

