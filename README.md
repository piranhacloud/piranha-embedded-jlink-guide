
# Piranha Embedded JLink application

See [Create an Piranha Embedded JLink application](https://piranha.cloud/web-profile/guides/rest)
for the step by step guide. This repository contains the resulting project for 
your reference.


## Assembling the runtime image

### ModiTect

The [Moditect](https://github.com/moditect/moditect) Maven plugin can create a runtime image using jdeps and jlink.
This is the configuration explained in the guide linked above. You simply invoke the following command:

```
mvn -Pmoditect clean verify
```

The runtime image will be located at `target/jlink`.

### JReleaser

The [JReleaser](https://jreleaser.org/guide/latest/tools/jreleaser-maven.html) Maven plugin can also assemble runtime
imaes with jdeps and jlink. The added benefit is that it can be configured to generate multiple cross-platform runtimes
within the same environment. However, this it's not shown in this particular example. To generate a runtime image
matching the JDK and platform used to run the build simply execute the following command

```
mvn -Pjreleaser clean verify
```

The runtime image will be located at `target/jreleaser/assemble/helloworld/jlink`.
