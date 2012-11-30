gopenvpn
--------

gopenvpn is a simple graphical front-end for OpenVPN, the open source
VPN solution.

It provides a GNOME system tray icon from which OpenVPN connections can
be started and stopped, and a dialog from which OpenVPN's logs can
be viewed.  It can manage multiple simultaneous connections, and
graphically indicates when you're connected to a VPN tunnel.

License
-------

gopenvpn is free software released under the GNU General Public License.
See file COPYING for details.

gopenvpn is Copyright (c) 2006 Gary Grossman <gary@softwareasart.com>
                          2012 David Sommerseth <dazo@users.sourceforge.net>

Installing
----------

1. Install prerequisites

The following libraries are prerequisites:

 * glib-2.0
 * gtk+-2.0
 * glade-2.0
 * gnome-keyring (for remembering passphrases)
 * polkit-0.96 (or newer)

The following packages are also prerequisites:

 * gedit (for editing configuration files)

2. Build it

   $ cd gopenvpn
   $ autoreconf -vi
   $ ./configure
   $ make

3. Install it

As root, run:
   # make install

4. To run gopenvpn on login, add /usr/local/bin/gopenvpn to your GNOME
session's startup items.

Configuration Files
-------------------

gopenvpn will look in the directory /etc/openvpn for OpenVPN configuration
files.  OpenVPN configuration files with suffixes ".conf" and ".ovpn"
are recognized.  Any configuration files found will appear in
gopenvpn's context menu.

Using gopenvpn
--------------

You can launch gopenvpn manually

  /usr/local/bin/gopenvpn

... or add it to your GNOME session's startup items so that it starts
up whenever you login to your computer.

Once gopenvpn is loaded, its system tray icon will appear.  The tray
icon appears RED when no connection is active, YELLOW and blinking
when a connection is being made, and GREEN when one or more connections
is active.

Right-click on the tray icon to display the gopenvpn context menu.
The context menu lists all the VPN connections available to connect,
as determined by gopenvpn's scan of the /etc/openvpn directory
for OpenVPN configuration files.

The OpenVPN log for each connection can be viewed in the Details
dialog box, accessible from the "Details..." menu item on the context
menu.  The Details dialog box permits you to tab between connections,
reviewing the log for each, and can also connect/disconnect connections
and edit the configuration file.
