# escape=`
ARG version=ltsc2019
FROM mcr.microsoft.com/windows/servercore:$version
RUN @powershell -NoProfile -ExecutionPolicy Unrestricted  -Command "$env:ChocolateyUseWindowsCompression='false'; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin" 
SHELL ["powershell"]
RUN choco --version