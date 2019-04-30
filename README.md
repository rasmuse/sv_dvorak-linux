Swedish Dvorak for Linux
=========================

![sv_dvorak keyboard layout](sv_dvorak-linux.png)

Based on work by Thomas Lundqvist et al. http://tlundqvist.org/sv_dvorak/

How to use it:
---------------

1. Append the contents of the `sv_dvorak` layout file to the end of `/usr/share/X11/xkb/symbols/se`, e.g. by running

```
sudo bash -c 'cat sv_dvorak >> /usr/share/X11/xkb/symbols/se'
```

2. The layout can now be used by running `sudo setxkbmap se sv_dvorak`.

Adding it to the menus (in Ubuntu/Kubuntu at least):
-------------------------------------------------------

If you want the layout added in the menus, insert the following under `se` layout in `/usr/share/X11/xkb/rules/evdev.xml`:

```xml
        <variant>
          <configItem>
            <name>sv_dvorak</name>
            <description>Swedish (sv_dvorak) [Lundqvist et al.]</description>
          </configItem>
        </variant>
```

In context, it should look something like this:

```xml
    <layout>
      <configItem>
        <name>se</name>
        
        <shortDescription>sv</shortDescription>
        <description>Swedish</description>
        <languageList>
          <iso639Id>swe</iso639Id>
        </languageList>
      </configItem>
      <variantList>

        [...]
        
        <variant>
          <configItem>
            <name>sv_dvorak</name>
            <description>Swedish (sv_dvorak) [Lundqvist et al.]</description>
          </configItem>
        </variant>

        [...]
    </variantList>
</layout>
```

Want to contribute?
----------------------

You are most welcome. Just send a pull request!