# linux_jni
note for build .so library


# compiler command for JNI library .so


## Example :

/usr/lib/jvm/java-8-oracle/jre/bin/java

g++ -Wall -fPIC -c '/home/sql/Desktop/Linux/DVR.cpp' -I ./ -I /usr/lib/jvm/java-8-oracle/include/linux/ -I /usr/lib/jvm/

g++ -fPIC -c jni.cpp -I /usr/lib/jvm/java-8-oracle/include/ -I /usr/lib/jvm/java-8-oracle/include/linux/

g++ -shared jni.o -o jni.so


## implementation :


g++ -Wall hand.cpp -I /usr/lib/jvm/java-8-oracle/include -I /usr/lib/jvm/java-8-oracle/include/linux -L. -lxmnetsdk -fPIC -c

g++ -shared hand.o -o hand.so

## put another library to compiler

g++ -Wall -fPIC -c -L. -lxmnetsdk hand.cpp -I /usr/lib/jvm/java-8-oracle/include -I /usr/lib/jvm/java-8-oracle/include/linux

g++ -Wall -rdynamic -shared -o libDVR.so hand.o -L. -lxmnetsdk



