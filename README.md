# Linux-subsystem-for-windows-Cross-Compilation
A guide to compile windows programs on linux.

## Windows Installation


### Windows SSH key authentication

To make the authentication by identity to work you need to make some changes in the permissions in the files:

First you need to create an text file called **authorized_keys** and put there your .pub keys content, save it as UTF-8 (without BOM (you can do so creating the file with code or vim and editing with it, dont use notepad or other windows programs, they always fuck something up)) .

Second, you need to change some permissions:
  - Go to the proprieties of the file > Security > Advanced...
  - Disable inherance > Convert ....
  - Remove Administrators and any other users that are not yourself and the SYSTEM
  - and apply

If you want to login with an user with administrator priviledges copy the **authorized_keys** to **$programdata$/ssh** and change the name to **administrators_authorized_keys**
and keep only **SYSTEM** and **Administrators**.

# Cross compilation without VM

## C++

TODO

## Rust

For rust you just need to add your targets, dont forget the follow the c++ guide to have mingw, you will need it.

```bash
# install cargo if didn't yet:
curl https://sh.rustup.rs -sSf | sh

# to list all the possible targets:
rustc --print=target-list

# add the targets for x64 and it's install the toolchain
rustup target add x86_64-pc-windows-gnu
rustup toolchain install stable-x86_64-pc-windows-gnu

# add the targets for x86 and it's install the toolchain
rustup target add i686-pc-windows-gnu
rustup toolchain install stable-i686-pc-windows-gnu

# you can install also other channels of toolchain, stable, beta and nightly are the options

# now for compilation you just to need to add the target to the end of the cargo command:
cargo build --release  --target x86_64-pc-windows-gnu
# or
cargo build --release --target i686-pc-windows-gnu
```
