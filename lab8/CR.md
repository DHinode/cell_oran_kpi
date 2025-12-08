# Task 1: 
`sudo docker-compose -f docker-compose-5g-core.yaml up -d`

To build the gNB and the UE : 
```bash
student@lab-vms-gw:~$ cat Readme.md 
git clone --depth 1 -b develop https://gitlab.eurecom.fr/oai/openairinterface5g.git /home/student/openairinterface5g


cd /home/student/openairinterface5g/cmake_targets
sudo ./build_oai -I




cd /home/student/openairinterface5g/cmake_targets
sudo ./build_oai --gNB --nrUE -w SIMU --ninja


git clone --depth 1 https://github.com/openaicellular/flexric.git /home/student/flexric


cd /home/student/flexric
mkdir -p build
cd build
cmake ..
make -j$(nproc)
sudo make install


check 

stat /home/student/openairinterface5g/cmake_targets/ran_build/build/nr-softmodem

stat /home/student/flexric/build/examples/ric/nearRT-RIC
```

# Task 2 :
```bash
student@lab-vm-23:~/labs_cell/lab8$ docker ps
CONTAINER ID   IMAGE                                     COMMAND                  CREATED         STATUS                            PORTS                                    NAMES
d074ca701e6c   oaisoftwarealliance/oai-udr:v2.1.0        "/openair-udr/bin/oa…"   3 minutes ago   Up 3 minutes (healthy)            80/tcp, 8080/tcp                         oai-udr
03285a048b18   oaisoftwarealliance/oai-upf:v2.1.0        "/openair-upf/bin/oa…"   3 minutes ago   Up 3 minutes (healthy)            2152/udp, 8805/udp                       oai-upf
12bd6c4ef57d   oaisoftwarealliance/oai-amf:v2.1.0        "/openair-amf/bin/oa…"   3 minutes ago   Up 3 minutes (healthy)            80/tcp, 8080/tcp, 9090/tcp, 38412/sctp   oai-amf
9cc0bfe52e20   oaisoftwarealliance/oai-udm:v2.1.0        "/openair-udm/bin/oa…"   3 minutes ago   Up 3 minutes (healthy)            80/tcp, 8080/tcp                         oai-udm
d49935b0f7b2   oaisoftwarealliance/oai-ausf:v2.1.0       "/openair-ausf/bin/o…"   3 minutes ago   Up 3 minutes (healthy)            80/tcp, 8080/tcp                         oai-ausf
13a2cc245ce0   oaisoftwarealliance/oai-smf:v2.1.0        "/openair-smf/bin/oa…"   3 minutes ago   Up 3 minutes (healthy)            80/tcp, 8080/tcp, 8805/udp               oai-smf
5b7cceeda4f8   oaisoftwarealliance/trf-gen-cn5g:latest   "/bin/bash /tmp/trfg…"   3 minutes ago   Up 3 minutes (healthy)                                                     oai-ext-dn
db072ff0a0e4   mysql:8.0                                 "docker-entrypoint.s…"   3 minutes ago   Up 3 minutes (health: starting)   3306/tcp, 33060/tcp                      mysql
01562fb002a5   oaisoftwarealliance/oai-nrf:v2.1.0        "/openair-nrf/bin/oa…"   3 minutes ago   Up 3 minutes (healthy)            80/tcp, 8080/tcp, 9090/tcp               oai-nrf
```

