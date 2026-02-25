# Trilium Quadlet

This repository includes the different resources to run a Trilium instance in a container using Podman Quadlet.
The Trilium instance is running within a Pod.

## How to use

Before starting, take time to read carefully the [Trilium Documentation](https://docs.firefly-iii.org/how-to/firefly-iii/installation/docker/)

By default not secret is needed by this Pod.

Then, check quadlet file in the quadlet folder. Check that port, volume and environment are compatible with the current setup. From this folder copy all quadlet file to `~/.config/containers/systemd/`.
One can use the `../install_quadlet` script to perform these actions. If the script is run by `sudo` it will install as rootfull containers.

Finally run the systemd command to start the Pod `systemctl --user start trilium-pod` and check that Trilium application is running `systemctl --user status trilium`.

If everything goes well, then Trilium can be accessed on [http://localhost:8080/](http://localhost:8080/).

One can modify the Pod file to set the network (host, port, etc) and then adjust the reverse proxy configuration.