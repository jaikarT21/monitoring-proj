# ==========================
# STAGE 1 — Build Application
# ==========================
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build

WORKDIR /src

# Copy csproj and restore

COPY . . 

RUN dotnet restore 


# Build the application
RUN dotnet publish -c Release -o /app/publish


# ==========================
# STAGE 2 — Run Application
# ==========================
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS final

WORKDIR /app

COPY --from=build /app/publish .

EXPOSE 5000

ENTRYPOINT ["dotnet", "dotnet-demoapp.dll"]


