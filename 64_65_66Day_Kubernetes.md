---
title: 64_65_66Day_Kubernetes
uuid: abc18960-4969-11ef-90df-6ef34fa959ce
version: 1004
created: '2024-07-24T08:36:06+05:30'
tags:
  - kubernetes
---

# <mark style="background-color:#F8914D;">**Monitoring Intro**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![34c297b0-4d53-4d71-a514-11160cdf1ae4.png|905](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/34c297b0-4d53-4d71-a514-11160cdf1ae4.png) [^1]

![25e7b1e9-0247-4b65-b077-c4a7c17f0b33.png|937.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/25e7b1e9-0247-4b65-b077-c4a7c17f0b33.png) [^2]

\

![811d3e29-21be-47c0-9686-d63420561824.png|972](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/811d3e29-21be-47c0-9686-d63420561824.png) [^3]

![f3384154-177e-45e6-8955-a0d48f413dc7.png|969.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/f3384154-177e-45e6-8955-a0d48f413dc7.png) [^4]

![df7c1a50-b781-4af6-8908-9576b337d5d5.png|744](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/df7c1a50-b781-4af6-8908-9576b337d5d5.png) [^5]

\

# <mark style="background-color:#F8914D;">**Four golden signals**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

![12c53e9c-b73a-47f7-bedc-6c95af987c6a.png|854](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/12c53e9c-b73a-47f7-bedc-6c95af987c6a.png) [^6]

\

Saturation -- Prometheus

Latency, traffic, Errors -- ELK

\

# <mark style="background-color:#F8914D;">**Time series Database -**<!-- {"backgroundCycleColor":"24"} --></mark> <mark style="background-color:#F8D616;">Prometheus depends on time series database<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"collapsed":true} -->

![ac5f20e2-86aa-45c7-94ab-be4489f77e34.png|897](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/ac5f20e2-86aa-45c7-94ab-be4489f77e34.png) [^7]

\

# <mark style="background-color:#F8914D;">**Prometheus**<!-- {"backgroundCycleColor":"24"} --></mark> <mark style="background-color:#F8D616;">- Depends on Time series Databases<!-- {"backgroundCycleColor":"25"} --></mark><!-- {"collapsed":true} -->

![f745530f-8c5a-4611-b3a2-e10eece3955a.png|554](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/f745530f-8c5a-4611-b3a2-e10eece3955a.png) [^8]

\

![ea10131e-3687-4c65-bd8a-f91b3e057738.png|863](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/ea10131e-3687-4c65-bd8a-f91b3e057738.png) [^9]

\

\

\

<mark>**Installing prometheus**</mark>

\

**Launch t3.medium instance with 30gb storage.**

![89e960e9-2509-49a3-9a60-026b38f17d46.png|1081.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/89e960e9-2509-49a3-9a60-026b38f17d46.png) [^10]

\

```
sudo su 
cd /opt/
```

![8986633b-d947-4acf-884c-009ed85b27d7.png|750](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/8986633b-d947-4acf-884c-009ed85b27d7.png) [^11]

\

![15291114-bbfb-4950-92ea-490ea620f5fc.png|636](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/15291114-bbfb-4950-92ea-490ea620f5fc.png) [^12]

\

Downloading prometheus file

```
wget https://github.com/prometheus/prometheus/releases/download/v2.53.1/prometheus-2.53.1.linux-amd64.tar.gz 
```

![138a6f4f-d3ac-4be3-a631-de0b51091ee9.png|1125.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/138a6f4f-d3ac-4be3-a631-de0b51091ee9.png) [^13]

\

untar the files

```
ls
tar -xf prometheus-2.53.1.linux-amd64.tar.gz
```

![67249cb3-6f4f-4c0e-af9a-18807910ff11.png|1126.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/67249cb3-6f4f-4c0e-af9a-18807910ff11.png) [^14]

\

```
ls
mv prometheus-2.53.1.linux-amd64 prometheus
ls
cd prometheus
ls -l
```

![27b1db6f-1f2c-4cac-860f-8e16ed931145.png|1126](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/27b1db6f-1f2c-4cac-860f-8e16ed931145.png) [^15]

\

\

Now I am creating sytemctl service for prometheus.

```
vim /etc/systemd/system/prometheus.service
```

```
{Unit]
Description=prometheus service.

[Service]
ExecStart=/opt/prometheus/prometheus --config.file=/opt/prometheus/prometheus.yml

[Install ]
WantedBy=multi-user.target
```

\

![61e7f184-8db9-4e08-ba70-7cc430e3a43d.png|725.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/61e7f184-8db9-4e08-ba70-7cc430e3a43d.png) [^16]

![88b0dd1b-9733-4331-827a-37c25c58a83f.png|1052.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/88b0dd1b-9733-4331-827a-37c25c58a83f.png) [^17]

\

```
systemctl start prometheus
systemctl status prometheus
systemctl enable prometheus
```

![bdabe706-3b09-4e3a-a1ed-c5e4dd316d64.png|1057.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/bdabe706-3b09-4e3a-a1ed-c5e4dd316d64.png) [^18]

![c0f21fc0-6054-4601-b40d-3cc3e6979005.png|1138.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/c0f21fc0-6054-4601-b40d-3cc3e6979005.png) [^19]

\

it runs on 9090 port

```
netstat -lntp
```

![2a42c25d-0c1d-4175-b3fe-b39b55bd6dc3.png|1114.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/2a42c25d-0c1d-4175-b3fe-b39b55bd6dc3.png) [^20]

\

connecting to prometheus

```
3.238.105.76:9090
```

![2537e045-6bc6-412d-aa11-f76d554867de.png|1009](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/2537e045-6bc6-412d-aa11-f76d554867de.png) [^21]

\

Prometheus have query language will learn in further...

\

From when prometheus server is up... you can view from both table and graph.  

**UP =1**

**DOWN =0**

![6e1c0673-da7d-4dc0-99b4-6df01eeb1d37.png|1027.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/6e1c0673-da7d-4dc0-99b4-6df01eeb1d37.png) [^22]

\

last 5min data

![3bc2ee87-863e-4c3c-954d-0fbfb0408247.png|1055.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/3bc2ee87-863e-4c3c-954d-0fbfb0408247.png) [^23]

\

![7a8d4ab4-dc39-4530-b926-3eddc3ec0e43.png|1032.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/7a8d4ab4-dc39-4530-b926-3eddc3ec0e43.png) [^24]

\

\

# <mark style="background-color:#F8914D;">**Monitoring a node in Prometheus**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

\

Create one instance

![6a6764b6-e3cb-4b8d-b43b-8d6d973a880b.png|1087.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/6a6764b6-e3cb-4b8d-b43b-8d6d973a880b.png) [^25]

\

**connect to node**

![1774a006-e7d1-4c02-8a88-40d0db6f594d.png|1077](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/1774a006-e7d1-4c02-8a88-40d0db6f594d.png) [^26]

\

Now we need to install node exporters in the node.

![3ed40650-0c9e-4198-9c8c-47d791e677c4.png|1157.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/3ed40650-0c9e-4198-9c8c-47d791e677c4.png) [^27]

