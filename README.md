## BlackBerry 10 Python port

### Current status

* Python 3.2.2 from BlackBerry building and working fine in the [Berrymuch](https://github.com/berryamin/berrymuch) prefix

### Roadmap

* Adapt the patchset for Python 3.4
* Bundle into Berrymuch

### Development

#### Cross-compilation for ARM

* Get an OS supported by the BlackBerry Native SDK (we recommend [32-bit Ubuntu 16.04](http://releases.ubuntu.com/16.04/ubuntu-16.04.6-desktop-i386.iso))
* Install the [BlackBerry Native SDK](https://developer.blackberry.com/native/download/)
* Install a few other packages:
  ```
  sudo apt install mercurial python
  ```
* Clone this repository and run:
  ```
  source ~/path/to/bbndk/bbndk_env.sh
  cd Python-3
  ./build.sh
  ```

#### Running on Berrymuch

* Package it up:
  ```
  cd nto-armv7/accounts/1000/shared/documents/clitools
  zip -yr python-3.2.zip .
  ```
* Transfer the package to your Berrymuch device and install with `pbpkgadd`
* Add to your `~/.profile`:
  ```
  export PYTHONPATH="/accounts/1000/shared/documents/clitools/lib/python3.2:/accounts/1000/shared/documents/clitools/lib/python3.2/lib-dynload"
  ```
* Enjoy

