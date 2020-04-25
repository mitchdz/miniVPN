## miniVPN-vagrant
## Prerequisites
- Vagrant
- Virtualbox

To provision the virtual machines for miniVPN, simply run
```
vagrant up
```
Which will provision 3 machines with the following allocation:

| machine | IP |
| ------- | -- |
| client | 10.0.2.7 |
| server | 10.0.2.8 & 192.168.60.1 |
| target | 192.168.60.101 |

to access the machines, simply run the following command

```
vagrant ssh [client|server|target]
```
where you choose one of the three machines, (client, server, target).


---
  ![UofA](images/UofA.jfif)
