## Streamlining ssh Configuration
* go to `.ssh` directory
* add a file named `config`, if it doesn't exist already
  * in the file add these lines:
    ```
    Host ieng6
      HostName ieng6.ucsd.edu
      User cs15lsp22zzz (replace zzz with your username)
   * ![](/Image/Config.png)
* if done properly, this command `ssh ieng6` should log in to your ieng6 account
  * ![](/Image/SSHieng6.png)
* this should also work with `scp <file directory> ieng6:<target directory>`
  * ![](/Image/SCPieng6.png)
* if that didn't work try adding a line in config to explicitly refer to your id_rsa file
  * in the file copy these lines:
    ```
    Host ieng6
      HostName ieng6.ucsd.edu
      User cs15lsp22zzz (replace zzz with your username)
      IdentityFile ~/.ssh/id_rsa (double check your address, \ or /

## Setup Github Access from ieng6
 * `ssh-keygen` in ieng6 account
  * the private key should be in the .ssh folder
    * ![](/Image/PrivateKey.png)
  * save the public key content, go to the .ssh directory and use `cat id_rsa.pub` command
  * go to [github.com/settings/keys](github.com/settings/keys)
    * create new SSH key and enter the content saved
    * after succefully added, the key should show up:![](/Image/PublicKey.png)
* after the keys are set up, you can successfully `git push` or `git pull` on your ieng6 account  
  * example of `git push`: ![](/Image/GitCP.png)
    * [commit link](https://github.com/shootingdarts/SkillDemo/commit/95132f03d45ab0fbfdffd4ee9d61179c2f410acd)

## Copy whole directories with `scp -r`
* use command `scp -r <directory> ieng6:<target directory>`
  * example: ![](/Image/SCP-r.png)
  * MarkdownParseTest.java compiled and ran properly
    * ![](/Image/Test.png)
* use this format to perform everything in one line `scp -r <directory> ieng6:<target directory>; ssh ieng6 "<commands to run remotely>"`
  * example: `scp -r .\Documents\GitHub\markdown-parser ieng6:~/; ssh ieng6 "cd markdown-parser"; /software/CSE/oracle-java-17/jdk-17.0.1/bin/javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java; /software/CSE/oracle-java-17/jdk-17.0.1/bin/java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest"`
