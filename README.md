# burpsuite

```bash
#!/usr/bin/env sh

set -e

export JAVA_CMD=java

java --illegal-access=permit -Dfile.encoding=utf-8 -javaagent:/usr/share/burpsuite/loader.jar -noverify -jar /usr/share/burpsuite/burpsuite.jar &
```
