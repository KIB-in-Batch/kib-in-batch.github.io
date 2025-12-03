# The KIB in Batch project

![alt text](./kali_in_batch_logo.png)

KIB in Batch is a lightweight UNIX-like environment for MS-Windows.

## Compare to alternatives

KIB is a lot lighter than alternatives like Cygwin, WSL and Msys2. This makes it better for constrained environments like IoT devices. But the POSIX layer is less complete, therefore making KIB have to use a Win32 port of BusyBox. For a complete POSIX implementation, use the alternatives I mentioned.

## Features

### Control what to install

KIB has the KIB-pkg package manager, and installing Nmap and Neovim in the setup is fully optional.

### Lightweight

KIB is in fact lightweight.

## FAQ

### Will KIB allow me to run Linux applications on MS-Windows natively?

No.

### Is this safe to run?

Yes, it works perfectly on my machine!

### Where is 11.0.0? 10.2.6 came out months ago!

It is a very large release, I am gonna take longer than usual to release it.