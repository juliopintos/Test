# syntax=docker/dockerfile:1
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env
WORKDIR /home/julio/WebApp01

# Copy everything else and build
#COPY ../engine/examples ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /home/julio/WebApp01
COPY --from=build-env /home/julio/WebApp01/out .
ENTRYPOINT ["dotnet", "WebApp01.dll"]