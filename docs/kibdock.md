# KIBDock

KIBDock is the containerization software that comes with KIB in Batch.

## 1. Initializing KIBDock

Initialize the KIBDock service in the KIB in Batch shell:

```bash
kibdock init
```

You can then get help information about it:

```bash
kibdock help
```

## 2. Creating and deploying a KIBDock container

Create the KIBDock container:

```bash
kibdock create # It will prompt you for container and image name
```

Deploy the KIBDock container:

```bash
kibdock deploy # It will prompt you for container name
# This will drop you into an interactive shell for the container
```
