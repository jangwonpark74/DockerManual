# seccomp security profile
- [Secure Computing Mode](https://docs.docker.com/engine/security/seccomp/)

- This feature is available only if Docker has been built with seccomp.
- The kernel should be configured with CONFIG_SECCOMP.

## enable
```
$docker run --rm \
            -it \
            --security-opt seccomp=/path/to/seccomp/profile.json \
            hello-world
```

## run without the default seccomp profile
```
$ docker run --rm -it --security-opt seccomp=unconfined debian:jessie \
         unshare --map-root-user --user sh -c whoami
```
