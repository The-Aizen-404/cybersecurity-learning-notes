# Nmap basics (localhost and authorized labs)

Nmap identifies hosts and reports port states and, when requested, services. Use it only on `127.0.0.1`, systems you own, or targets for which you have explicit authorization. Written permission is the safest basis for testing; provider rules and local laws may also apply.

## Check the installed version

```sh
nmap --version
```

## Scan selected TCP ports on this computer

```sh
nmap -p 22,80,443 127.0.0.1
```

`127.0.0.1` is the loopback address for the machine running Nmap. `-p` limits the scan to the listed port numbers.

## Ask Nmap to identify services on those ports

```sh
nmap -sV -p 22,80,443 127.0.0.1
```

`-sV` enables service/version detection. It sends additional probes, so keep the target and port range within the authorized scope.

## Read the port states

- `open`: an application is listening on the port.
- `closed`: the host responded, but no application was listening on that port at scan time.
- `filtered`: a firewall or other network obstacle prevents Nmap from determining whether the port is open or closed.

A scan result is a point-in-time observation, not proof that a system is secure or vulnerable.

## References

- [Nmap Reference Guide](https://nmap.org/book/man.html)
- [Nmap legal issues and authorization guidance](https://nmap.org/book/legal-issues.html)
