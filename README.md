# Forked

Forked from github.com/tmc/keyring to use updated https://github.com/godbus/dbus instead of https://github.com/guelfey/go.dbus

# keyring provides cross-platform keychain access

http://godoc.org/github.com/dougEfresh/keyring

Keyring provides a common interface to keyring/keychain tools.

License: ISC

Currently implemented:
- OSX
- SecretService
- gnome-keychain (via "gnome_keyring" build flag)

Contributions welcome!

Usage example:

```go
  err := keyring.Set("libraryFoo", "jack", "sacrifice")
  password, err := keyring.Get("libraryFoo", "jack")
  fmt.Println(password) //Output: sacrifice
```

## Linux

Linux requirements:

### SecretService provider

- dbus

### gnome-keychain provider

- gnome-keychain headers
- Ubuntu/Debian: `libsecret-dev`
- Fedora: `libsecret-devel`
- Archlinux: `libsecret`

Tests on Linux:
```sh
 $ go test github.com/dougEfresh/keyring
 $ # for gnome-keyring provider
 $ go test -tags gnome_keyring github.com/dougEfresh/keyring
```

