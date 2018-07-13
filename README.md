# proxmox-pve-tools
Few utilities for Proxmox PVE maintenance

## qcow2-check
QCOW2 files are very performant, bud badly protected. It may happen that the file gets corrupted, sometimes unrecoverable, and it often happens while creating a snapshot. Such damage can be prevented by checking the QCOW2 file. It is safe to run this check on running VM disks.

If a file is detected as damaged, move in to another place (using the disk move function in Proxmox), and it will get fixed.

## qcow2-check-all
This script will search QCOW2 files in all the defined storage paths, and then check them with qcow2-check.

## ssl-check
If you did change the SSL certificates with yours, adding a machine can be painful. This script will check that all the SSL keys and certificated match, and warn in case of error.

## ssl-gen-csr-for-myself
If you want to use your own certificates, you might want to generate a CSR file. In such case, join the cluster using « pvecm add », and you will get an error telling that the certificate cannot be generated. Once done, run this script on the new machine, and you will get the CSR to sign by your CA. This script requires the « openssl.cnf » file in the same folder.
