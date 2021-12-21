# DeployDatabaseInDocker

What is [docker](https://docker-curriculum.com/#what-is-docker-)

[Docker overview](https://docs.docker.com/get-started/overview/)

## Install Docker on Windows

1. [Activate WSL 2](https://docs.microsoft.com/en-us/windows/wsl/install)

    * Open a powershell with admin privileges and run `wsl --install`
    * A reboot will be required at the end of the installation process

2. After the installatin processes finishes you will need to [define a linux user and password](https://docs.microsoft.com/en-us/windows/wsl/setup/environment#set-up-your-linux-username-and-password)

3. Check if you have WSL2 active by runnig `wsl -l -v`. If you see `2` under the Version column that you have version 2. If not switch to version 2 with the command `wsl --set-default-version 2`

4. Download the docker desktop installer from [docker hub](https://hub.docker.com/editions/community/docker-ce-desktop-windows/)

5. Run the installer by double clicking on `Docker Desktop Installer.exe`

6. To validate that Docker was installed correctly run `docker run hello-world` in a console. If everything is ok you should get back the message: `Hello from Docker!` then everything is running fine.

7. To see the [image](https://docs.docker.com/get-started/overview/#docker-objects) and the [container](https://docs.docker.com/get-started/overview/#docker-objects), run the `Docker Desktop` app and navigate to the `Containers/Apps` tab. In the `Images` tab you will be able to the the docker images.

8. More about docker commands [here](https://docs.docker.com/engine/reference/run/)

## [Install MS SQL server 2019](https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver15&pivots=cs1-powershell)

1. In powershell run `docker pull mcr.microsoft.com/mssql/server:2019-latest`

2. Run the sql server with ```docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Strong@Passw0rd" `
   -p 1433:1433 --name container_name -h container_name `
   -d mcr.microsoft.com/mssql/server:2019-latest```

3. You can connect to the MS SQL server running in docker with [SQL Server Management Studio](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15)

    * The `Server name` is `localhost,1433`
    * For authentication select `SQL Server Authentication`
    * The `Login` user is `SA`
    * The `Password` is the one defined in the `docker run` command

4. To open a shell in the container run `docker exec -it container_name bash`

5. To exit the bash type `exit`

