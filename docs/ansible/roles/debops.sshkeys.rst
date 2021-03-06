debops.sshkeys
##############



``debops.sshkeys`` role can be used to manage users SSH keys in
``/etc/ssh/authorized_keys/`` directory. This role is required for SFTPonly
accounts created by ``debops.sftpusers`` role to disallow access to
``~/.ssh/authorized_keys`` for users themselves.

.. contents:: Table of Contents
   :local:
   :depth: 2
   :backlinks: top

Installation
~~~~~~~~~~~~

This role requires at least Ansible ``v1.7.0``. To install it, run::

    ansible-galaxy install debops.sshkeys




Role variables
~~~~~~~~~~~~~~

List of default variables available in the inventory::

    ---
    
    # System-wide authorized_keys directory
    sshkeys_path: '/etc/ssh/authorized_keys'
    
    # Lists of authorized_keys entries for users
    # They will be put in /etc/ssh/authorized_keys/ directory per user
    # Format is the same for all lists
    
    # List for "global" entries
    sshkeys_list: []
    
      #- name: 'username'
      #  sshkeys: [ 'ssh-rsa AAAAB3NzaC1...', '{{ lookup("file","~/.ssh/id_rsa.pub") }}' ]
      #  options: 'key-options'	# optional
      #  state: 'present'		# optional, choice: present,absent
    
    # List for "group" entries (only 1 group at a time)
    sshkeys_group_list: []
    
    # List for "host" entries
    sshkeys_host_list: []




Authors and license
~~~~~~~~~~~~~~~~~~~

``debops.sshkeys`` role was written by:

- Maciej Delmanowski | `e-mail <mailto:drybjed@gmail.com>`__ | `Twitter <https://twitter.com/drybjed>`__ | `GitHub <https://github.com/drybjed>`__

License: `GPLv3 <https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29>`_

