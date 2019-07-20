proguard maven plugin
=======================

bug
---
 Mybatis cannot find mapper of com.baidu.fsg.uid.worker.dao.WorkerNodeDAO

solution
--------
 re-package the jar file: uid-generator-1.0.0-SNAPSHOT-pg.jar
````
mkdir out
cd out\
jar xvf ..\uid-generator-1.0.0-SNAPSHOT-pg.jar
del ..\uid-generator-1.0.0-SNAPSHOT-pg.jar
jar cvfM ..\uid-generator-1.0.0-SNAPSHOT-pg.jar .
cd ..
rmdir out /s /q
````

proguad options
----------------
```
-target 1.8
-verbose
-dontshrink
-dontoptimize
-dontskipnonpubliclibraryclasses
-dontskipnonpubliclibraryclassmembers
-allowaccessmodification
-useuniqueclassmembernames
-keeppackagenames
-keepclassmembers public class * {void set*(***);*** get*();}
-keepattributes Exceptions
-keepattributes InnerClasses
-keepattributes Signature
-keepattributes Deprecated
-keepattributes *Annotation*
-keepattributes Synthetic
-keepattributes EnclosingMethod
-keepattributes SourceFile,LineNumberTable
-keepattributes LocalVariable*Table
```