```
sudo su
cd /opt/
wget https://github.com/prometheus/node_exporter/releases/download/v1.8.2/node_exporter-1.8.2.linux-amd64.tar.gz 
```

![a6450acc-7fb4-4d01-932c-263f626c8cee.png|1055.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/a6450acc-7fb4-4d01-932c-263f626c8cee.png) [^28]

\

```
ls
tar -xf node_exporter-1.8.2.linux-amd64.tar.gz 
ls
mv node_exporter-1.8.2.linux-amd64 node_exporter     --> renaming
ls
```

![ea13acef-fd0d-4281-8961-931cd96b370d.png|1055.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/ea13acef-fd0d-4281-8961-931cd96b370d.png) [^29]

\

Creating node exporter service

```
vim /etc/systemd/system/node_exporter.service
```

```
{Unit]
Description=prometheus service.

[Service]
ExecStart=/opt/node_exporter/node_exporter

[Install ]
WantedBy=multi-user.target
```

![db0683c2-ebab-46fd-8820-685f0f150b11.png|824.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/db0683c2-ebab-46fd-8820-685f0f150b11.png) [^30]

![277ec23c-e68d-4099-b6fa-a1d797150d9c.png|597](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/277ec23c-e68d-4099-b6fa-a1d797150d9c.png) [^31]

\

```
systemctl start node_exporter
systemctl status node_exporter
systemctl enable node_exporter
```

![500fa39b-8b43-44c0-a043-a1c73d9f2a73.png|1083.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/500fa39b-8b43-44c0-a043-a1c73d9f2a73.png) [^32]

![9154e530-6e4a-49f6-8d43-38199559403e.png|1158.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/9154e530-6e4a-49f6-8d43-38199559403e.png) [^33]

\

this will run in 9100 port

```
netstat -lntp
```

![09c96599-6679-4251-a628-b28958979252.png|1046.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/09c96599-6679-4251-a628-b28958979252.png) [^34]

\

Node exporter is running continually and getting metrics from its node

![0738fa7b-e01c-4c7b-85c4-a9ff6a8adb47.png|787](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/0738fa7b-e01c-4c7b-85c4-a9ff6a8adb47.png) [^35]

\

Need to update **node exporter** details in prometheus.yml on prometheus server

![f32cf5cf-48d2-4632-9be4-0818a127bcfc.png|716](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/f32cf5cf-48d2-4632-9be4-0818a127bcfc.png) [^36]

\

![5ee65f08-a60c-4147-a0bd-7799909cc1ef.png|903](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/5ee65f08-a60c-4147-a0bd-7799909cc1ef.png) [^37]

\

![381f7003-b31b-4340-829e-2b2eaf80f6fc.png|1102.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/381f7003-b31b-4340-829e-2b2eaf80f6fc.png) [^38]

\

\

Restart the prometheus 

```
systemctl restart prometheus
```

![081c8ec1-65fb-483b-b131-0182d32e92b2.png|1098](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/081c8ec1-65fb-483b-b131-0182d32e92b2.png) [^39]

\

Now you are getting node-exporter alerts

![006093ca-2fab-4710-b133-f8b9d6b93d43.png|1186.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/006093ca-2fab-4710-b133-f8b9d6b93d43.png) [^40]

![ea88f3ab-eda8-4b96-a67a-4a922d02cbb3.png|1177.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/ea88f3ab-eda8-4b96-a67a-4a922d02cbb3.png) [^41]

\

or

![641d0460-d869-474d-aca6-63c593e9d8e2.png|1176.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/641d0460-d869-474d-aca6-63c593e9d8e2.png) [^42]

\

cross check on node

```
free
```

![b89a40e1-6964-462c-9542-9ace4b2b622d.png|1170.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/b89a40e1-6964-462c-9542-9ace4b2b622d.png) [^43]

\

\

# <mark style="background-color:#F8914D;">**Grafana**<!-- {"backgroundCycleColor":"24"} --></mark> -- A nice graph presentation.<!-- {"collapsed":true} -->

It can get data from multiple sources. prometheus is one of the sources.

It's not a big application, if we give data (Time series database (TSDB) to it, then it will show in good graphical presentation.

\

**Prometheus and Grafana is a nice combination.**

\

\

<mark>**Installing Grafana (heavy application) in prometheus server**</mark>

![8a98e754-4015-42a6-84ce-8c6205ab9ba2.png|965.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/8a98e754-4015-42a6-84ce-8c6205ab9ba2.png) [^44]

\

```
wget -q gpg.key https://rpm.grafana.com/gpg/key
sudo rpm --import gpg.key
```

![d31ab299-ca8f-4033-83d3-f370981dd183.png|1057](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/d31ab299-ca8f-4033-83d3-f370981dd183.png) [^45]

\

adding grafana repo

```
vim /etc/yum.repos.d/grafana.repo
```

```
[grafana]
name=grafana
baseurl=https://rpm.grafana.com
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey-https://rpm.grafana.com/gpg.key
sslverify=1
ssicacert=/etc/pki/tls/certs/ca-bundle.crt
```

![3549d466-ab09-4bdf-9379-4b2ba8a5a466.png|745](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/3549d466-ab09-4bdf-9379-4b2ba8a5a466.png) [^46]

![28f4b6fc-dd57-4840-9a32-2131833d6f49.png|628](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/28f4b6fc-dd57-4840-9a32-2131833d6f49.png) [^47]

\

```
sudo dnf install grafana -y
```

![5e37e35c-054b-48b1-83ea-0be50bf0a297.png|1012.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/5e37e35c-054b-48b1-83ea-0be50bf0a297.png) [^48]

\

```
systemctl daemon-reload
systemctl start grafana-server
systemctl status grafana-server
```

![e9bf13fa-1b2d-4de2-90f1-48b5893d34b8.png|1098.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/e9bf13fa-1b2d-4de2-90f1-48b5893d34b8.png) [^49]

\

```
systemctl enable grafana-server
```

![e7cf9507-d68c-4ac9-9280-31c57ab5668a.png|1101.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/e7cf9507-d68c-4ac9-9280-31c57ab5668a.png) [^50]

\

Grafana opens port 3000

```
netstat -lntp
```

![ba190626-5135-4e69-970f-43f830962001.png|1072.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/ba190626-5135-4e69-970f-43f830962001.png) [^51]

\

```
3.238.105.76:3000
username: admin
psw: admin
```

![05da8d37-1a6f-4cbe-9828-1a7f1fae3d82.png|926.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/05da8d37-1a6f-4cbe-9828-1a7f1fae3d82.png) [^52]

\

new password

![c5b69e89-99fa-4814-bf64-d30a0b0aaa95.png|745](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/c5b69e89-99fa-4814-bf64-d30a0b0aaa95.png) [^53]

\

\

Adding prometheus as data source

![5262876d-54d1-4d87-a5d4-f59fe78c80a8.png|1078.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/5262876d-54d1-4d87-a5d4-f59fe78c80a8.png) [^54]

\

