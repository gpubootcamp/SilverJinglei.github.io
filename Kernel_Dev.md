

# VS Code Setting

## C/C++ Configurations
@.vscode/c_cpp_properties.json

Include path
```
${workspaceFolder}/**
/usr/src/linux-headers-4.15.0-47/include/**
/usr/src/linux-headers-4.15.0-47-generic/include/**
```

## settings
@.vscode/settings.json

```json
{
    "files.associations": {
        "kernel.h": "c",
        "module.h": "c"
    },
    "files.exclude": {
        "*.cmd": true,
        "*.ko": true,
        "*.mod.c": true,
        "*.mod.o": true,
        "*.o": true,
        "*.o.cmd": true
    }
}
```

# Steps
> https://blog.csdn.net/yexiangCSDN/article/details/81064618

1. follow above tutorial to write a "hello kernel" with Makefile
2. $make => gen .ko
3. cmd: insmod, modinfo, dmesg, rmmod
