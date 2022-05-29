# AUR package for azure functions core tools
This repo contains an Arch User Repository package for Azure Functions Core Tools following the next standard for the installation:

1. App files directory: `/usr/share/azure-functions-core-tools`
2. Executable `func` directory: `/usr/bin/func`

* The executable in `/usr/bin` is installed as symbolic link to the `func` bin inside the app files.

## * Notes

This package proceeds with the installation as described in [Azure Functions Core Tools](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=v4%2Clinux%2Ccsharp%2Cportal%2Cbash)

This package may differ from the "official" in the AUR repository in the directories used for the installation and the steps used. The purpose of this package and others 
ones in this account is for install all the programs that I used following certain standard (i.e. using `/usr/share/{pkgname}` for app files and `/usr/bin/{execname}`
for executable) and in some cases clean the installation steps from some bloat.