![f20d13b8-79c9-4f06-92a0-d1834e999d16.png|1005](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/f20d13b8-79c9-4f06-92a0-d1834e999d16.png) [^55]

![cdb6a464-b20b-4b7f-b780-7cb09cb9803f.png|757](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/cdb6a464-b20b-4b7f-b780-7cb09cb9803f.png) [^56]

\

\

![4a0a651f-0db1-4bb5-ba15-fd78b6ea6406.png|707](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/4a0a651f-0db1-4bb5-ba15-fd78b6ea6406.png) [^57]

\

dashboard - create dashboard - add visualization - select prometheus data source.

![954b1c83-49f4-4662-a53d-09bfb1077f23.png|1070](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/954b1c83-49f4-4662-a53d-09bfb1077f23.png) [^58]

\

Different types of charts we can select & suggestions from grafana based on our query

![26590a60-779f-44c8-a6c9-49ab744d7031.png|438](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/26590a60-779f-44c8-a6c9-49ab744d7031.png) [^59]

\

![98c13c7f-c4f8-4c86-9d67-4759463c98e5.png|1052.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/98c13c7f-c4f8-4c86-9d67-4759463c98e5.png) [^60]

\

We can change the setting from options.

![2d700f59-1a3b-44df-b917-dc7ac3bf2bf4.png|837](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/2d700f59-1a3b-44df-b917-dc7ac3bf2bf4.png) [^61]

\

\

to test stop the Node instance, now it shows 0

![81ba2b35-9340-478e-87cb-b39dd978d3cd.png|1032.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/81ba2b35-9340-478e-87cb-b39dd978d3cd.png) [^62]

![b76ca2b3-1091-4ddf-a551-88fa45a73acc.png|935.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/b76ca2b3-1091-4ddf-a551-88fa45a73acc.png) [^63]

\

![efdc1a20-ab98-495f-abca-7ad6c02aa8a7.png|1191.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/efdc1a20-ab98-495f-abca-7ad6c02aa8a7.png) [^64]

\

# <mark style="background-color:#F8914D;">**Dynamic Scraping**<!-- {"backgroundCycleColor":"24"} --></mark><!-- {"collapsed":true} -->

Kubernetes & cloud Instances creates dynamically like catalogue, web etc. and we don't know the IP address, so prometheus has an option Dynamic Scraping.

\

**Here the goal is due to auto-scaling a new instance created then prometheus should monitor that server instantly(node_exporter is not required)** 

\

Creating a role **ec2:DescribeInstances** for prometheus instance (read only)

![599770ed-a590-49f8-9bb3-7a95432b78df.png|1160.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/599770ed-a590-49f8-9bb3-7a95432b78df.png) [^65]

![9c253880-0c87-40fd-81ab-749477b5c868.png|851.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/9c253880-0c87-40fd-81ab-749477b5c868.png) [^66]

\

![e4ed0aa0-212e-48d8-b4e2-842c64417621.png|1097.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/e4ed0aa0-212e-48d8-b4e2-842c64417621.png) [^67]

\

A new instance created for testing

![97f4a0fc-95c1-493b-8c1f-c60781b36bb0.png|1133.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/97f4a0fc-95c1-493b-8c1f-c60781b36bb0.png) [^68]

\

\

\

In prometheus server adding **ec2_scrapping details this will fetch log details dynamically.**

```
vim /opt/prometheus/prometheus.yml
```

```
- job_name: ec2_scrapping
  ec2_sd_configs
  - region: us-east-1
    port: 9100
```

![cdcd0fba-5752-4816-a9bd-6feb7b5bbb4a.png|940](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/cdcd0fba-5752-4816-a9bd-6feb7b5bbb4a.png) [^69]

![6a08bfb1-583f-4586-8d1f-85c961057369.png|870](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/6a08bfb1-583f-4586-8d1f-85c961057369.png) [^70]

\

```
systemctl restart prometheus
```

![30ba02e7-fb9a-423c-b32c-230a3d654612.png|809](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/30ba02e7-fb9a-423c-b32c-230a3d654612.png) [^71]

\

now it worked and reports & alerts are coming... All EC2 instance data shows

![6be6988c-31f5-4a9f-b2b2-1b167d6083d1.png|1078.666748046875](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/6be6988c-31f5-4a9f-b2b2-1b167d6083d1.png) [^72]

\

\

---

# <mark style="background-color:#F8914D;">**Prometheus Alerts**<!-- {"backgroundCycleColor":"24"} --></mark>

1. Raise the alert in the system (We need to add rules)

creating a directory alert-rules

```
cd /opt/prometheus
mkdir alert-rules
```

![3d931222-104b-4b5c-96e1-b1fd4ef844fc.png|740](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/3d931222-104b-4b5c-96e1-b1fd4ef844fc.png) [^73]

\

<mark>**Amazon SES(simple email service)**</mark>

\

<mark>**Installing Prometheus in EKS cluster.**</mark>

\

<mark>**ELK - Elasticsearch, Logstash, Kibana**</mark>

![8cc94e10-1d50-4cd8-b40e-26ba3d8c7ff4.png|1015.6666870117188](https://images.amplenote.com/abc18960-4969-11ef-90df-6ef34fa959ce/8cc94e10-1d50-4cd8-b40e-26ba3d8c7ff4.png) [^74]

\

check YouTube videos next....

\

[^1]: CAT-1 --> end user applications --> banking
    CAT-2 --> end user applications --> extra requests from customers
    CAT-3 -->
    CAT-4 -->

[^2]: Monitoring
    SRE --> Jenkins, Nexus, SonarQube, EKS, Ansible
    Authentication
    Authorization
    Upgrades
    Patches
    Maintainance --> admin activities
    Project creation
    Traffic
    Monitoring --> tool/website should be running 24\*7 with low latency

[^3]: Monitoring
    Collecting, processing, aggregating, and displaying real-time quantitative data about a system, such as query counts
    and types, error counts and types, processing times, and server lifetimes.
    White-box monitoring
    Monitoring based on metrics exposed by the internals of the system, including logs, interfaces like the Java Virtual
    Machine Profiling Interface, or an HTTP handler that emits internal statistics.
    Black-box monitoring
    Testing externally visible behavior as a user would see it.

[^4]: Black Box --> closed, we don't know internal details of app/system
    White Box -> open. we know internal details of app/system
    normal facebook user --> black box
    1. is facebook running or not?
    2. login is working or not
    3. input validations
    4. functionality testing
    white box --> you should know internal details
    1. all fb servers are up and running
    2. CPU, memory, disk, i/o
    3. log errors
    4. latency b/w internal components

[^5]: Alert --> that is an incident
    investigate the incident
    find why, implement solution, prepare root cause

[^6]: Latency --> Low latency
    Traffic --> measure traffic everytime
    Errors --> Log errors, application errors 5\* \*
    Saturation --> CPU, Memory, Disk

[^7]: 11-MAR --> 1000 --> food 200, travel 200, movies 200
    12-MAR --> 900
    weekly expenditure
    monthly expenditure
    quarterly expenditure
    yearly expenditure
    max expenditure
    min expenditure
    avg expenditure
    applications
    - - - - ---------------
    timestamp --> cpu 50
    cpu 52
    cpu 45
    H
    cpu 67

[^8]: Agent mechanism
    CCTV Mechanism
    CCTV cameras --> data collectors
    Central Storage --> analyse

[^9]: NODE-1
    Prometheus
    node
    Alert
    exporter
    Manager
    TSDB
    Service
    http-server
    Discovery
    node
    exporter

[^10]: Instances (1/3) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q. Find Instance by attribute or tag (case-sensitive)
    Any state
    < 1 >
    -
    Name
    4
    Instance ID
    Instance state
    4
    Instance type
    4
    Status check
    Alarm status
    Availabil
    jd-server-don't-delete
    i-05d90fc9fd7e1b342
    Stopped Q Q
    t2.micro
    View alarms +
    us-east-1
    prometheus
    i-Ode7fefc60b 192f75
    Running Q Q
    t3.medium
    Initializing
    View alarms +
    us-east-1
    O
    jd-db-don't-delete
    i-Ofa7cb4doc4ef9630
    Stopped Q Q
    t3.medium
    View alarms +
    us-east-1

[^11]: 3. 238. 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ centos@ip-172-31-6-11 \~ \]$ sudo su
    3. 238. 105. 76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /home/centos \]# cd /opt/

