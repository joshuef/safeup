# safeup

Simple utility for installing and updating safe-related components.

## Install

### Linux/macOS

You can choose to run the installation for `safeup` as the current user or with `sudo`. The difference between them is the install location and modification of the shell profile. If running with `sudo`, `safeup` will be installed to `/usr/local/bin`; otherwise it will be installed to `~/.local/bin` and the Bash shell profile will be modified to add that location to the `PATH` variable. For almost any Linux-based or macOS installation, `/usr/local/bin` is already available on `PATH` as standard.

To install as `sudo`, use the following:
```
curl -sSL https://raw.githubusercontent.com/maidsafe/safeup/main/install.sh | sudo bash
```

Otherwise:
```
curl -sSL https://raw.githubusercontent.com/maidsafe/safeup/main/install.sh | bash
```

This process will download and install `safeup` for your platform, then run it to have it install the `safe` client binary.

The install script also accepts two flag arguments, namely `--client` and `--node`. If either are used, the script will invoke the installed `safeup` binary to install `safe` and `safenode`, respectively, without having to run either as an additional post-install step.

To use these options as `sudo`:
```
curl -sSL https://raw.githubusercontent.com/maidsafe/safeup/main/install.sh | sudo bash -s -- --client
```

Otherwise:
```
curl -sSL https://raw.githubusercontent.com/maidsafe/safeup/main/install.sh | bash -s -- --client
```

### Windows

On Windows, we are currently not supporting installing either `safeup` or the other binaries with Administrator privileges, so there is only one command:
```
iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/maidsafe/safeup/main/install.ps1'))
```

The Powershell installer does not support the `--client` or `--node` arguments because it's not possible to pass them when the script is downloaded.

Therefore, installing any components on Windows is an additional post-safeup-installation step.

## Usage

Use the `client`, `node` or `testnet` commands to install the latest versions of the `safe`, `safenode` or `testnet` binaries, respectively. 

As above, you can choose to run `safeup` using `sudo`, depending on where you'd like your binaries installed. Again, this does not apply to Windows, where we don't support running with Administrator privileges.

## License

This Safe Network repository is licensed under the General Public License (GPL), version 3 ([LICENSE](LICENSE) http://www.gnu.org/licenses/gpl-3.0.en.html).

See the [LICENSE](LICENSE) file for more details.
