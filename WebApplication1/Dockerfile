FROM mcr.microsoft.com/dotnet/core/aspnet:7.0

WORKDIR /app

COPY --from=build-env /app/out .


EXPOSE 80

ENTRYPOINT ["dotnet", "WebApplication1.dll"]