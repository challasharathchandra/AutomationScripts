## A ruby Script to test whether you are able to depoy your application to CF platform or not


# Instructions to use ruby script.
1) First install Ruby
2) Check if gem command is working or not in command prompt or terminal.
3) Check if cloud foundry cli is installed or not.
    refer below link https://github.com/cloudfoundry/cli
3) Run the following commands
    ```
    gem install cf-uaac
    gem install colorize
    gem install json
    ```
4) If you are using windows then install curl
5) open the file main.rb and make some changes as per your system configuration.</br>
   ```
   In this file, go to main() method.
    @home_directory= enter your home path in quotes
    @curl_path=?
    	If curl environmental variable is not working
          then @curl_path = path to curl executable in your system in quotes
   	If curl enviromental variable is working
          then @curl_path = some dummy path which have read and write access in quotes
    @curl_command = ?
        If you are windows users and curl enviromental is not working then
          @curl_command = "curl.exe"
	if you are linux users then
	  @curl_command = "curl"
    @dummy_directory = enter some dummy path which have read and write access in quotes.
   ```
**Note**: Windows users  must use / rather than \ in between the directories.</br>

6) when you run the script, it will prompt for entering the data from the user.
   ```
   project name : name of the folder in your system which contains source files of the application
      if those files are not present in your system then provide some dummy path here
      In next instance it will ask for the path to the above folder
      here provide any path you like, your source files from git will be downloaded to this path
   ```
7) service name is the name of the service you want to use for creation of service instance.

8) if you see yellow color means the script is waiting for your input.

9) if you see green color means the script execution is success.

10) if you see red color means the script execution is failed.</br>
    press Ctrl+c to stop the execution and read the error.</br>
11) if you see execution failed with out giving the red color,</br>
    this may arise out of program logic then report this incident.</br>
12) create the following folders.
    ```
    /opt/cloudfoundry/gitzip/redis
    /opt/cloudfoundry/gitzip/rabbitmq
    /opt/cloudfoundry/gitzip/postgres
    /opt/cloudfoundry/project
   ```
13) If you want to change any defaults, you can change them in main.rb file.
14) After all modifications are done, you can run the main.rb file with the following command.
    ```
    ruby main.rb
    ```
