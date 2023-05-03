# burpsuite

#### downloads burpsuite pro

click link [here](https://portswigger.net/burp/releases)

compile java files
```
javac --add-exports java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED --add-exports java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED -d bin *.java
```

create a file in the META-INF directory with the name MANIFEST.MF
```
Manifest-Version: 1.0
Can-Retransform-Classes: true
Main-Class: com.eno.burpkey.KeygenForm
Premain-Class: com.eno.burpkey.Loader

```

now compile class file
```
/usr/lib/jvm/jdk-20/bin/jar cvfm burpkey.jar META-INF/MANIFEST.MF bin/com/eno/burpkey/*.class
```

##### create file to /usr/bin/burpsuite

```bash
#!/usr/bin/env sh

set -e

export JAVA_CMD=java

java --add-opens=java.desktop/javax.swing=ALL-UNNAMED \
     --add-opens=java.base/java.lang=ALL-UNNAMED \
     --add-opens=java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED \
     --add-opens=java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED \
     --add-opens=java.base/jdk.internal.org.objectweb.asm.Opcodes=ALL-UNNAMED \
     -javaagent:$(pwd)/burpkey.jar \
     -noverify \
     -jar $(pwd)/burpsuite.jar "$@"

```
<details>
<summary>Old version</summary>

java --illegal-access=permit -Dfile.encoding=utf-8 -javaagent:/usr/share/burpsuite/loader.jar -noverify -jar /usr/share/burpsuite/burpsuite.jar &

</details>
