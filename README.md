# fabric8-jkube-migration

JKube 1.9.1 does not support `<buildx>` but Fabric8 does.

## Instructions

```
mvn install
docker run neil/fabric8
docker run neil/jkube
```

## Actual

If run on a Mac with an M1 chip:

* Fabric8 produced Docker image reports `x86_64`, the requested target architecture.
* JKube produced Docker image reports `aarch64`, the build architecture.

If the `<buildx>` section is included for JKube, then JKube 1.9.1 reports:

```
Cannot find 'buildx' in class org.eclipse.jkube.kit.config.image.build.BuildConfiguration
```

## Desired

JKube to report `x64_64`, the requested target architecture.

