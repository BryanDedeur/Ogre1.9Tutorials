# How to setup Ogre 1.9 on Ubuntu 18.04

# Installing Dependencies

See this page for dependency information [https://ogrecave.github.io/ogre/api/latest/building-ogre.html](https://ogrecave.github.io/ogre/api/latest/building-ogre.html)

1. Open Terminal (CTRL+ALT+T)
2. Update already installed package dependencies 
3. Install new dependencies for Ogre
```
sudo apt-get update
    
sudo apt-get install libgles2-mesa-dev libxt-dev libxaw7-dev nvidia-cg-toolkit libsdl2-dev doxygen cmake libfreetype6-dev libfontconfig1-dev xclip zlibc zlib1g zlib1g-dev zziplib-bin -y pugixml-doc libsdl2-2.0 libsdl2-dev libfreeimage-dev doxygen graphviz nvidia-cg-toolkit libboost-all-dev libpoco-doc libpoco-dev libtbb-dev libois-1.3.0v5 libois-dev mercurial libboost-all-dev automake cmake libtool libfreetype6-dev libfreeimage-dev libzzip-dev libxrandr-dev libxaw7-dev freeglut3-dev libgl1-mesa-dev libglu1-mesa-dev libxt-dev libpng16-16 nvidia-cg-toolkit libois-dev doxygen graphviz libcppunit-dev mercurial subversion git
```
Some dependencies might change, if you have any errors while installing dependencies 

# Installing Ogre

1. Make directory for Ogre v1.9 download and navigate to directory
2. Download Ogre v1.9 from Ogre Bit Bucket
```
mkdir ~/Downloads/Ogre-v1-9 && cd ~/Downloads/Ogre-v1-9
    
hg clone https://bitbucket.org/sinbad/ogre/src/v1-9/ && cd v1-9
```
3. Make build directory and move into it, stage the installation with cmake
```
mkdir build && cd build && cmake ..
```
4. Determine how many cores your computer has and specify how many cores make should utilize (make -j 4 or make -j 8)

5. Build with make (takes a while)

6. Install built content
```
grep -c ^processor /proc/cpuinfo
    
make -j 8
    
sudo make install
```
### How to check if install worked properly

1. Run the Oger sample browser (in the built binary directory) cd 
```
cd bin
    
./SampleBrowser
```
2. Navigate to the following directory to see if it exists

```
/usr/local/include/OGRE
    
/usr/local/share/OGRE
```

### (Optional) Remove unnecessary downloaded content

    cd ~/Downloads
    
    sudo rm -rf Ogre-v1-9

# Installing Latest Eclipse IDE with C/C++ Package

Eclipse version 2019-03 (4.11.0)

Install the java run time environment

Then install ecplise

    sudo apt install default-jre
    
    sudo snap install eclipse classic

Then to install Eclipse CDT C/C++ IDE

1) run Eclipse

2) navigate to Help -> Eclipse Marketplace -> Search -> "The Complete Eclipse C/C++ IDE"

3) install

4) restart Eclipse

