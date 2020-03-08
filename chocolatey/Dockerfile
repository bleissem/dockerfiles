ARG version=ltsc2019
FROM mcr.microsoft.com/windows/servercore:$version

ENV chocolateyUseWindowsCompression true
RUN powershell -c Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))