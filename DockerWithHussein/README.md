┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:30:23]─[G:DockerWithHussein]
╰─>$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:30:25]─[G:DockerWithHussein]
╰─>$ docker run -p 80:80 -d httpd
Unable to find image 'httpd:latest' locally
latest: Pulling from library/httpd
dd6189d6fc13: Already exists
19310c2838ce: Already exists
57763793d667: Already exists
d4c2d36121f0: Already exists
f500cd0cfd27: Already exists
Digest: sha256:5fa96551b61359de5dfb7fd8c9e97e4153232eb520a8e883e2f47fc80dbfc33e
Status: Downloaded newer image for httpd:latest
ee36da1004aeec16b4127e85bdf997a36f3d49352e344e756f95a96ceaf5f929
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:31:02]─[G:DockerWithHussein]
╰─>$ curl http://Arafats-MacBook-Pro.local
<html><body><h1>It works!</h1></body></html>
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:31:14]─[G:DockerWithHussein]
╰─>$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED          STATUS          PORTS                               NAMES
ee36da1004ae   httpd     "httpd-foreground"   58 seconds ago   Up 58 seconds   0.0.0.0:80->80/tcp, :::80->80/tcp   zealous_goldberg
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:31:37]─[G:DockerWithHussein]
╰─>$ docker inspect ee3
[
    {
        "Id": "ee36da1004aeec16b4127e85bdf997a36f3d49352e344e756f95a96ceaf5f929",
        "Created": "2022-11-02T18:30:39.019865005Z",
        "Path": "httpd-foreground",
        "Args": [],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 4481,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2022-11-02T18:30:39.226652797Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:046709a1d626aa32994a0c0566830da97c8bd074ea29f3b57cb75991077d91eb",
        "ResolvConfPath": "/var/lib/docker/containers/ee36da1004aeec16b4127e85bdf997a36f3d49352e344e756f95a96ceaf5f929/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/ee36da1004aeec16b4127e85bdf997a36f3d49352e344e756f95a96ceaf5f929/hostname",
        "HostsPath": "/var/lib/docker/containers/ee36da1004aeec16b4127e85bdf997a36f3d49352e344e756f95a96ceaf5f929/hosts",
        "LogPath": "/var/lib/docker/containers/ee36da1004aeec16b4127e85bdf997a36f3d49352e344e756f95a96ceaf5f929/ee36da1004aeec16b4127e85bdf997a36f3d49352e344e756f95a96ceaf5f929-json.log",
        "Name": "/zealous_goldberg",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {
                "80/tcp": [
                    {
                        "HostIp": "",
                        "HostPort": "80"
                    }
                ]
            },
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "host",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                0,
                0
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "KernelMemory": 0,
            "KernelMemoryTCP": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": null,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/0fe70231ade73193860420790871222fad5c48d305d77eb6a43a7dbe893cb238-init/diff:/var/lib/docker/overlay2/4452719c06fd752d1d273c2ee3e81eb21d1927d32c94b9ab87ed51c888877937/diff:/var/lib/docker/overlay2/ddf37a3fa298d9849cca59cd0f54fd850d655025d69fbdbf3bf82c9f4192f6b6/diff:/var/lib/docker/overlay2/e38601c85136909b6de47682fe7f4b70ba1f5e905f3bb3540f62c4af3752102e/diff:/var/lib/docker/overlay2/856d5f18b56c8a30d14d56ea2b47ba793869e8f15660b9e0c4277f19105e8b41/diff:/var/lib/docker/overlay2/46301fd761f00f9b0d8f0002a3914042162567695c8d632d889956418a08d592/diff",
                "MergedDir": "/var/lib/docker/overlay2/0fe70231ade73193860420790871222fad5c48d305d77eb6a43a7dbe893cb238/merged",
                "UpperDir": "/var/lib/docker/overlay2/0fe70231ade73193860420790871222fad5c48d305d77eb6a43a7dbe893cb238/diff",
                "WorkDir": "/var/lib/docker/overlay2/0fe70231ade73193860420790871222fad5c48d305d77eb6a43a7dbe893cb238/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "ee36da1004ae",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/apache2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "HTTPD_PREFIX=/usr/local/apache2",
                "HTTPD_VERSION=2.4.54",
                "HTTPD_SHA256=eb397feeefccaf254f8d45de3768d9d68e8e73851c49afd5b7176d1ecf80c340",
                "HTTPD_PATCHES="
            ],
            "Cmd": [
                "httpd-foreground"
            ],
            "Image": "httpd",
            "Volumes": null,
            "WorkingDir": "/usr/local/apache2",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {},
            "StopSignal": "SIGWINCH"
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "1ba76a3405de4a2482b2080681f900e8679abcf7456cdfbfd7976b83386254eb",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "80/tcp": [
                    {
                        "HostIp": "0.0.0.0",
                        "HostPort": "80"
                    },
                    {
                        "HostIp": "::",
                        "HostPort": "80"
                    }
                ]
            },
            "SandboxKey": "/var/run/docker/netns/1ba76a3405de",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "c4ad1c0119ea7ba10423bec00ee179fb234e83dbdf11cbfa31fa9bd8f7e9ca91",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.2",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:11:00:02",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "99fcd19da9a9349394b6958b3a29da42c0bb57af9565a02ba37f8075154add89",
                    "EndpointID": "c4ad1c0119ea7ba10423bec00ee179fb234e83dbdf11cbfa31fa9bd8f7e9ca91",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:11:00:02",
                    "DriverOpts": null
                }
            }
        }
    }
]
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:31:45]─[G:DockerWithHussein]
╰─>$ docker stop ee3
ee3
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:31:52]─[G:DockerWithHussein]
╰─>$ curl http://Arafats-MacBook-Pro.local
curl: (7) Failed to connect to Arafats-MacBook-Pro.local port 80 after 2262 ms: Connection refused
┬─[arafat@Arafats-MacBook-Pro:~]─[00:03:12]
╰─>$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:34:13]─[G:DockerWithHussein]
╰─>$ vim Dockerfile
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:34:13]─[G:DockerWithHussein]
╰─>$ cat Dockerfile
FROM httpd
RUN apt-get update
RUN apt-get install -y iputils-ping
RUN apt-get install -y inetutils-traceroute
RUN apt-get install -y iproute2
RUN apt-get install -y curl telnet dnsutils vim
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:17:47]─[G:DockerWithHussein]
╰─>$ docker build -t nhttpd .
[+] Building 21.5s (11/11) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                                       0.0s
 => => transferring dockerfile: 234B                                                                                                                                       0.0s
 => [internal] load .dockerignore                                                                                                                                          0.0s
 => => transferring context: 2B                                                                                                                                            0.0s
 => [internal] load metadata for docker.io/library/httpd:latest                                                                                                            3.9s
 => [auth] library/httpd:pull token for registry-1.docker.io                                                                                                               0.0s
 => [1/6] FROM docker.io/library/httpd@sha256:5fa96551b61359de5dfb7fd8c9e97e4153232eb520a8e883e2f47fc80dbfc33e                                                             0.0s
 => => resolve docker.io/library/httpd@sha256:5fa96551b61359de5dfb7fd8c9e97e4153232eb520a8e883e2f47fc80dbfc33e                                                             0.0s
 => [2/6] RUN apt-get update                                                                                                                                               5.4s
 => [3/6] RUN apt-get install -y iputils-ping                                                                                                                              1.2s
 => [4/6] RUN apt-get install -y inetutils-traceroute                                                                                                                      1.5s
 => [5/6] RUN apt-get install -y iproute2                                                                                                                                  1.9s
 => [6/6] RUN apt-get install -y curl telnet dnsutils vim                                                                                                                  7.3s
 => exporting to image                                                                                                                                                     0.2s
 => => exporting layers                                                                                                                                                    0.2s
 => => writing image sha256:886746e65efbc6f1e5cf787328d46bf12602308d31c3b39cd917195dbb1f3b2c                                                                               0.0s
 => => naming to docker.io/library/nhttpd                                                                                                                                  0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:19:47]─[G:DockerWithHussein]
