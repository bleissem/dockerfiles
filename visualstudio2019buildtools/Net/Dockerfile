# escape=`
ARG REPO=mcr.microsoft.com/dotnet/framework/sdk
FROM $REPO:4.8-windowsservercore-ltsc2019

SHELL ["cmd", "/S", "/C"]

RUN curl -fSLo vs_BuildTools.exe https://download.visualstudio.microsoft.com/download/pr/c650b629-fb28-4b7a-b943-1d293b185299/5303c184326b53784d6822601cce9eab01660410078b496102117e88c2eee1bb/vs_BuildTools.exe

RUN  setx /M DOTNET_SKIP_FIRST_TIME_EXPERIENCE 1
RUN  start /w vs_BuildTools.exe ^ `
    --add Microsoft.VisualStudio.Component.SQL.SSDTBuildSku ^ `
    --add Microsoft.Component.MSBuild ^ `
    --add Microsoft.VisualStudio.Component.CoreBuildTools ^ `
    --add Microsoft.VisualStudio.Component.Roslyn.Compiler ^ `
    --add Microsoft.NetCore.BuildTools.ComponentGroup ^ `
    --add Microsoft.NetCore.Component.SDK ^ `
    --add Microsoft.VisualStudio.Component.NuGet.BuildTools ^ `
    --add Microsoft.VisualStudio.Component.VSSDKBuildTools ^ `
    --quiet --norestart --nocache --wait 

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]
