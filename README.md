# Fedora Silverblue FAQ

## Glossary

**Image**: the system files that cannot be changed by the user. In Fedora Silverblue and Kinoite, this includes everything but `/var` and `/etc`.

**Layering**: installing packages system-wide on image-based operational systems. In Fedora Silverblue, layering is done using the command `rpm-ostree`.

**Base image**: any image provided

## Questions and Answers
- Is there an easy way to tell how much storage a given toolbox is taking

> ```
> podman container inspect -s terratest --format "{{.SizeRw}}" | numfmt --to iec --format "%10.3f"
> ```


- How do I make sure the latest ostree deployment is not automatically deleted

> ```
> sudo ostree admin pin 0
> ```

- How to increase the number of deployments preserved by ostree by default?

>

- How do I get to the boot menu?

> Press Esc or Shift repeatedly as your computer boots. Alternatively, if you are able to start a graphical environment, you can hold the Alt key on GNOME's restart dialog. This will show a button named "Boot options" that will take you to GRUB once pressed.

- Why is "Downloaded size" different from "Installed size" in `dnf`?

> Downloaded packages are compressed, so they need to be decompressed to be installed.

- How can I have different `.bashrc` configurations for toolbx?

> You can check for the existence of two files: `run/.containerenv` and `/run/.toolboxenv`. Here's an example snippet, that sources different aliases if you are inside a toolbox.
> ```
>
> ```

- How can I make a GNOME Terminal profile automatically enter a specific toolbox?

>

- How can I integrate VS Code into my toolbox environment?

>

- How can I configure my firewall with a Graphical User Interface (GUI)?

> You can install a package called `firewall-config` system-wide using `rpm-ostree` like so:
>
> ```
> rpm-ostree install firewall-config
> ```
>
> Alternatively you can evoke `nm-connection-editor` in a terminal, which will open an app that allows configuring firewall "Zones" for each of your known connections. This option does not require layering any packages, but it is less fully-featured than `firewall-config`.

- How can I check the packages that changed between ostree deployments

> ```
> rpm-ostree db diff <INDEX>
> ```

- How to enable automatic updates on Fedora Silverblue?
> To enable updates to
