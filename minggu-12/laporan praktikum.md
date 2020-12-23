

https://github.com/jauhmad/tekn-cloud-computing/blob/master/minggu-12/laporan%20praktikum.md
# Laporan Praktikum Teknologi Teknologi Cloud Computing - Minggu 12

## Materi

**Podman**

## Disusun oleh:
* Nama : Jauhari Ahmad 
* No. Mhs : 205411167 


## Pembahasan Hasil Praktikum 
## Rangkuman dari acara yang ada di https://i.postimg.cc/s2pr1fBJ/acara-estu-cloud.jpg
**Docker is deprecated in Kubernetes**

Docker support in the kubelet is now deprecated and will be removed in a future release. The kubelet uses a module called "dockershim" which implements CRI support for Docker and it has seen maintenance issues in the Kubernetes community. We encourage you to evaluate moving to a container runtime that is a full-fledged implementation of CRI (v1alpha1 or v1 compliant) as they become available.

Kubernetes actually needs inside of the red area. Docker Network and Volume are not used in Kubernetes. Having more features while you never use, itself can be a security risk. The less features you have, the smaller the attack surface becomes.

* CRI runtimes

As I described, CRI is an API that Kubernetes provides to talk to a container runtime in order to create/delete containerised applications. They talk in gRPC via IPC as kubelet and the runtime runs on the same host, and a CRI runtime has responsibility for getting request from kubelet and execute OCI container runtime to run a container. Wait, what? Maybe I should explain with a diagram for this one.

* OCI runtimes

OCI runtimes are responsible for spawning a container using Linux kernel system calls such as cgroups and namespace. You might have heard about runc or gVisor. This is what they are.

* gVisor

gVisor is an OCI runtime that were originally created by Google folks. It actually runs on their infrastructure to run their Cloud services such as Google Cloud Run, Google App Engine(2nd gen), and Google Cloud Functions(and even more!). What's interesting here is that gVisor has a "guest kernel" layer which means a containerised applications cannot directly touch to the host kernel layer. Even if they think they do, they only touch the gVisor's guest kernel. gVisor's security model is actually very interesting and worth reading the official doc.

**Podman**

Podman is an open-source project that is available on most Linux platforms and resides on GitHub. Podman is a daemonless container engine for developing, managing, and running Open Container Initiative (OCI) containers and container images on your Linux System. Podman provides a Docker-compatible command line front end that can simply alias the Docker cli, alias docker=podman.

Containers under the control of Podman can either be run by root or by a non-privileged user. Podman manages the entire container ecosystem which includes pods, containers, container images, and container volumes using the libpod library. Podman specializes in all of the commands and functions that help you to maintain and modify OCI container images, such as pulling and tagging. It allows you to create, run, and maintain those containers created from those images in a production environment.

The Podman service runs only on Linux platforms, however a REST API and clients are currently under development which will allow Mac and Windows platforms to call the service. There is currently a Varlink based remote client which runs on Mac or Windows platforms that allows the remote client to talk to the Podman server on a Linux platform. In addition to those clients, there is also a Mac client. NOTE: the Varlink remote client will be deprecated after the REST API is completed.

At a high level, the scope of libpod and Podman is the following:

* Support multiple image formats including the OCI and Docker image formats.
* Support for multiple means to securely download images including trust & image verification.
* Container image management (managing image layers, overlay filesystems, etc).
* Full management of container lifecycle.
* Support for pods to manage groups of containers together.
* Resource isolation of containers and pods.
