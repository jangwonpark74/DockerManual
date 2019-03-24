# Docker NetworkID 
- Added NetworkID for docker inspection

# Docker Network-scoped alias 

```
$ docker network connect --alias scoped-app local_alias container6
```

multiple containers can share the same network-scoped alias within the same network
```
$ docker run --net=isolated_nw -itd --name=container7 --net-alias app busybox 
3138c678c123b8799f4c7cc6a0cecc595acbdfa8bf81f621834103cd4f504554
```

# Docker Client API

```
github.com/docker/docker/cli
github.com/docker/components/engine/api/client 
```

# Docker volumn mount propagation option
```
Allow passing mount propagation option shared, slave, or private as volume
property.

For example.
docker run -ti -v /root/mnt-source:/root/mnt-dest:slave fedora bash
```

# seccomp security profile
- [Secure Computing Mode](https://docs.docker.com/engine/security/seccomp/)

- This feature is available only if Docker has been built with seccomp.
- The kernel should be configured with CONFIG_SECCOMP.

## pass a profile for a container 
```
$docker run --rm \
            -it \
            --security-opt seccomp=/path/to/seccomp/profile.json \
            hello-world
```

### seccomp: what it does?
- By default it disable around 44 systemcall from 300+ system calls.

## run without the default seccomp profile
```
$ docker run --rm -it --security-opt seccomp=unconfined debian:jessie \
         unshare --map-root-user --user sh -c whoami
```
