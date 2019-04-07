# custom-openshift-ansible
Some customized playbooks for OpenShift,

These playbooks are used in the "OpenShift Upgrade via ose-ansible" project (https://github.com/dwatson-rh/openshift-upgrade - to upgrade OpenShift, from 3.9 to 3.10 and 3.11, automatically, via the "ose-ansible" docker container).

They are called by the 'upgrade_ocp.sh' script, in the 'custom-ose-ansible-<openshift_version>' docker container, to: 
* Rollout a new docker configuration
* Clean old etcd backups (free up space in /var/lib/etcd)
* Change hostname (from short name) to FQDN
* Pull (base) docker images, uniquely for masters, infra nodes and app/compute/worker/minion nodes
* Backup certain files, uniquely for masters, infra nodes and app/compute/worker/minion nodes
* Configure yum to use the local repo, only

