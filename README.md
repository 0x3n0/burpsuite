# burpsuite

#### downloads burpsuite pro

click link [here](https://portswigger.net/burp/releases)

##### create file to /usr/bin/burpsuite

```bash
#!/usr/bin/env sh

set -e

export JAVA_CMD=java

java --illegal-access=permit -Dfile.encoding=utf-8 -javaagent:/usr/share/burpsuite/loader.jar -noverify -jar /usr/share/burpsuite/burpsuite.jar &
```
run burpsuite from terminal and run java -jar keygen.jar
copy paste your key burpsuite
