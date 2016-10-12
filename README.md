# **This directory contains an Ansible playbook that will deploy a alerting, telemetry and correlation monitoring solution.**

###CONTRIBUTING


1. Fork it.
2. Create your feature branch (`git checkout -b my-new-feature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin my-new-feature`).
5. Create new Pull Request.


Quickstart: Run the demo
------------------------
(This assumes you are running Ansible 1.9.4 and Vagrant 1.8.4 on your host.)

    Create the virtual network:
    git clone https://github.com/cumulusnetworks/cldemo-vagrant
    cd cldemo-vagrant
    vagrant up oob-mgmt-server oob-mgmt-switch leaf01 leaf02 leaf03 leaf04 spine01 spine02 server01 server02 server03 server04
    vagrant ssh oob-mgmt-server
    sudo su - cumulus
    sudo apt-get install software-properties-common -y
    sudo apt-add-repository ppa:ansible/ansible -y
    sudo apt-get update
    sudo apt-get install ansible -qy
    -
    Setting up the base network:
    git clone https://github.com/cumulusnetworks/cldemo-automation-ansible
    cd cldemo-automation-ansible
    git checkout full-reference-topology
    ansible-playbook run-demo.yml
    ssh server01
    wget 172.16.2.101
    cat index.html
    exit to oob-mgmt-server
    -
    Specific to Monitoring:
    cd..
    git clone https://github.com/CumulusNetworks/monitoring-project/
    cd health-monitoring-checks/
    git checkout influx-grafana
    cd cldemo
    ansible-playbook main.yml
    -
    Getting to the Dashboard:
    With VirtualBox or Vagrant, forward port 3000 on the NAT enabled NIC for the Grafana dashboard. Also port forward 8083 for the influxDB dashboard and 8086 for the influxDB API if you plan on accessing influxDB with the browser.
    Open a web browser on your local machine, navigate to http://localhost:3000 . Once logged in, click on the grafana logo in the top right of the browser. Navigate the drop down menu to dashboards, then import. 
    Import the json file from /health-monitoring-checks/cldemo/roles/mgmt/files/dashboards . 

## License and Authors

* Author:: Cumulus Networks Inc.

* Copyright:: 2015 Cumulus Networks Inc.

Licensed under the MIT License.

---

![Cumulus icon](http://cumulusnetworks.com/static/cumulus/img/logo_2014.png)

### Cumulus Linux

Cumulus Linux is a software distribution that runs on top of industry standard
networking hardware. It enables the latest Linux applications and automation
tools on networking gear while delivering new levels of innovation and
ﬂexibility to the data center.

For further details please see:
[cumulusnetworks.com](http://www.cumulusnetworks.com)

