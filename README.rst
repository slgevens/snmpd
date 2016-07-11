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
	
   snmpd_proc
   snmpd_disk
   snmpd_load
   
   snmpd_trapsink 
   snmpd_trap2sink 

   snmpd_extend 
   snmpd_extend-sh 
   
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

       snmpd_view_configuration: []


       snmpd_proc_configuration: []
       snmpd_load_configuration: []
       snmpd_disk_configuration: []

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
   
