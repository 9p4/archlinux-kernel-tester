# Archlinux Kernel Tester

A custom archiso to run 7zip benchmarks on four different kernels:

- Stable (Normal kernel (no modifications) latest: 5.12.5.arch1-1
- Hardened (Security focused) latest: 5.11.21.hardened1-2
- Realtime (Optimized for real time workloads) latest: linux-rt-5.11.4.11.arch1-2
- Zen (Everyday-esque kernel) latest: 5.12.5.zen1-1

For the AP Statistics 2020-2021 ANOVA PBA

## Building

Because Linux-RT isn't available in the official repositories, it must be compiled from the AUR and loaded into a custom repository. Edit `pacman.conf` to point to that location. [Archwiki Guide on a custom local repository](https://wiki.archlinux.org/title/Pacman/Tips_and_tricks#Custom_local_repository). Just copy over the finished zst files from the `makepkg -s` command (in the linux-rt git aur root) to the repo. Naturally, this has to be compiled on the same architechture you are targeting (x86_64, probably). Then, generate the ISO with `sudo mkarchiso -v -w workdir -o out baseline`.

## Credits

Much thanks to the [ArchWiki](https://wiki.archlinux.org/title/Archiso) for showing me how to do this.
