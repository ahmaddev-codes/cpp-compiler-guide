# cpp-compiler-guide
This guide will walk you through setting up **MSYS2** so you can have the latest `g++` and avoid weird silent fails.
We’ll go step-by-step

## **Step 1 — Download MSYS2**

1. Go to: [https://www.msys2.org](https://www.msys2.org)
2. Download the installer for Windows.
3. Run it, and install MSYS2 in the default location (`C:\msys64`).

## **Step 2 — Update the base system**

1. Open **MSYS2 MSYS** from the Start Menu (pink terminal).
2. Run:

```bash
pacman -Syu
```

3. If it says “close the terminal”, close it and reopen MSYS2 MSYS.
4. Run again:

```bash
pacman -Syu
```

until it’s fully up to date.


## **Step 3 — Install the latest g++**

1. In MSYS2 MSYS, run:

```bash
pacman -S mingw-w64-ucrt-x86_64-gcc
```

This installs the latest stable **GCC** (includes `g++`).

## **Step 4 — Use the MinGW terminal for compiling**

1. From Start Menu, open **MSYS2 MinGW UCRT64** terminal (blue icon).
2. Navigate to your project folder:

```bash
cd /c/Users/omega/Desktop/project/practise
```

3. Compile:

```bash
g++ odd.cpp -o output.exe
```

4. Run:

```bash
./output.exe
```

## **Step 5 — Make `g++` available in Windows PowerShell**

If you still want to compile from **PowerShell**, you’ll need to add MSYS2’s bin path to your system PATH:

1. Go to **Start → Edit the system environment variables → Environment Variables**.
2. In *System variables*, select `Path`, click **Edit**, and add:

```
C:\msys64\mingw64\bin
```

(or `C:\msys64\ucrt64\bin` if you used UCRT64).
3\. Restart PowerShell and check:

```powershell
g++ --version
```

It should now show a **much newer version** (e.g., 13.x).