[^12]: prometheus.io/download/
    . mysqld_exporter
    . node_exporter
    promlens
    . pushgateway
    . statsd_exporter
    Operating system popular .
    Architecture amd64
    prometheus
    The Prometheus monitoring system and time series database. ( prometheus/prometheus
    2.50.1 / 2024-02-26 Release notes
    File name
    OS
    Arch
    Size
    SHA256 Checksum
    prometheus-2.50.1.darwin-amd64.tar.gz
    darwin
    amd64
    93.61 MiB
    prometheus-2.50.1.linux-amdGA.tar.gz
    linux
    amd64 94.41 MiB
    prometheus-2.50.1.windows-amd64.zip
    windows
    amd64 96.47 MiB
    2.45.3 / 2024-01-24 LTS Release notes

[^13]: 3. 238 . 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt \]# wget https: //github. com/prometheus/prometheus/releases/download/v2 . 50. 1/prometheus-2 . 50. 1. linux-amd64 . tar
    gz
    --2024-03-11 02:35:11-- https://github. com/prometheus/prometheus/releases/download/v2 . 50.1/prometheus-2 . 50. 1. linux-amd64 . tar . gz
    Resolving github. com (github. com) ... 140 . 82.114.3
    Connecting to github. com (github. com) \| 140 . 82. 114. 31: 443. .. connected.
    HTTP request sent, awaiting response. . .

[^14]: 3 . 238. 105. 76 \| 172 . 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt \]# 1s
    prometheus-2 . 50. 1. linux-amd64 . tar . gz
    3. 238. 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt \]# tar -xf prometheus-2.50.1. linux-amd64. tar . gz

[^15]: 3. 238. 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt \]# 1s
    prometheus-2. 50 . 1 . linux-amd64 prometheus-2 . 50 . 1 . linux-amd64 . tar . gz
    3. 238. 105.76 \| 172. 31.6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt \]# mv prometheus-2. 50.1. linux-amd64 prometheus
    3. 238. 105.76 \| 172. 31. 6.11 \| t3.medium \| null
    \[ root@ip-172-31-6-11 /opt \]# 1s
    prometheus prometheus-2 . 50. 1. linux-amd64 . tar . gz
    3. 238. 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    C
    root@ip-172-31-6-11 /opt \]# cd prometheus
    3 . 238. 105. 76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt/prometheus \]# ls -1
    total 244904
    drwxr-xr-x 2 1001 127
    38 Feb 26 12:11 console libraries
    drwxr-xr-x 2 1001 127
    173 Feb 26 12:11 consoles
    rw-r--r-- 1 1001 127
    11357 Feb 26 12:11 LICENSE
    rw-r--r-- 1 1001 127
    3773 Feb 26 12:11 NOTICE
    rwxr-xr-x 1 1001 127 129611890 Feb 26 11:38 prometheus
    rw-r--r-- 1 1001 127
    934 Feb 26 12:11 prometheus . yml
    rwxr-xr-x 1 1001 127 121143706 Feb 26 11:38 promtool
    3 . 238 . 105. 76 \| 172. 31.6.11 \| t3. medium \| null

[^16]: 3. 238. 105. 76 \| 172 . 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt/prometheus \]# vim /etc/systemd/system/prometheus . service

[^17]: \[Unit\]
    Description=prometheus service.
    \[Service\]
    ExecStart=/opt/prometheus/prometheus --config. file=/opt/prometheus/prometheus . yml
    \[Install\]
    WantedBy-multi-user . target

[^18]: 3. 238. 105.76 \| 172 . 31 . 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt/prometheus \]# systemctl start prometheus
    3. 238 . 105. 76 \| 172. 31. 6.11 \| t3. medium \| null
    root@ip-172-31-6-11 /opt/prometheus \]# systemctl status prometheus
    prometheus . service - prometheus service.
    Loaded: loaded (/etc/systemd/system/prometheus . service; disabled; vendor preset: disabled)
    Active: active (running) since Mon 2024-03-11 02:38:13 UTC; 8s ago
    Main PID: 4728 (prometheus)
    Tasks: 7 (limit: 22564)
    Memory: 19.5M
    CGroup: /system. slice/prometheus . service
    L4728 /opt/prometheus/prometheus --config. file=/opt/prometheus/prometheus . yml
    Mar 11 02:38:14 ip-172-31-6-11. ec2. internal prometheus \[4728\]: ts=2024-03-11T02 : 38: 14. 045% caller=head.g
    Mar 11 02:38:14 ip-172-31-6-11. ec2. internal prometheus \[4728\] : ts=2024-03-11T02: 38: 14. 045% caller=head.

[^19]: 3. 238. 105.76 \| 172 . 31. 6.11 \| t3. medium \| null
    \[ rootdip-172-31-6-11 /opt/prometheus \]# systemctl enable prometheus
    Created symlink /etc/systemd/system/multi-user . target . wants/prometheus . service - /etc/systemd/system/prometheus . service.

[^20]: 3. 238
    105
    \| 172 . 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt/prometheus \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    top
    0 0.0.0.0:22
    0 .0.0.0:\*
    LISTEN
    849/sshd
    top6
    OOOOO
    0 : : : 9090
    LISTEN
    4728/prometheus
    tcp6
    0
    : : :111
    LISTEN
    1/systemd
    top6
    0
    : : : 22
    LISTEN
    849/sshd

[^21]: C
    A Not secure 3.238.105.76:9090/graph?g0.expre&g0.tab=1&:90.display_mode=lines&g0.show_exemplars=0&g0.range_input=1h
    Prometheus Alerts Graph Status . Help
    Use local time Enable query history Enable autocomplete @ Enable highlighting Enable linter
    Q
    Expression (press Shift+Enter for newlines)
    Table
    Graph
    <
    Evaluation time
    No data queried yet
    Add Panel

