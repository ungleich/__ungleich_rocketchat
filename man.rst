cdist-type__ungleich_rocketchat(7)
==================================
Setup basic rocketchat

ungleich GmbH <cdist--@--ungleich.ch>


DESCRIPTION
-----------
This cdist type sets up basic rocketchat on the target
and sets up a reverse proxy via nginx.

If the destination rocketchat directory already exists then it
does nothing.
In case of state 'absent' it removes rocketchat destination directory
if exists but does not remove any dependencies.


REQUIRED PARAMETERS
-------------------
None.


OPTIONAL PARAMETERS
-------------------
state
    'present', 'absent', defaults to 'present'.
   
admin-email
    Use this email for first admin email.

admin-pass
    Use this password for first admin password.

hostname
    Use this hostname for rocketchat hostname. Default is target's hostname.

mongodb-key
    mongodb key identifier.

mongodb-keyserver
    mongodb key server.

mongodb-src-uri
    mongodb packages source uri.

mongodb-dist
    mongodb package distribution specification.

nodejs-key-uri
    nodejs key uri.

nodejs-src-uri
    nodejs package source uri. It beats nodejs-version.

nodejs-version
    Use this nodejs-version. Used if nodejs-src-uri is empty. Note that in
    order to use this parameter you need to clear nodejs-src-uri default
    parameter.

port
    Use this port for rocketchat.

bindip
    Bind rocketchat to this IP address/hostname.

rocketchat-uri
    Use this rocketchat uri. It beats rocketchat-version parameter.

rocketchat-version
    Use this rocketchat version. Used if rocketchat-uri is empty. Note
    that in order to use this parameter you need to clear rocketchat-uri
    default parameter.


EXAMPLES
--------

.. code-block:: sh

    # Install basic default rocketchat at specified directory
    __ungleich_rocketchat /root/rocketchat
    # The same thing but use specified first admin pass and email.
    __ungleich_rocketchat /root/rocketchat --admin-email admin@server.com \
        --admin-pass secret
    # Delete existing rocketchat
    __ungleich_rocketchat /root/rocketchat --absent
    # Install basic default rocketchat at specified directory and bind it o
    # localhost.
    __ungleich_rocketchat /root/rocketchat --bindip localhost


SEE ALSO
--------
- `cdist-type(7) <cdist-type.html>`_
- `cdist-type__apt_key(7) <cdist-type__apt_key.html>`_
- `cdist-type__apt_key_uri(7) <cdist-type__apt_key_uri.html>`_
- `cdist-type__apt_source(7) <cdist-type__apt_source.html>`_
- `cdist-type__directory(7) <cdist-type__directory.html>`_
- `cdist-type__file(7) <cdist-type__file.html>`_
- `cdist-type__process(7) <cdist-type__process.html>`_
- `cdist-type__start_on_boot(7) <cdist-type__start_on_boot.html>`_


COPYING
-------
Copyright \(C) 2016 ungleich GmbH (www.ungleich.ch). 
Free use of this software is granted under the terms 
of the GNU General Public License version 3 (GPLv3).
