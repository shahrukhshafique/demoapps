# Define base image that includes dev tools
FROM mcr.microsoft.com/dotnet/sdk:5.0 as DevEnv
#FROM mcr.microsoft.com/dotnet/sdk:5.0

# Create a folder
WORKDIR /app

# Copy the project file
COPY *.csproj ./

# Restore dotnet libraries for the project
RUN dotnet restore

# Copy all application files
COPY . ./

# Compile project and create production binaries
RUN dotnet publish -c Release -o /app/out

# Download another images with aspnet runtime
FROM mcr.microsoft.com/dotnet/aspnet

# Copy from the first image (DevEnv) binaries
COPY --from=DevEnv /app/out .
#
EXPOSE 80
# Define the process to be executed in the container
ENTRYPOINT [ "dotnet", "HelloWorld.dll" ]
