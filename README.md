# First Boot Setup #

When distribution starts for the first time, it won't automatically connect
to the public Tor network. This is useful for users who want to hide Tor from
their ISP. Anon Connection Wizard is automatically started, which educates
about different methods to connect (public Tor network, bridges, etc.).

Also automatically starts the Distribution Repository Tool (if installed), so
the user can decide whether to use Distribution's Repository and if yes,
choose which one.

## How to install `setup-wizard-dist` using apt-get ##

1\. Download the APT Signing Key.

```
wget https://www.kicksecure.com/derivative.asc
```

Users can [check the Signing Key](https://www.kicksecure.com/wiki/Signing_Key) for better security.

2\. Add the APT Signing Key..

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add the derivative repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.kicksecure.com bullseye main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `setup-wizard-dist`.

```
sudo apt-get install setup-wizard-dist
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions.

NOTE: Replace `generic-package` with the actual name of this package `setup-wizard-dist`.

* **A)** [easy](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.kicksecure.com)
* [Professional Support](https://www.kicksecure.com/wiki/Professional_Support)

## Donate ##

`setup-wizard-dist` requires [donations](https://www.kicksecure.com/wiki/Donate) to stay alive!
