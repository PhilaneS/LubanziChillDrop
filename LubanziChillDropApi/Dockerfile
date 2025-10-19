# Stage 1: Build
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /app

# Copy only the project file first
COPY LubanziChillDropApi.csproj ./
RUN dotnet restore LubanziChillDropApi.csproj

# Copy everything else
COPY . ./
RUN dotnet publish LubanziChillDropApi.csproj -c Release -o /out

# Stage 2: Runtime
FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS runtime
WORKDIR /app
COPY --from=build /out .

EXPOSE 80
ENTRYPOINT ["dotnet", "LubanziChillDropApi.dll"]
