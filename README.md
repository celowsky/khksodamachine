Soda machine RFID program built with NodeJS

===DATABASE===
The soda machine uses a RethinkDB to keep track of purchases made by members
of KHK with their Wiscards.
- Contains two tables (members and purchases)
- Run via rethinkdb --directory /home/admin/rethinkdb1
- Can access administration tools at kappa on port 8080
- Set up as a systemd service on kappa in /etc/systemd/system/rethink.service

===SODASERVER===
- Sets up connection between Arduino Uno inside the soda machine and
  kappa
- Run via /home/admin/soda-machine/bin/sodaserver
- Set up as a systemd service on kappa in /etc/systemd/system/sodaserver.service

===WWW===
- Creates a simple HTML output for purchase amounts made by each member on a
  monthly basis
- Accessed on kappa on port 8082
- Set up as a systemd service on kappa in /etc/systemd/system/sodawww.service

===CHATEAU===
- GUI tool to make managing the RethinkDB easier
- Accessed at kappa on port 8081
- Set up as a systemd service on kappa in /etc/systemd/system/chateau.service
