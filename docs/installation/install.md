# Installation Guide

## Prerequisites
3D Visualizer requires Vrui version 14.0 build 001 or newer. To read images in PNG, JPEG, or TIFF formats, libpng, libjpeg, or libtiff have to be installed, respectively, and Vrui has to be configured with support for these image formats (see [Vrui's documentation](https://github.com/vrui-vr/vrui/blob/main/docs/installation/index.md)). To include collaboration functionality, 3D Visualizer requires the Vrui Collaboration Infrastructure version 10.3 or newer.

It is recommended to download or move the source packages for Vrui and 3D Visualizer into a src directory underneath the user's home directory. Otherwise, references to ~/src in the following instructions need to be changed.

It is also recommended to skip optional steps 4 and 6 in the following instructions. 3D Visualizer does not need to be installed in order to be used; installation (to a system directory such as /usr/local) is only recommended if 3D Visualizer will be used from multiple user accounts.

??? info "Heads up!"
    Angle brackets `<>` in commands below are placeholders, meaning that you have to replace everything between, and including, the angle brackets with some text that depends on your specific circumstances.

0. Install Vrui by running: 

    ```sh
    ~/src/Vrui-<version>-<build>
    ``` 

1. Change into the `~/src` directory and unpack the 3D Visualizer tarball in one of the two following ways:

    ```sh
    cd ~/src
    tar xfz <download path>/3DVisualizer-<version>.tar.gz
    ```

    Or:

    ```sh
    cd ~/src
    tar xf <download path>/3DVisualizer-<version>.tar
    ```

2. Change into 3D Visualizer base directory:
    
    ```sh
    cd 3DVisualizer-<version>
    ```

3. If the Vrui version installed in step 0 was not 14.0, or Vrui's installation directory was changed from the default of `/usr/local`, adapt the makefile using a text editor. Change the value of `VRUI_MAKEDIR` close to the beginning of the file as follows:
    
    ```sh
    VRUI_MAKEDIR := <Vrui install dir>/share/make
    ```

    `<Vrui install dir>` should be the installation directory chosen in step 0. Use `$(HOME)` to refer to the user's home directory instead
    of `~`.


4. *Optional:* Adapt the makefile if you'd like to install 3D Visualizer in a different location, for example, `/usr/local`, by setting `INSTALLDIR` to the desired target location. 3D Visualizer will be then be installed in `$(INSTALLDIR)/bin`, `$(INSTALLDIR)/lib` (or `$(INSTALLDIR)/lib64` on 64-bit Linux systems), and `$(INSTALLDIR)/share/3DVisualizer-<version>`.

    !!! important 
        Do not use `~` as a shortcut for the user's home directory here, use `$(HOME)` instead. For example, write `INSTALLDIR = $(HOME)/apps` instead of `INSTALLDIR = ~/apps`.

5. Build 3D Visualizer by running:
    
    ```sh
    make
    ```

6. *Optional:* Install 3D Visualizer in the selected target location. This is only necessary if the `INSTALLDIR` variable in the makefile was changed. By default, 3D Visualizer can be run from its base directory. To install, either run:

    ```sh
    make install
    ```

    Or, if the target location is a system directory:

    ```sh
    sudo make install
    ```

7. *Optional*: Add the directory containing the 3D Visualizer executable (`~/src/3DVisualizer-<version>/bin` in the default installation, `$(INSTALLDIR)/bin` otherwise) to the user's search path. This allows you to run 3D Visualizer from any directory. 

    - Using csh or tcsh, run either: 

        ```sh
        setenv PATH ${PATH}:~/src/3DVisualizer-<version>/bin
        ```

        Or, with <INSTALLDIR> as the target location set in the makefile: 

        ```sh
        setenv PATH ${PATH}:<INSTALLDIR>/bin
        ```

    - Using bash:

        ```sh
        export PATH=${PATH}:~/src/3DVisualizer-<version>/bin
        ```

        Or: 

        ```sh
        export PATH=${PATH}:<INSTALLDIR>/bin
        ```
        
        ???+ tip
            These lines can also be added to the user's .cshrc or .bashrc files to make the additions persist between logins.
