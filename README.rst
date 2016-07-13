Ansible role for SNMPD
#######################
.. sectnum::

Context
========

A role to use SNMPD with Ansible.

Variables
===========

List of variables used in this role :

::

   snmpd_agent_address 
   snmpd_agent_port 
   snmpd_community 
   snmpd_communityv6
   snmpd_location 
   snmpd_contact 
   snmpd_services

   snmpd_proc_configuration:
     - { proc_name, proc_interval }
     
   snmpd_load_configuration:
     - { load_interval }
  
   snmpd_disk_configuration:
     - { disk_path, disk_percentage }
       
   snmpd_trapsink 
   snmpd_trap2sink 

   snmpd_extend_configuration:
     - { snmpd_extend }
  
   snmpd_extend_sh_configuration:
     - { snmpd_extend_sh }
   
   snmpd_master 
   
Example Playbook
==================
::

   - hosts: snmpd

     roles:
     - role: ansible-snmpd

       snmpd_agent_address: 192.168.1.1
       snmpd_agent_port: 161
       snmpd_community: public
       snmpd_communityv6: public #if need IPV6
       snmpd_location: paris
       snmpd_contact: evenssolignac@live.fr
       snmpd_services: 72

       snmpd_view_configuration:
        - { view_name: greneta, oid_tree: .1.3.6.1.4.1 }

       snmpd_proc_configuration:
        - { proc_name: mountd, proc_interval: 2 }

       snmpd_load_configuration:
        - { load_interval: 12 1 22 }

       snmpd_disk_configuration:
        - { disk_path: /var, disk_percentage: 70% }
		 
       snmpd_trapsink: localhost public
       snmpd_trap2sink: localhost public

       snmpd_extend: test1   /bin/echo  Hello, world!
       snmpd_extend-sh: test2   echo Hello, world! ; echo Hi there ; exit 35

       snmpd_master: Agentx
     
License
============

MIT_

.. _MIT: LICENSE

Author
=======

Evens SOLIGNAC - evenssolignac@live.fr
   
