# Daff binary

`daff-haxe2cpp-1.3.46-amd64-debug` is result of [daff](https://github.com/paulfitz/daff) `make cpp` and is symlinked to bin/daff by `install-data-engr.sh`

To rebuild:

```bash
asdf plugin add haxe
asdf plugin add neko
asdf install haxe latest
asdf install neko latest
export PATH=$PATH:$HOME/.engrsb/haxe:$HOME/.engrsb/neko
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$HOME/.engrsb/neko
mkdir -p /tmp/engrsb-build
cd /tmp/engrsb-build
git clone https://github.com/paulfitz/daff
make cpp
```

If there are no errors, the binrary will be placed into `./bin/Coopy-debug`, get the version and copy the latest to `redistributables/linux` directory:

```bash
./bin/Coopy-debug version
cp ./bin/Coopy-debug $HOME/.engrsb/dist/daff-1.3.46-haxe2cpp-amd64-debug
```