# escape=`
ARG version=ltsc2019
FROM mcr.microsoft.com/windows/servercore:$version
RUN @powershell -NoProfile -ExecutionPolicy Unrestricted  -Command "$env:ChocolateyUseWindowsCompression='false'; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin;%PROGRAMFILES%\PowerShell\7" 
SHELL ["powershell"]

RUN choco install git powershell-core -y --ignoredetectedreboot --ignorepackagecodes

# https://docs.microsoft.com/de-de/visualstudio/install/workload-component-id-vs-build-tools?view=vs-2019
RUN choco install visualstudio2019buildtools -y --ignoredetectedreboot --ignorepackagecodes --package-parameters "--allWorkloads --includeRecommended --includeOptional --passive --quiet --norestart --nocache --locale en-US"