# alchemist-apprentice-wasm

## How to Deploy

In main game repo:
```bash
cd alchemist_apprentice
cargo build --release --target wasm32-unknown-unknown
wasm-bindgen --out-dir ./out/ --target web .\target\wasm32-unknown-unknown\release\alchemist_apprentice.wasm
```

This will output a ./out/ directory in that repo's directory. Next copy over `./out` directory to this repo, commit, and then push. GitHub pages will auto deploy it from there. 

```bash
cd ..
rm -rf ./alchemist_apprentice-wasm/out
cp -R ./alchemist_apprentice/out ./alchemist_apprentice-wasm/out
cd alchemist_apprentice-wasm
git stage .
git commit -m "<release_version>"
git push
```