[^22]: O Use local time ) Enable query history ) Enable autocomplete @ Enable highlighting @ Enable linter
    Q
    up
    E
    6
    Execute
    Load time: 289ms Resolutions Is Result series:
    Table
    Graph
    5m
    <
    End time
    Res. (s)
    Show Exemplars
    1.20
    1.00
    0.80
    +
    2024-03-11 02 39:05 +00:00
    up: 1
    0.60
    Series:
    up
    instance: localhost.9090
    job: prometheus
    0.40
    0.20
    0.00
    02:35:30
    02:36:00
    02:36:30
    02:37:00
    0237:30
    02:38-00
    02-38-30
    02:39:00
    02:39:30
    02 40-00

[^23]: Prometheus Alerts Graph Status . Help
    O Use local time ) Enable query history Enable autocomplete Enable highlighting Enable linter
    up \[ 5m\]
    E
    Execute
    Graph
    Load time: 296ms Resolution: 14s Result series: 1
    Table
    Evaluation time
    >
    up (instance="localhost:9090", job="prometheus")
    1 @1710124708.488
    1 @1710124723.488
    1 @1710124738.488
    1 @1710124753.493
    1 @1710124768.492
    1 @1710124783.488
    1 @1710124798.492
    1 @1710124813.488
    1 @1710124828.493
    1 @1710124843.488
    1 @1710124858.492
    1 @1710124873.493
    1 @1710124888.488
    1 @1710124903.492
    1 @1710124918.488
    1 @1710124933.488
    1 @1710124948.492
    1 @1710124963.488
    1 @1710124978.488
    Remove Panel

[^24]: Prometheus Alerts Graph Status . Help
    & CO
    O Use local time O Enable query history Enable autocomplete @ Enable highlighting @ Enable linter
    Q
    prometheus_http_requests_total
    E
    Execute
    Load time: 293ms Resolution: Is Result series: 52
    Table
    Graph
    Evaluation time
    prometheus_http_requests_total(code="200", handler="/ instance="localhost:9090". job="prometheus"}
    prometheus_http_requests_total (code="200". handler="/-healthy", instance="localhost:9090", job="prometheus"}
    o o
    prometheus_http_requests_total(code="200", handler="/-/quit", instance="localhost:9090". job="prometheus")
    prometheus_http_requests_total(code="200", handler="/-/ready", instance="localhost:9090, job="prometheus")
    prometheus_http_requests_total(code="200", handler="/-/reload", instance="localhost:9090", job="prometheus")
    ooo -
    prometheus_http_requests_total(code="200", handler="/alerts", instance="localhost:9090", job="prometheus"}
    prometheus_http_requests_total(code="200", handler="/api/v1/"path", instance="localhost:9090", job="prometheus"}
    prometheus_http_requests_total(code="200", handler="/api/v1/admin/tsab/clean_tombstones", instance="localhost:9090", job="prometheus")
    prometheus_http_requests_total(code="200", handler="/api/v1/admin/tsdo/delete_series", instance="localhost:9090", job="prometheus")
    prometheus_http_requests_total(code="200", handler="/api/v1/admin/tsab/snapshot", instance="localhost:9090", job="prometheus"}
    prometheus_http_requests_total (code="200", handler="/api/v1/alertmanagers", instance="localhost:9090", job="prometheus"}

[^25]: Instances (1/4) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    < 1 >
    -
    Name
    V
    Instance ID
    Instance state
    4
    Instance type
    4
    Status check
    Alarm status
    Availabili
    jd-server-don't-delete
    i-05d90fc9fd7e1b342
    Stopped Q Q
    t2.micro
    View alarms +
    us-east-1
    prom-node
    i-067dee1af3e52b152
    Pending Q Q
    t2.micro
    View alarms +
    us-east-1

[^26]: Commands
    server
    node
    LL
    WUL
    Disclaimer :

[^27]: G
    @ https://prometheus.io/download/
    node_exporter
    Exporter for machine metrics () prometheus/node_exporter
    1.8.2 / 2024-06-19 Release notes
    File name
    OS
    Arch
    Size
    SHA256 Checksum
    node_exporter-1.8.2.darwin-amd64.tar.gz
    darwin
    amd64
    4.83 MiB
    97 ad998fe48904a86085f2c5adc6abeed85389f5fc298a6d2e94ee2e73cf1728
    node exporter-1.8.2.linux-amd64.tar.gz
    linux
    amd64
    10.18 MiB
    6809ddeb3ec45fd6992c19071d6b5253aed3ead7bf0686885a51d85c6643c66

[^28]: 44 . 212.2. 83 \| 172. 31.83.66 \| t2.micro \| null
    \[ centos@ip-172-31-83-66 \~ \]$ sudo su
    44 . 212.2.83 \| 172. 31.83. 66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /home/centos \]# cd /opt/
    44 . 212.2. 83 \| 172. 31.83. 66 \| t2. micro \| null
    root@ip-172-31-83-66 /opt \]# wget https: //github. com/prometheus/node_exporter/releases/download/v1 . 7.0/node_exporter-1. 7.0. linux-and
    4 . tar . gz
    --2024-03-11 02: 48:00-- https://github. com/prometheus/node_exporter/releases/download/v1 . 7.0/node_exporter-1. 7.0. linux-amd64 . tar . gz
    Resolving github. com (github. com) . . . 140 . 82.114.3
    Connecting to github. com (github. com) \|140 . 82 . 114. 3\|: 443. .. connected.
    HTTP request sent, awaiting response. . . 302 Found
    Location: https: //objects . githubusercontent. com/github-production-release-asset-2e65be/9524057/01323270-6ecb-47aa-813f-52a2a89cdc64?X-
    mz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA$2F20240311$2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20240311T024
    OOZ&X-Amz-Expires=300&X-Amz-Signature=30fe947301d2316e8ef337b2183439ab05b11c738113f647ace8535b0f4ed46c&X-Amz-SignedHeaders=host&actor

[^29]: 44 . 212.2.83 \| 172.31.83.66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt \]# 1s
    node_exporter-1. 7.0. linux-amd64 . tar . gz
    44 . 212.2. 83 \| 172. 31.83. 66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt \]# tar -xf node_exporter-1. 7.0. linux-amd64 . tar . gz
    44 . 212.2.83 \| 172. 31. 83.66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt \]# 1s
    node_exporter-1. 7.0. linux-and64 node_exporter-1. 7.0. linux-amd64 . tar . gz
    44 . 212. 2.83 \| 172. 31. 83. 66 \| t2. micro \| null
    \[ root@ip-172-31-83-66 /opt \]# mv node_exporter-1. 7.0. linux-amd64 node exporter
    44 . 212.2.83 \| 172. 31. 83.66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt \]#\|

[^30]: 44 . 212.2.83 \| 172. 31. 83.66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt/node_exporter \]# vim /etc/systemd/system/node_exporter . service

[^31]: \[Unit\]
    Description=prometheus service.
    \[Service\]
    ExecStart=/opt/node_exporter/node_exporter
    \[Install\]
    WantedBy-multi-user . target

