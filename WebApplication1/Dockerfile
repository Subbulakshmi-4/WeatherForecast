# Build stage
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build-env
WORKDIR /app
 
# Copy the project file and restore dependencies
COPY *.csproj ./
RUN dotnet restore
 
# Copy the rest of the code and build the application
COPY . ./
RUN dotnet publish -c Release -o out
 
# Runtime stage
FROM mcr.microsoft.com/dotnet/aspnet:7.0
WORKDIR /app
COPY --from=build-env /app/out .
 
# Expose port and define entrypoint
EXPOSE 80
ENTRYPOINT ["dotnet", "WebApplication1.dll"]
 