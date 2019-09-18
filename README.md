# Singularity configuration for simg-rnaseqvariants container

A [Singularity](http://singularity.lbl.gov) definition for rnaseqvariants workflow, available at [https://www.singularity-hub.org/collections/2532](https://www.singularity-hub.org/collections/2532).

If [Singularity](http://singularity.lbl.gov) is installed locally, the container can be build (needs root access) locally like this:

```bash
sudo singularity build simg-rnaseqvariants.simg Singularity > build.log 2>&1
```

The container can also be downloaded from [Singularity Hub](https://www.singularity-hub.org/) without root access to the local machine like this:

```bash
singularity pull --name "simg-rnaseqvariants.simg" sschmeier/simg-rnaseqvariants
```

Then, it can be used, e.g.:

```bash
singularity exec simg-rnaseqvariants.simg samtools view -h
```
