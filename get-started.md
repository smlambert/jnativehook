

# Do this first, creates a jnativehook repo and deps
# does not need your git .ssh creds setup, so separate clone of 
```
git clone  https://github.com/smlambert/jnativehook.git 
(cd jnativehook/src/external; git clone  https://github.com/kwhat/libuiohook.git)
```

# ensure Java home is CMAKE_SYSTEM_PROCESSOR
```
set JAVA_HOME=/usr/lib/jvm/java-17-openjdk-ppc64el
```

# One of the H files is missing 
```
javac -h . com/github/kwhat/jnativehook/GlobalScreen.java
```

Copy the new generated h file to the build location 
```
cp src/main/java/com_github_kwhat_jnativehook_GlobalScreen.h \
        src/main/jni/com_github_kwhat_jnativehook_GlobalScreen.h
```

# bash build-all