[^32]: 44 . 212.2.83 \| 172. 31.83.66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt/node_exporter \]# systemctl start node_exporter
    44 . 212.2.83 \| 172. 31.83.66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt/node_exporter \]# system status node_exporter
    bash: system: command not found
    44 . 212. 2.83 \| 172. 31.83. 66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt/node_exporter \]# systemctl status node_exporter
    node exporter . service - prometheus service.
    Loaded: loaded (/etc/systemd/system/node_exporter . service; disabled; vendor preset: disabled)
    Active: active (running) since Mon 2024-03-11 02:49:30 UTC; 13s ago
    Main PID: 4697 (node exporter)
    Tasks: 3 (limit: 4398)
    Memory: 4. 7M
    CGroup: /system. slice/node_exporter . service
    L4697 /opt/node_exporter/node_exporter
    Mar 11 02:49:30 ip-172-31-83-66. ec2. internal node exporter \[4697\]: ts=2024-03-11T02 : 49: 30. 035% caller=n
    Mar 11 02:49:30 ip-172-31-83-66. ec2. internal node exporter \[4697\] : ts=2024-03-11T02 : 49:30.035% caller=n
    Mar 11 02:49:30 ip-172-31-83-66.ec2. internal node_exporter \[4697\] : ts=2024-03-11T02: 49: 30. 035% caller=n
    Mar 11 02:49:30 ip-172-31-83-66. ec2. internal node exporter \[4697\]: ts=2024-03-11T02 : 49:30.035% caller=n
    Mar
    11 02 : 49 : 30 ip-172-31-83-66. ec2. internal node
    exporter \[46971 :
    ts=2024-03-11TO2 : 49 : 30 . 035Z
    aller

[^33]: 44. 212. 2.83 \| 172. 31. 83. 66 \| t2. micro \| null
    \[ rootdip-172-31-83-66 /opt/node_exporter \]# systemctl enable node_exporter
    Created symlink /etc/systemd/system/multi-user . target. wants/node_exporter. service - /etc/systemd/system/node_exporter . service.

[^34]: 44 . 212.2.83 \| 172. 31.83.66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt/node_exporter \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    top
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    tcp
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    799/sshd
    tcp6
    OOOOO
    0 : : :9100
    LISTEN
    4697/node exporter
    top6
    0 : : :111
    LISTEN
    1/systemd
    top6
    0 : : :22
    LISTEN
    799/sshd
    83
    172
    31 83 66

[^35]: C
    A Not secure 44.212.2.83:9100/metrics
    HELP node_filesystem_files_free Filesystem total free file nodes.
    # TYPE node_filesystem_files_free gauge
    node_filesystem_files_free{device="/dev/xvdal", fstype="xfs",mountpoint-"/"} 5.184692e+06
    node_filesystem_files_free{device="tmpfs", fstype="tmpfs",mountpoint="/run"} 97807
    node_filesystem_files_free{device."tmpfs", fstype="tmpfs", mountpoint-"/run/user/1000"} 98202
    " HELP node_filesystem_free_bytes Filesystem free space in bytes.
    " TYPE node_filesystem_free_bytes gauge
    node_filesystem_free_bytes{device="/dev/xvdal", fstype="xfs",mountpoint="/"} 7.499251712e+09
    node_filesystem_free_bytes{device="tmpfs", fstype="tmpfs", mountpoint="/run"} 4.018176e+08
    node_filesystem_free_bytes{device."tmpfs", fstype="tmpfs",mountpoint="/run/user/1000"} 8.0449536e+07
    " HELP node_filesystem_readonly Filesystem read-only status.
    TYPE node_filesystem_readonly gauge
    node_filesystem_readonly(device="/dev/xvdal", fstype="xfs",mountpoint="/"} 0
    node_filesystem_readonly(device="tmpfs", fstype-"tmpfs", mountpoint-"/run"} 0
    node_filesystem_readonly(device."tmpfs", fstype="tmpfs",mountpoint="/run/user/1000"} 0
    " HELP node_filesystem_size_bytes Filesystem size in bytes.
    " TYPE node_filesystem_size_bytes gauge
    node_filesystem_size_bytes{device="/dev/xvdal", fstype="xfs",mountpoint="/"} 1.0725863424e+10
    2355872-408

[^36]: Escrape_configs :
    # The job name is added as a label job=<job
    config.
    - job name: "prometheus"
    I # metrics path defaults to '/metrics'
    # scheme defaults to 'http'.
    static configs :
    - targets: \["localhost : 9090"\]
    - job name: "node-exporter"
    static configs :
    - targets: \["172. 31. 83. 66:9100"\]

[^37]: 3. 238 . 105. 76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt/prometheus \]# vim prometheus . yml

[^38]: #
    A scrape configuration containing exactly one endpoint to scrape:
    #
    Here it's Prometheus itself.
    scrape_configs :
    #
    The job name is added as a label job=<job name> to any timeseries scraped from
    job name: "prometheus"
    #
    metrics path defaults to '/metrics'
    #
    scheme defaults to 'http'.
    static configs :
    - targets: \["localhost: 9090"\]
    job name: "node-exporter"
    static configs :
    - targets: \["172 . 31 . 83. 66:9100"\]
    INSERT (paste)

[^39]: 3. 238 . 105. 76 \| 172 . 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 /opt/prometheus \]# systemctl restart prometheus

[^40]: A Not secure 3.238.105.76:9090/graph?g0.exprup&g0.tab=18190.display_mode=lines&g0.show_exemplars=0890.range_input=1h
    Prometheus Alerts Graph Status \~ Help
    # CO
    O Use local time ) Enable query history Enable autocomplete Enable highlighting Enable linter
    Q
    up
    E
    Execute
    Load time: 284ms Resolution: 145 Result series:
    Table
    Graph
    Evaluation time
    up (instance="localhost:9090", job="prometheus")
    up(instance="172.31.83.669100", job="node-exporter"
    Remove Panel
    Add Panel

[^41]: O Use local time ) Enable query history Enable autocomplete Enable highlighting Enable linter
    node_memory_MemAvailable_bytes
    E
    Execute
    Load time: 292ms Resolutions 14s Result series: 1
    Table
    Graph
    Evaluation time
    node_memory_MemAvailable_bytes(instance="172.31.83.66:9100", job="node-exporter")
    $56802048
    Remove Panel

[^42]: O Use local time ) Enable query history Enable autocomplete @ Enable highlighting @ Enable linter
    Q
    node_memory_MemAvailable_bytes / 1024
    E
    Execute
    Table
    Graph
    Load time: 279es Resolution: 145 Result series: 1
    Evaluation time
    (instance="172.31.83.66:9100", job="node-exporter")
    543492
    Remove Panel

[^43]: server
    node
    44 . 212.2.83 \| 172. 31.83.66 \| t2.micro \| null
    \[ root@ip-172-31-83-66 /opt/node_exporter \]# free
    total
    used
    free
    shared buff/cache
    available
    Mem :
    785656
    124132
    397876
    1964
    263648
    543280
    Swap :
    0
    0
    0

