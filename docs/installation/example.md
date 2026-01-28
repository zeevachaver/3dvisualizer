# Running 3D Visualizer: Alaska Example Data

These instructions assume that 3D Visualizer was installed in its base directory, (see steps 4 and 6 in the [installation guide](https://github.com/vrui-vr/3dvisualizer/docs/installation/install.md)).

??? info "Heads up!"
    Angle brackets `<>` in commands below are placeholders, meaning that you have to replace everything between, and including, the angle brackets with some text that depends on your specific circumstances.

1. Change into 3D Visualizer base directory by running:
    
    ```
    cd ~/src/3DVisualizer-<version>
    ```

2. Download the example data tarball AlaskaData.tar.gz.

3. Unpack the example data tarball in the 3D Visualizer directory, using either: 

    ```
    tar xfz <download path>/AlaskaData.tar.gz
    ```
    
    Or: 
    
    ```
    tar xf <download path>/AlaskaData.tar
    ```

4. On MacOS X: Start X11. 3D Visualizer requires a running X server but, if preferred, it can be started from a MacOS X terminal instead of xterm. <!-- ^Figure out better formatting -->

5. To run 3D Visualizer on the example data, run either:
    
    ```
    ./bin/3DVisualizer -palette AlaskaData/slab2.pal AlaskaData/slab2.in
    ```
    
    Or (with the full command line): 

    ``` 
    ./bin/3DVisualizer -palette AlaskaData/slab2.pal -class MultiCitcomtFile AlaskaData/slab2.dat Temp "log(Visc)" 
    ```

6. See Vrui's HTML documentation or 3D Visualizer's user's guide on Vrui's basic user interface and how to use 3D Visualizer.

