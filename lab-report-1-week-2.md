[Download VScode](https://code.visualstudio.com/Download)
* Make sure to download the correct installer for your operating system

To remotely connect to the ieng6 computer, you will need to enter this command(ssh cs15lsp22<username>@ieng6.ucsd.edu) into the VScode terminal
* [Look up your username and password for ieng6 computer](https://sdacs.ucsd.edu/~icc/index.php)
* Enter your school email and PID
* [Set your password with this tutorial](https://cdn-uploads.piazza.com/paste/ktv2gnof3sx5bf/181c3cb053df5cf1ccaf0457f56f12a2e5aa90b139aef8c2ea8fcc590f02fadf/How-to-Reset-your-Password.pdf)

Some useful commands
* type exit of ctrl+d to log out
* pwd to check current directory
* cd to change directory, cd ~ will change to homepage, cd .. will go to the previous directory
* cp <file1> <directory> to copy a file's content to a directory, can be another file to override it

To copy a file from your computer to the remote computer, use the command (scp <file> cs15lsp22<username>@ieng6.ucsd.edu)
* if it worked, it should ask you for your password
* remember to log out of the remote computer before copying something from your computer
  
To speed up the process of accessing the remote computer, you can set up a SSH key to eliminate the need of entering password
* Use the command ssh keygen
* for Windows operating system, follow this tutorial after

To further optimize remote running, you can combine commands into one line that you can copy everytime you want to copy a file to the remote computer
* 
