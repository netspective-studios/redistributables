# Daff binary

[daff](https://github.com/paulfitz/daff) is library for comparing tables, producing a summary of their differences and `daff-haxe2cpp-1.3.46-amd64-debug` is result of [daff](https://github.com/paulfitz/daff) `make cpp` and is symlinked to bin/daff by `install-data-engr.sh`.

To rebuild on Linux:

```bash
asdf plugin add haxe
asdf plugin add neko
asdf install haxe latest
asdf install neko latest
asdf shell haxe latest
asdf shell neko latest
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$(asdf where neko)
mkdir -p /tmp/engrsb-build
cd /tmp/engrsb-build
git clone https://github.com/paulfitz/daff
cd daff
make cpp
```

If there are no errors, the binrary will be placed into `./bin/Coopy-debug`, get the version and copy the latest to `redistributables/linux` directory:

```bash
./bin/Coopy-debug version
cp ./bin/Coopy-debug $HOME/.engrsb/dist/daff-1.3.46-haxe2cpp-amd64-debug
```