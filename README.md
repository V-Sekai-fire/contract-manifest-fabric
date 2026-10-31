Google `repo` manifests for the fabric stack. Each variant checks out a different set of repos.

| variant | `-m` file | repos |
|---|---|---|
| Steam Deck (default) | `default.xml` | backend, steamos |
| Steam Deck | `steamos.xml` | backend, steamos |
| Steam Frame | `frame.xml` | backend, steamos (aarch64 needs FEX, untested) |
| container | `container.xml` | backend, runtime (the bootc host repo joins once it is renamed) |
| garment fit build | `garment-fit.xml` | backend, plus the repos that build `fit.elf`: meshing-pen, guest-runtime, guest-common, ggml, ggml-rd, lean-slang, curvenet, lasso, usd-guest, garment-fit, cloth-fit, riscv64-sysroot |

    repo init -u https://github.com/V-Sekai-fire/contract-manifest-fabric -m container.xml
    repo sync

Rows follow branches (`main`), not SHA pins.
