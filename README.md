# Fogos and Rhodep Android sources

Local manifest for the Motorola SM6375 Linux 6.1 port, on LineageOS 24.0.

Copy `sedona61.xml` to `.repo/local_manifests/` in a LineageOS checkout, then run `repo sync`. It selects the device, vendor, prebuilt kernel and compatibility repositories for both boards. The kernel source manifest is separate so kernel rebuilds do not require syncing the whole ROM.

See the [build guide](https://github.com/Motorola-Sedona61/guide).

## Halcyon fogos

Use `halcyon-fogos.xml` as the only Sedona local manifest for Halcyon 17.0. It includes the fogos device/prebuilt/vendor dependencies, fogos-only Moto Camera package, and the reviewed Halcyon framework, vendor and Qualcomm common forks. It preserves Halcyon common linkfiles and uses prebuilt kernels.

```sh
mkdir -p .repo/local_manifests
curl -fL https://raw.githubusercontent.com/Motorola-Sedona61/local_manifests/main/halcyon-fogos.xml -o .repo/local_manifests/halcyon-fogos.xml
repo sync
```

Remove a previously installed `sedona61.xml`/`motocam.xml` before using this standalone manifest, to avoid duplicate project declarations. For an existing checkout switching the camera/framework repository names, back up local changes before a targeted `repo sync --force-sync vendor/motorola/camera frameworks/av`.
