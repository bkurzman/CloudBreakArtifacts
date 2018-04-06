Instructions for setting up twitter demo on open stack cluster:

1.	Set up a 3 node cluster in open stack using m3.xlarge sizes
2.	SSH into one of the nodes
3.	In the root user, run the below commands. Answer all the prompts accordingly
  a.	yum install wget 
  b.	yum instasll git clone
4.	Download the ambari repo for ambari 2.5.2.0
  a.	wget -nv http://public-repo-1.hortonworks.com/ambari/centos7/2.x/updates/2.5.2.0/ambari.repo -O       /etc/yum.repos.d/ambari.repo
5.	Install the server with the below command. Answer all prompts accordingly
  a.	yum install ambari-server
6.	Set up the server with the below command. Answer all prompts accordingly
  a.	ambari-server setup
7.	Start the server
  a.	ambari-server start
8.	Navigate to the ambari UI. In the installation wizard select to use HDP-2.6.2.0
9.	Continue with all the default settings and add your other computing instances to your cluster.
10.	When selecting services, select to add the following services
  a.	HDFS
  b.	Yarn
  c.	MapReduce2
  d.	Tez
  e.	Hive
  f.	HBase
  g.	Pig
  h.	ZooKeeper
  i.	Storm
  j.	Ambari Infra
  k.	Atlas
  l.	Kafka
  m.	Slider
11.	Use the default configs for all of these services
12.	Launch the cluster
13.	Once launched, in the terminal 
  a.	git clone https://github.com/bkurzman/CloudBreakArtifacts
  b.	cd CloudBreakArtifacts/recipes/
  c.	chmod +x hdp-hdf-post-install.sh
  d.	./hdp-hdf-post-install.sh
14.	Add the demo as a service as you normally would through the demo store
