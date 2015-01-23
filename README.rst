Ansible Selenium Server
-----------------------

This environment is used to install a Selenium Standalone Server on a virtual
machine, merely for a testing platform.


Requirements
````````````

- `Vagrant <http://www.vagrantup.com/>`_ 1.5 or higher has to be installed.
- `Ansible <http://www.ansible.com/>`_ 1.8 or higher has to be installed.
- As the installation work only for `Virtualbox <https://www.virtualbox.org/>`_,
  you will need to install it.


Setup
`````

Run the following command in the directory containing the ``Vagrantfile``:

.. code-block:: bash

    $ vagrant up

Vagrant will launch a VM and install:

- Java
- Selenium Standalone Server (with Chromedriver)
- Xvfb (with a service for Selenium)
- Chromium
- Firefox

It can take between 5 to 10 mins depending on the amount of RAM you have on
your computer, the hard disk drive I/O speed and your Internet connection
speed.

Once the installation has completed, the Selenium Server is available at
`http://172.16.3.10:4444/wd/hub/ <http://172.16.3.10:4444/wd/hub/>`_.