╰─>$ docker ps -a
CONTAINER ID   IMAGE                 COMMAND                  CREATED         STATUS                      PORTS                                                                                                                                                 NAMES
8d9cbcb643cc   httpd                 "httpd-foreground"       3 hours ago     Exited (0) 10 minutes ago                                                                                                                                                         cool_darwin
7a79b76ecca8   rabbitmq:management   "docker-entrypoint.s…"   13 months ago   Exited (255) 4 weeks ago    4369/tcp, 5671/tcp, 0.0.0.0:5672->5672/tcp, :::5672->5672/tcp, 15671/tcp, 15691-15692/tcp, 25672/tcp, 0.0.0.0:15672->15672/tcp, :::15672->15672/tcp   rabbitmq
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:19:51]─[G:DockerWithHussein]
╰─>$ docker run --name s1 -d nhttpd
73d44c33dfa1eb41da4a3e5fc7c93f5b55fd03cb306ff8c46a84eb45063a4ce5
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:19:58]─[G:DockerWithHussein]
╰─>$ docker run --name s2 -d nhttpd
6b66f061b76b5969ce8963b36d643e9369062a140e274113aeeec33cb1ca2459
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:20:08]─[G:DockerWithHussein]
╰─>$ docker inspect 6b66
[
    {
        "Id": "6b66f061b76b5969ce8963b36d643e9369062a140e274113aeeec33cb1ca2459",
        "Created": "2022-11-02T18:20:07.844661838Z",
        "Path": "httpd-foreground",
        "Args": [],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 3975,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2022-11-02T18:20:08.039798546Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:886746e65efbc6f1e5cf787328d46bf12602308d31c3b39cd917195dbb1f3b2c",
        "ResolvConfPath": "/var/lib/docker/containers/6b66f061b76b5969ce8963b36d643e9369062a140e274113aeeec33cb1ca2459/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/6b66f061b76b5969ce8963b36d643e9369062a140e274113aeeec33cb1ca2459/hostname",
        "HostsPath": "/var/lib/docker/containers/6b66f061b76b5969ce8963b36d643e9369062a140e274113aeeec33cb1ca2459/hosts",
        "LogPath": "/var/lib/docker/containers/6b66f061b76b5969ce8963b36d643e9369062a140e274113aeeec33cb1ca2459/6b66f061b76b5969ce8963b36d643e9369062a140e274113aeeec33cb1ca2459-json.log",
        "Name": "/s2",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "host",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                0,
                0
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "KernelMemory": 0,
            "KernelMemoryTCP": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": null,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/642db748f77b35630d97b1d8f86e9c9732178035202b3e6c56d522c7209de61d-init/diff:/var/lib/docker/overlay2/x8y7iup5jnxagbj3elbk0jo9m/diff:/var/lib/docker/overlay2/57cl83p9aencyafjgog4repcv/diff:/var/lib/docker/overlay2/a2c3ijodwf9aacpfkgj1cu9cg/diff:/var/lib/docker/overlay2/jt34lc3dmlvhgk0i2pyfa4k2j/diff:/var/lib/docker/overlay2/sf6dejaawa0jekrurax1kp455/diff:/var/lib/docker/overlay2/4452719c06fd752d1d273c2ee3e81eb21d1927d32c94b9ab87ed51c888877937/diff:/var/lib/docker/overlay2/ddf37a3fa298d9849cca59cd0f54fd850d655025d69fbdbf3bf82c9f4192f6b6/diff:/var/lib/docker/overlay2/e38601c85136909b6de47682fe7f4b70ba1f5e905f3bb3540f62c4af3752102e/diff:/var/lib/docker/overlay2/856d5f18b56c8a30d14d56ea2b47ba793869e8f15660b9e0c4277f19105e8b41/diff:/var/lib/docker/overlay2/46301fd761f00f9b0d8f0002a3914042162567695c8d632d889956418a08d592/diff",
                "MergedDir": "/var/lib/docker/overlay2/642db748f77b35630d97b1d8f86e9c9732178035202b3e6c56d522c7209de61d/merged",
                "UpperDir": "/var/lib/docker/overlay2/642db748f77b35630d97b1d8f86e9c9732178035202b3e6c56d522c7209de61d/diff",
                "WorkDir": "/var/lib/docker/overlay2/642db748f77b35630d97b1d8f86e9c9732178035202b3e6c56d522c7209de61d/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "6b66f061b76b",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/apache2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "HTTPD_PREFIX=/usr/local/apache2",
                "HTTPD_VERSION=2.4.54",
                "HTTPD_SHA256=eb397feeefccaf254f8d45de3768d9d68e8e73851c49afd5b7176d1ecf80c340",
                "HTTPD_PATCHES="
            ],
            "Cmd": [
                "httpd-foreground"
            ],
            "Image": "nhttpd",
            "Volumes": null,
            "WorkingDir": "/usr/local/apache2",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {},
            "StopSignal": "SIGWINCH"
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "c143705209c124ba4bedd771281403e422824d4dcefaad39149e9e599742b6a9",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "80/tcp": null
            },
            "SandboxKey": "/var/run/docker/netns/c143705209c1",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "30f1c5cf43c8533576981bee9430203521825eabb51d6cefeaec7cd7154cfc9b",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.3",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:11:00:03",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "99fcd19da9a9349394b6958b3a29da42c0bb57af9565a02ba37f8075154add89",
                    "EndpointID": "30f1c5cf43c8533576981bee9430203521825eabb51d6cefeaec7cd7154cfc9b",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.3",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:11:00:03",
                    "DriverOpts": null
                }
            }
        }
    }
]
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:22:39]─[G:DockerWithHussein]
╰─>$ docker inspect bridge
[
    {
        "Name": "bridge",
        "Id": "99fcd19da9a9349394b6958b3a29da42c0bb57af9565a02ba37f8075154add89",
        "Created": "2022-11-02T15:25:55.789102625Z",
        "Scope": "local",
        "Driver": "bridge",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": null,
            "Config": [
                {
                    "Subnet": "172.17.0.0/16",
                    "Gateway": "172.17.0.1"
                }
            ]
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {
            "6b66f061b76b5969ce8963b36d643e9369062a140e274113aeeec33cb1ca2459": {
                "Name": "s2",
                "EndpointID": "30f1c5cf43c8533576981bee9430203521825eabb51d6cefeaec7cd7154cfc9b",
                "MacAddress": "02:42:ac:11:00:03",
                "IPv4Address": "172.17.0.3/16",
                "IPv6Address": ""
            },
            "73d44c33dfa1eb41da4a3e5fc7c93f5b55fd03cb306ff8c46a84eb45063a4ce5": {
                "Name": "s1",
                "EndpointID": "dce204ab3276fbf3455c2be99797b5eb028eaf466c5bf4be405e2a70e74cf9e9",
                "MacAddress": "02:42:ac:11:00:02",
                "IPv4Address": "172.17.0.2/16",
                "IPv6Address": ""
            }
        },
        "Options": {
            "com.docker.network.bridge.default_bridge": "true",
            "com.docker.network.bridge.enable_icc": "true",
            "com.docker.network.bridge.enable_ip_masquerade": "true",
            "com.docker.network.bridge.host_binding_ipv4": "0.0.0.0",
            "com.docker.network.bridge.name": "docker0",
            "com.docker.network.driver.mtu": "1500"
        },
        "Labels": {}
    }
]
┬─[arafat@Arafats-MacBook-Pro:~/W/p/B/DockerWithHussein]─[00:22:44]─[G:DockerWithHussein]
╰─>$
