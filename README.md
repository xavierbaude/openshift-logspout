# openshift-logspout
A logspout kubernetes daemonset to ship logs from docker.sock and send it to a syslog server (graylog, logstash, syslog daemon...)

# Setup
Edit the file daemonset-logspout.yaml and change these values:
<syslog_IP>
<syslog_port>
Then,

    oc project <project_name> 
    oc create sa logspout 
    oc adm policy add-scc-to-user privileged -z logspout
    oc create -f daemonset-logspout.yaml
     
# tag
log kubernetes openshift docker.sock logspout
