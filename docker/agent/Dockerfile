FROM jetbrains/teamcity-agent:latest

USER root

#install .NET 8.0 sdk
RUN apt-get update && \
    apt-get install -y wget && \
    wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb && \
    dpkg -i packages-microsoft-prod.deb && \
    apt-get update && \
    apt-get install -y apt-transport-https && \
    apt-get update && \
    apt-get install -y dotnet-sdk-8.0 && \
    rm -rf /var/lib/apt/lists/*

RUN dotnet tool install Microsoft.SqlPackage --tool-path /usr/local/bin


USER buildagent


