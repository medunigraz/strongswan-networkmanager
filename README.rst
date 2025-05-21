Strongswan with Network-Manager
===============================

In order to connect to the Medical University of Graz VPN on Checkpoint one needs to make small changes to the Strongswan configuration.

Debian & Ubuntu
---------------

Install the following packages:

::

  sudo apt install strongswan-charon libstrongswan-extra-plugins libstrongswan-standard-plugins network-manager-strongswan libcharon-extra-plugins

Copy the `mug.conf` file from this repository to `/etc/strongswan.d/`:

::

  sudo cp mug.conf /etc/strongswan.d/

Now you can configure a new Strongswan connection in Network-Manager. Use the `vpn.medunigraz.at.crt` from this repository as the certificate.

Connection settings
-------------------

.. list-table:: Settings
   :widths: 15 30
   :header-rows: 1

   * - Setting
     - Value
   * - Gateway
     - vpn.medunigraz.at
   * - Certificate
     - vpn.medunigraz.at.crt
   * - Identity
     - <empty>
   * - Method
     - EAP
   * - Username
     - o<name>
   * - User Password
     - Ask for this password every time
   * - Request an inner IP address
     - yes
   * - Enable UDP encapsulation
     - yes
   * - Enable Custom Cipher Proposals
     - yes
   * - IKE
     - aes256-sha1-modp1024
   * - ESP
     - aes128-sha1

