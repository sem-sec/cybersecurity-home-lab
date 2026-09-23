# Linux Fundamentals

## Environment
- Ubuntu 26.04.1 LTS running in VirtualBox on Windows


## Skills Practiced

### File system navigation
- `cd`, `ls`, `ls -la`, `pwd`

### File and directory management
- `mkdir`, `touch`, `rm`, `nano`, `cat`

### File permissions
- Used `chmod` with numeric modes (700, 755, 644, 600)
- Understood read/write/execute permissions for owner, group, and others

### Package management
- `sudo apt update`, `sudo apt install`
- Learned to check package availability with `apt search` before installing

### Networking tools
- `ip a` — viewing network interfaces and IP addresses
- `ping` — testing connectivity
- `nslookup`, `dig` — DNS resolution
- `traceroute` — tracing network routing hops
- `ss -tuln` — viewing open/listening ports
- `curl -I` — inspecting HTTP response headers

## Notable Troubleshooting

- The `neofetch` package has been deprecated and removed from Ubuntu's repositories. Identified this via an "unable to locate package" error, searched for the actively maintained alternative (`fastfetch`), and installed it successfully.
- Ran a local Python HTTP server (`python3 -m http.server`) and observed directory listing exposure firsthand, including visibility of `.ssh` and `.bash_history` — a practical demonstration of why default web server configurations can accidentally expose sensitive files.
