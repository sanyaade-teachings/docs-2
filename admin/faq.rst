.. _FAQ:

FAQ - Frequently Asked Questions
================================

Does Veyon run under Chrome OS (ChromeBooks) or MacOS?
------------------------------------------------------
Currently Veyon is only available for Linux or Windows based environments. However, one goal among others in the process
of further development is to port Veyon to other platforms and provide respective installation files.
In this context the Veyon project is dependent on support from experienced software developers, especially for
porting Veyon to MacOS and Android.

How can I add computers in order to access them?
------------------------------------------------

If the preconfigured :ref:`network object directory` is used, the only action required is adding the respective
rooms and computers on the configuration page :ref:`local data`. Afterwards the added resources are available 
to the Veyon master. 

If :ref:`LDAP/AD Integration <LDAP>` is configured the network object register has to be reconfigured to LDAP in
order to make the computers listed in the register available to the Veyon master.

.. index:: iTALC

How can I migrate an existing iTALC installation to Veyon?
----------------------------------------------------------

Although iTALC and Veyon are conceptually similar, a complete reinstall and reconfiguration is necessary to use Veyon,
because configuration and file formats as well as their paths have changed and are not compatible with each other.
For a migration iTALC has to be uninstalled completely at first. It is recommended to reboot the computer thereafter.
Afterwards Veyon can be installed and configured analogously to iTALC.

Whilst the configuration of authentication methods is very similar, the configuration of rooms and computers is 
done via the Veyon configurator and not via the master anymore. In this context you should check, whether the new
:ref:`LDAP/AD Integration <LDAP>` can be used to make rooms and computers automatically available in Veyon.

Is it possible to use Veyon Master on multiple computers?
---------------------------------------------------------

The usage of Veyon Master on multiple computers is possible without any problems. For this to work an identical configuration has to be used on all master computers like its required for client computers in general. If logon authentication is used no further steps are necessary. If key authentication is used the same private key has to be distributed to all master computers.

How can an existing VNC server be used in conjunction with Veyon?
-----------------------------------------------------------------

In some environments a VNC server is already installed (e. g. UltraVNC) or is being provided by the system (e. g. VNC-based access to virtual desktops in VDI environments). This can lead to performance losses or conflicts with the Veyon-internal VNC server in some circumstances. In such cases it's recommended to configure Veyon to use the existing (external) VNC server instead of starting its internal VNC server. The configuration is done through the Veyon Configurator in the configuration page :ref:`Service configuration` in section :ref:`VNCServer`.

Can I import or use a self-generated file with room and computer information?
-----------------------------------------------------------------------------

This is not possible with Veyon 4.0, but Veyon 4.1 will provide a an import feature as well as a command line interface for room and computer administration.

How can I view or control all monitors of a remote computer?
------------------------------------------------------------

On Windows by default only the primary monitor of a computer is accessible with Veyon. You can however change this behaviour in the :ref:`VNCServer` configuration. Select the VNC server plugin :guilabel:`Builtin VNC server` and activate the option :guilabel:`Enable dual monitor support`.

How can I import or export the selection of displayed computers?
----------------------------------------------------------------

The selection of displayed computers is saved in the personal :ref:`User Configuration <User Configuration>`.
To extend this more multiple user, there a two options. First, the user configuration file can be copied into the
respective profile of the user, using login scripts for example. Second the user configuration can be moved to a
shared directory (e.g. a network drive) and the :ref:`Setting <User Configuration>` has to be changed accordingly,
such that the user configuration is loaded from this directory. However, you have to ensure that the access rights
may have to be changed, for that changes made by the user are not rewritten into the global user configuration.

In this context we point you to the function for :ref:`Automatic switch to current classroom <RoomAutoSwitch>`,
that may permit to realize the desired behavior directly. 

How can I hide the master computer in the room administration?
--------------------------------------------------------------

Just activate the option :ref:`Automatically hide local computer in room administration <AutoHideLocalComputer>`.

What happens if there is no matching access control rule?
---------------------------------------------------------

If there is no previously defined access control rule that matches all activated conditions, access is denied
and the connection is closed. In doing so we prohibit that an attacker may have access because of an unfinished
rule set.

