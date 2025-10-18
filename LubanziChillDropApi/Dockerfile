FROM mcr.microsoft.com/dotnet/aspnet:9.0 AS base
WORKDIR /app
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/LubanziChillDropApi.dll"]
