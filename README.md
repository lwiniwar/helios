# helios

> Heidelberg LiDAR Operations Simulator (HELIOS)

HELIOS is a software package for interactive real-time simulation and visualization of terrestrial, mobile and airborne laser scanning surveys written in Java. Official website: https://www.uni-heidelberg.de/helios

[![HELIOS](http://img.youtube.com/vi/1SOg7b5q4ak/0.jpg)](https://www.youtube.com/watch?v=1SOg7b5q4ak "HELIOS")

## Table of Contents
- [Install](#install)
- [Usage](#usage)
- [Documentation](#documentation)
- [Authorship](#authorship)
- [License](#license)

## Install
The pre-built project is available [here](https://heibox.uni-heidelberg.de/f/06bb612921/?raw=1) with a test scene and survey. Note that for faster simulations **building the project is recommended**. 

To build the project, first install the dependencies, then compile the source code, and finally execute it.

### Requisites
- Oracle Java 1.8
- Maven 3

You can use ```java -version``` and ```mvn -v``` to check if you already have installed those on your computer.

#### Linux/Ubuntu:
They can be installed by:

```bash
sudo apt-get install oracle-java8-installer maven
```
#### Windows:
In Windows installation is less straightforward:  
- Java JDK  
	1. Download the [Java JDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) and install it  
	2. Create the environment variable *JAVA_HOME* to point to the JDK folder  
	(e .g: *JAVA_HOME=C:\Program Files\Java\jdk1.8.0_151*)  
	3. Add to the *PATH* the value *%JAVA_HOME%\bin*  
- Maven  
	1. Download the [Maven](https://maven.apache.org/download.cgi) *binary* zip  
	2. Unzip it and move it to the desired folder (e. g. *C:\apache-maven-3.5.2*)  
	3. Add to the *PATH* the bin folder inside (e. g. *C:\apache-maven-3.5.2\bin*)  

### Compilation

Download the source code from this web site or from git:

```bash
git clone https://github.com/GIScience/helios.git
```
Then inside the root folder simply execute:
```bash
mvn package
```

### Eclipse IDE

To add this project to Eclipse go to *File > Import > Existing Maven Projects* and select *helios* folder.  
You may also want to disable the spell checker: right click in the project > *Checkstyle > Deactivate Checkstyle*

## Usage

HELIOS supports both single-ray and full-waveform simulations. Currently the default mode is the full-waveform. The selection between this two methods is done in the source code when creating the detector object in [*XmlAssetsLoader.java*](src/main/java/de/uni_hd/giscience/helios/assetsloading/XmlAssetsLoader.java). 

### Input

The argument of the program is the survey XML file, also the 3D models of the scene pointed in the survey are needed. See [Wiki: Basic input data](https://github.com/GIScience/helios/wiki/Quick-start-guide#basic-input-data) for further details. 

### Execution

From the root folder run:

```bash
java -jar target/helios.jar <survey-file>
```
To run the example survey:

```bash
java -jar target/helios.jar data/surveys/demo/tls_arbaro_demo.xml 
```

To use the batch mode (no visualization):

```bash
java -jar target/helios.jar <survey-file> headless
```
### Output

Output files are generated inside *output/Survey Playback* folder.

* Point cloud: File named *legxxx_points.xyz* separated by spaces  where *xxx* is the leg number.  
Fields:  
X Y Z I ECHO_WIDTH RN NOR FWF_ID OBJ_ID  
Example:   
-4.615 15.979 2.179 4.0393 1.4317 1 1 214275 1
* Waveform: File named *legxxx_points.xyzfullwave.txt* separated by spaces  where *xxx* is the leg number.  
See [FWF.md](FWF.md) for further details. 

## Documentation

See [Wiki](https://github.com/GIScience/helios/wiki).

## HELIOS in the Literature

Liu, J., Skidmore, A.K., Wang, T., Zhu, X., Premier, J., Heurich, M., Beudert, B. &amp; Jones, S. (2019): Variation of leaf angle distribution quantified by terrestrial LiDAR in natural European beech forest</a>. In: ISPRS Journal of Photogrammetry and Remote Sensing, 148, pp. 208-220. DOI: [10.1016/j.isprsjprs.2019.01.005](https://doi.org/10.1016/j.isprsjprs.2019.01.005).

Hämmerle, M., Lukač, N., Chen, K.-C., Koma, Zs., Wang, C.-K., Anders, K., &amp; Höfle, B. (2017): Simulating Various Terrestrial and UAV LiDAR Scanning Configurations for Understory Forest Structure Modelling. In: ISPRS Ann. Photogramm. Remote Sens. Spatial Inf. Sci., IV-2/W4, pp. 59-65. DOI: [10.5194/isprs-annals-IV-2-W4-59-2017](https://doi.org/10.5194/isprs-annals-IV-2-W4-59-2017).

Rebolj, D., Pučko, Z., Babič, N.Č., Bizjak, M. & Mongus, D. (2017). Point cloud quality requirements for Scan-vs-BIM based automated construction progress monitoring</a>. In: Automation in Construction, 84, pp. 323-334. DOI: [10.1016/j.autcon.2017.09.021](https://doi.org/10.1016/j.autcon.2017.09.021).

Bechtold, S., Hämmerle, M. &amp; Höfle, B. (2016): [Simulated full-waveform laser scanning of outcrops for development of point cloud analysis algorithms and survey planning: An application for the HELIOS lidar simulation framework](http://lvisa.geog.uni-heidelberg.de/papers/2016/Bechtold_et_al_2016.pdf). In: Proceedings of the 2nd Virtual Geoscience Conference, Bergen, Norway, 21-23 September 2016, pp 57-58.

Bechtold, S. &amp; Höfle, B. (2016): HELIOS: A Multi-purpose LiDAR Simulation Framework for Research, Planning and Training of Laser Scanning Operations With Airborne, Ground-based Mobile and Stationary Platforms. In: ISPRS Ann. Photogramm. Remote Sens. Spatial Inf. Sci., III-3, pp. 161-168. DOI: [10.5194/isprs-annals-III-3-161-2016](http://dx.doi.org/10.5194/isprs-annals-III-3-161-2016).


## Authorship

GIScience Research Group  
Institute of Geography  
University of Heidelberg  

### Citation

Bechtold, S. & Höfle, B. (2016): HELIOS: A Multi-Purpose LiDAR Simulation Framework for Research, Planning and Training of Laser Scanning Operations with Airborne, Ground-Based Mobile and Stationary Platforms. ISPRS Annals of Photogrammetry, Remote Sensing and Spatial Information Sciences. Vol. III-3, pp. 161-168. DOI: [10.5194/isprs-annals-III-3-161-2016](http://dx.doi.org/10.5194/isprs-annals-III-3-161-2016)

### Maintainers

[@sebastian-bechtold](https://github.com/sebastian-bechtold) [@nlukac](https://github.com/nlukac) [@kathapand](https://github.com/kathapand) [@deuxbot](https://github.com/deuxbot) 

The first HELIOS version with full-waveform support is available in [this](https://github.com/nlukac/helios-FWF) repository maintained by [@nlukac](https://github.com/nlukac).

## License

See [LICENSE.md](LICENSE.md).
