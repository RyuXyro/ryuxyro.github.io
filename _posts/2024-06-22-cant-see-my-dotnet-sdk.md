---
title: "I Cant See my dotnet SDK!!"
categories:
  - blog
tags:
  - page
  - dotnet
---

# Here some tutorial

Run where dotnet from the command line. If the output is similar to:
```bash
C:\Program Files (x86)\dotnet\dotnet.exe
C:\Program Files\dotnet\dotnet.exe
```

Then both the 32-bit and 64-bit versions of the SDK have been installed at some time.
```bash
32 bit --- C:\Program Files (x86)\dotnet\dotnet.exe
64 bit --- C:\Program Files\dotnet\dotnet.exe
```
---
The first SDK installed on the computer puts the dotnet path in the system path. Any subsequent SDK install of a different bit size SDK also adds dotnet path to the system path, but after the first dotnet path. Therefore, only SDK's of the first bit size are available by default, using the path variable.

There are two approaches to fixing the problem:

1. Install the latest SDK with the other bit size. This is the easiest solution.
2. Change the order of `C:\Program Files (x86)\dotnet\dotnet.exe` and `C:\Program Files\dotnet\dotnet.exe` in the System environment variables path:

Select the windows key and enter Edit, then select Edit the system variables
![](https://i.sstatic.net/g7b7X.png)


Select the Environment Variables button on the Advanced tab:
![](https://i.sstatic.net/2IvJq.png)


Select the Path > Edit under System variables (not User variables).
![](https://i.sstatic.net/brrh3.png)


Find the entries for `C:\Program Files\dotnet\dotnet.exe` (64 bit) and `C:\Program Files\dotnet\dotnet.exe` (32 bit) and using the Move up button, change to order. Here's an example:
![](https://i.sstatic.net/HHYGZ.png)


Select the **OK** button until all the windows are closed. Open a new command prompt and run where dotnet.

Answer from https://github.com/dotnet/core/issues/5962 More details at https://weblog.west-wind.com/posts/2019/Apr/20/Adventures-in-NET-SDK-Installation-SDKs-not-Showing-Up

---

*Source: https://stackoverflow.com/questions/67049414/windows-or-visual-studio-2022-cant-find-the-latest-installed-net-sdk-due-to-bi/67049415#67049415*