[^44]: F
    C
    grafana.com/docs/grafana/latest/setup-grafana/installation/redhat-rhel-fedora/
    your applications.
    Q Search docs
    Expand table
    Product
    Grafana
    Grafana Version
    Package
    Repository
    Viewing: v10.4 (latest)
    Grafana Enterprise
    grafana-enterprise
    https://rpm.grafana.com
    Find another version
    Grafana OSS
    grafana
    https://rpm.grafana.com
    Grafana open source documentation
    > What's new
    NOTE
    > Breaking changes
    > Upgrade Grafana
    Grafana Enterprise is the recommended and default edition. It is available for free and includes
    > About Grafana
    all the features of the OSS edition. You can also upgrade to the full Enterprise feature set,
    which has support for Enterprise plugins.
    > Introduction
    > Get started with Grafana Open Source
    To install Grafana from the RPM repository, complete the following steps:
    Set up
    \|\~ Install Grafana
    1 Import the GPG key:
    Debian or Ubuntu
    bash
    Copy
    RHEL or Fedora
    SUSE or openSUSE
    wget -q -0 gpg-key https://rpm. grafana. com/gpg.key
    Grafana Docker image
    sudo rpm - -import gpg.key
    Grafana on Kubernetes
    Grafana on Helm Charts
    2 Create /etc/yum. repos.d/grafana. repo with the following content:

[^45]: 3. 238. 105. 76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# wget -q -0 gpg. key https: //rpm. grafana. com/gpg . key
    3. 238 . 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# sudo rpm --import gpg . key
    3. 238 . 105. 76 \| 172 . 31. 6.11 \| t3. medium \| null

[^46]: 3. 238 . 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# vim /etc/yum. repos . d/grafana . repo

[^47]: \[grafana\]
    name=grafana
    baseurl=https : / /rpm . grafana. com
    repo_gpgcheck=1
    enabled=1
    gpgcheck=1
    gpgkey-https : //rpm. grafana . com/gpg . key
    sslverify=1
    ssicacert=/etc/pki/tls/certs/ca-bundle . crt

[^48]: 3. 238 . 105.76 \| 172. 31.6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# sudo anf install grafana -y
    Centos Stream 8 - AppStream
    45 MB/S
    I
    28 MB
    00:00
    Centos Stream 8 - BaseOS
    39 MB/S
    10 MB
    00:00

