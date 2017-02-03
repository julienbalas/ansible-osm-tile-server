# ansible-osm-tile-server
Ansible playbook to install an OSM server tile

It's the content of https://wiki.debian.org/OSM/tileserver/jessie in ansible.

Params 
- the name of the file to import

usage (for now)
vagrant up
or 
vagrant provision
 
Roadmap (TODO)
- use the minute-diff to get the database in sync (with filtering according to your area)
- monitoring using cacti/munin/not-yet-decided
- purge
- prerender areas