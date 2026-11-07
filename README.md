# Fogos and Rhodep Android sources

Local manifest for the Motorola SM6375 Linux 6.1 port, on LineageOS 24.0.

Copy `sedona61.xml` to `.repo/local_manifests/` in a LineageOS checkout, then run `repo sync`. It selects the device, vendor, prebuilt kernel and compatibility repositories for both boards. The kernel source manifest is separate so kernel rebuilds do not require syncing the whole ROM.

See the [build guide](https://github.com/Motorola-Sedona61/guide).