[^49]: 3. 238. 105. 76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# systemctl daemon-reload
    3. 238. 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# systemctl start grafana-server
    3. 238 . 105. 76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# systemctl status grafana-server
    grafana-server . service - Grafana instance
    Loaded: loaded (/usr/lib/systemd/system/grafana-server . service; disabled; vendor preset:
    Active: active (running) since Mon 2024-03-11 03:00:09 UTC; 1s ago
    Docs: http: / /docs . grafana . org
    Main PID: 16565 (grafana)

[^50]: 3. 238 . 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# systemctl enable grafana-server
    Synchronizing state of grafana-server. service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
    Executing: /usr/lib/systemd/systemd-sysv-install enable grafana-server
    Created symlink /etc/systemd/system/multi-user . target. wants/grafana-server . service - /usr/lib/systemd/system/grafana-server . service

[^51]: 3. 238. 105. 76 \| 172 . 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# netstat -Intp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address
    Foreign Address
    State
    PID/Program name
    tcp
    0 0.0.0.0:111
    0.0.0.0:\*
    LISTEN
    1/systemd
    top
    0 0.0.0.0:22
    0.0.0.0:\*
    LISTEN
    849/sshd
    top6
    :: :9090
    LISTEN
    4848/prometheus
    oooooo
    tcp6
    : ::111
    LISTEN
    1/systemd
    tcp6
    0 :::22
    LISTEN
    849/sshd
    tcp6
    0 : : : 3050
    LISTEN
    16565/grafana

[^52]: F
    C
    A Not secure 3.238.105.76:3000/login
    Welcome to Grafana
    Email or username
    admin
    Password
    .....
    Smog in
    Forgot your password?

[^53]: Update your password
    Continuing to use the default password
    exposes you to security risks.
    New password
    ........
    Show password
    Confirm new password
    O
    Submit
    Skip

[^54]: A Not secure 3.238.105.76:3000/connections/datasources/new
    O
    Q Search or jump to.
    ctrick
    O
    Home > Connections > Data sources > Add data source
    Home
    Add data source
    V
    Datasource added
    Starred
    Dashboards
    Choose a data source type
    Explore
    Q. Filter by name or type
    Cancel
    Alerting
    Time series databases
    Connections
    Add new connection
    Prometheus
    Data sources
    Open source time series database & alerting
    Learn more
    Core
    Administration
    Graphit
    Open source time series database
    Core
    InfluxDB
    Open source time series database
    Core
    OpenTSDB
    Open source time series database
    Core
    Logging & document databases

[^55]: Configure your Prometheus data source below
    Or skip the effort and get Prometheus (and Loki) as fully-managed, scalable, and hosted data sources from Grafana Labs with the free-forever
    Name
    prometheus
    Default
    Before you can use the Prometheus data source, you must configure it below or in the config file. For detailed instructions, view the documentation.
    Fields marked with \* are required
    Connection
    Prometheus server URL .
    http://localhost:9090

[^56]: V
    Successfully queried the Prometheus API.
    Next, you can start to visualize data by building a dashboard, or by querying data in the Explore view.
    Delete
    Save & test

[^57]: Grafana
    http
    NODE-1
    Prometheus
    node
    Alert
    exporter
    Manager
    TSDB
    15S
    Service
    http-server
    Discovery
    node
    exporter

[^58]: Q Search or jump to..
    @ ctrl+k
    Home > Dashboards > New dashboard > Edit panel
    Discar
    Home
    Table view
    Fill
    Actual
    Last 6 hours
    Time series
    Starred
    88
    Dashboards
    Panel Title
    Q Search options
    2
    Playlists
    All
    Snapshots
    1.5
    Panel options
    Library panels
    Title
    Public dashboards
    0.5
    Panel Title
    O
    Explore
    Description
    Alerting
    03:00
    03:30
    04:00
    04:30
    05:00
    05:30
    06:00
    06:30
    07:00
    07:30
    08:00
    08:30
    Connections
    - {name_="up", instance="172.31.83.66:9100", job="node-exporter"}
    Add new connection
    - {name_="up", instance="localhost:9090", job="prometheus"}
    Transparent background
    Data sources
    Query 1
    Transform data o
    8 Alert 0
    Administration
    Panel links
    > Repeat options
    A
    (prometheus)
    Tooltip
    Kick start your query
    Explain
    Run queries
    Builder
    Code
    Tooltip mode
    Metrics browser >
    up
    Single
    All
    Hidden
    > Options Legend: Auto Format: Time series
    Step: auto Type: Range Exemplars: false
    Hover proximity
    How close the cursor must be to

[^59]: Q Search for...
    Visualizations
    Suggestions
    Library panels
    Time series
    Time based line, area and bar charts
    Bar chart
    Categorical charts with group support
    12.4
    Stat
    Big stat values & sparklines
    Gauge
    79
    Standard gauge visualization
    Bar gauge
    Horizontal and vertical gauges
    Table
    Supports many column styles
    Pie chart
    The new core pie chart visualization
    State timeline
    State changes and durations
    Heatmap
    Like a histogram over time

[^60]: Save dashboard
    New dashboard
    Panel Title
    Details
    Title
    Demo
    Description
    Folder
    (_name_="up", instance="172.31.83.... {_n
    Dashboards
    Cancel
    Save
    B Query
    1
    Transform data
    Data source
    prometheus

[^61]: UP
    ...
    172.31.83.66:9100
    localhost:9090
    Query
    1
    Transform data
    O
    A
    (prometheus)
    Kick start your query
    Explain
    Run queries
    Builder
    Code
    Metrics browser >
    up
    >
    Options Legend: {{instance}} Format: Time series Step: auto Type: Range Exemplars: false

[^62]: Successfully stopped i-067 dee 1af3e52b152
    Instances (1/4) Info
    C
    Connect
    Instance state
    Act
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    -
    Name
    Instance ID
    Instance state
    Instance type
    Status ch
    0
    jd-server-don't-delete
    i-05d90fc9fd7e1b342
    Stopped Q Q
    t2.micro
    ...
    prom-node
    i-067dee 1af3e52b152
    Stopping Q Q
    t2.micro

[^63]: F
    A Not secure 3.238.105.76:3000/d/bdfatpdwtpts0a/demo?orgld =1
    Q. Search or jump to.
    ctrl+k
    E
    Home > Dashboards > Demo
    Home
    UP
    . ..
    Starred
    98
    Dashboards
    Playlists
    Snapshots
    Library panels
    O
    Public dashboards
    Explore
    172.31.83.66:9100
    localhost:9090
    Alerting

[^64]: Q Search or jump to.
    @ ctrl+k
    E
    Home > Dashboards > Demo
    KO
    Add v
    Share
    Last 15 minutes
    Home
    UP
    Starred
    Dashboards
    Playlists
    0.75
    Snapshots
    10.5
    Library panels
    0.25
    Public dashboards
    08:30
    08:35
    Explore
    2024-03-11 08:37:00
    - 172.31.83.66:9100 - localhost:9090
    - 172.31.83.66:9100
    A
    Alerting
    Connections
    Add new connection
    Data sources

[^65]: Successfully stopped i-067dee 1af3e52b152
    X
    Instances (1/4) Info
    C
    Connect
    Instance state
    Actions
    Launch instances
    4
    Q Find Instance by attribute or tag (case-sensitive)
    Any state
    Connect
    View details
    Name _
    Instance ID
    Instance state
    Instance type
    St
    Availab
    Manage instance state
    O
    jd-server-don't-delete
    i-05d90fc9fd7e1b342
    Stopped Q Q
    t2.micro
    us-east-
    Instance settings
    0
    prom-node
    i-067 dee 1af3e52b152
    Stopped Q Q
    t2.micro
    us-east
    Networking
    prometheus
    i-Ode7fefc60b 192f75
    Running
    Change security groups
    us-east-
    Security
    0
    jd-db-don't-delete
    i-Ofa7cb4doc4ef9630
    Stopped Q
    Get Windows password
    Image and templates
    us-east
    Modify IAM role
    Monitor and troubleshoot

[^66]: EC2 > Instances > i-Ode7fefc60b192f75 > Modify IAM role
    Modify IAM role Info
    Attach an IAM role to your instance.
    Instance ID
    i-0de7fefc60b 192f75 (prometheus)
    IAM role
    Select an IAM role to attach to your instance or create a new role if you haven't created any. The role you select replaces any roles that are
    currently attached to your instance.
    ShellScriptRoleForRoboshop
    C
    Create new IAM role Z
    Cancel
    Update IAM role

[^67]: F
    prometheus.io/does/prometheus/latest/configuration/configuration/#ec2_sd_config
    kec2_sd_config>
    EC2 SD configurations allow retrieving scrape targets from AWS EC2 instances. The private IP address is used by
    default, but may be changed to the public IP address with relabeling.
    The IAM credentials used must have the ec2: DescribeInstances permission to discover scrape targets, and may
    optionally have the ec2: DescribeAvailabilityZones permission if you want the availability zone ID available as a
    label (see below).
    The following meta labels are available on targets during relabeling:
    _meta_ec2_ami : the EC2 Amazon Machine Image
    _meta_ec2_architecture : the architecture of the instance
    . .
    _meta_ec2_availability_zone : the availability zone in which the instance is running
    _meta_ec2_availability_zone_id : the availability zone ID in which the instance is running (requires
    ec2:DescribeAvailabilityZones )

[^68]: EC2 > Instances > Launch an instance
    Launching instance
    Launch initiation
    75%
    Details

[^69]: 3. 238. 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# vim /opt/prometheus/prometheus . yml

[^70]: A scrape configuration containing exactly one endpoint to scrape:
    Here it's Prometheus itself.
    scrape_configs :
    #
    The job name is added as a label job=<job name> to any timeseries scraped from this config.
    job name: "prometheus"
    #
    metrics path defaults to ' /metrics'
    #
    scheme defaults to 'http' .
    static configs :
    - targets: \["localhost: 9090"\]
    job name: "node-exporter"
    static configs :
    - targets: \["172. 31. 83. 66: 9100"\]
    job name: ec2_scrapping
    ec2_sd_configs :
    - region: us-east-1
    port: 9100

[^71]: 3. 238 . 105.76 \| 172. 31. 6.11 \| t3. medium \| null
    \[ root@ip-172-31-6-11 \~ \]# systemctl restart prometheus

[^72]: F
    C A Not secure 3.238.795.76:9090/graph
    Q \*
    Prometheus Alerts Graph Status Help
    C O
    Use local time O Enable query history Enable autocomplete Enable highlighting Enable linter
    Q
    up
    E
    Execute
    Load time: 278ms Resolution: 14s Result series: 7
    Table
    Graph
    Evaluation time
    up (instance ="localhost:9090", job="prometheus"}
    -
    up (instance="172.31.83.66:9100", job="node-exporter")
    up (instance ="172.31.6.11:9100", job="ec2_scrapping")
    - . o
    up (instance="172.31.80.226:9100", job="ec2_scrapping"}
    up (instance ="172.31.11.108:9100", job="ec2_scrapping"}
    O
    up (instance="172.31.83.66:9100", job="ec2_scrapping"}
    O
    up (instance ="172.31.87.242:9100", job="ec2_scrapping"}
    O
    Click to copy label matcher
    Remove Panel

[^73]: 44 . 203. 34.154 \| 172. 31.2.22 \| t3. medium \| null
    \[ root@ip-172-31-2-22 \~ \]# cd /opt/prometheus
    44 . 203 . 34. 154 \| 172. 31.2.22 \| t3. medium \| null
    \[ root@ip-172-31-2-22 /opt/prometheus \]# mkdir alert-rules

[^74]: ELK
    ElasticSearch
    --> DB to Store log files /documents
    Logstash
    Kibana --> Ui for elastic search
    usually application logs should be shifted external system for analysis

