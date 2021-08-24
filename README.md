# 3D House Modelling



[![LinkedIn][linkedin-shield]](https://www.linkedin.com/in/samuel-dodet/)


![Logo](https://github.com/SamuelDodet/Belgium_3DHouses/blob/main/static/example.png)
<!-- PROJECT LOGO -->
<br />
<p align="center">
    

  <h3 align="center">3D House Modelling </h3>

  <p align="center">
    Project done during BeCode Bootcamp.
    <br />
    <a href="https://becode.org/learn/ai-bootcamp/"><strong> BeCode BootCamp </strong></a>
    <br />
    <br />

  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Conclusion</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project


### Mission objectives
- to be able to search and implement new libraries
- to be able to read and use the shapefile format
- to be able to read and use geoTIFFs
- to be able to render a 3D plot
- to be able to present a final product

### Built With

To achieve this challenge, here are the main framework use in it:

* [Pandas](https://pandas.pydata.org/)
* [rasterio](https://rasterio.readthedocs.io/en/latest/index.html)
* [fiona](https://pypi.org/project/Fiona/)
* [geopandas](https://geopandas.org/)
* [Shapely](https://shapely.readthedocs.io/en/stable/index.html)
* [plotly](https://plotly.com/)
* [Flask](https://flask.palletsprojects.com/en/2.0.x/)





<!-- GETTING STARTED -->
## Getting Started



### Installation


1. Clone the repo
   ```sh
   git clone git@github.com:SamuelDodet/Belgium_3DHouses.git
   ```
2. Install required packages
   ```sh
   pip install requirement.txt
   ```
   or
   ```sh
   pip3 install requirement.txt
   ```
3.Download Data

- [Digital Terrain Model (DTM)](http://geoportail.wallonie.be/catalogue/6029e738-f828-438b-b10a-85e67f77af92.html)
- [Digital Surface Model (DSM)](https://geoportail.wallonie.be/catalogue/7d23d8ab-962a-493f-8771-2054e06ad36f.html)
- [Bâtiments 3D 2013-2014]((https://geoportail.wallonie.be/catalogue/4de94d5d-9036-4953-beca-3ff76e4b1ec8.html))
DSM, DTM and Canopy height model (CHM) are three important terms in this project!:
<img align="center" src="https://i.stack.imgur.com/1l3EA.png" />
  
4. Add your MapBoX KEY in function.py --> search_mapbox_key()

<!-- USAGE EXAMPLES -->
## Usage

#### 3D Map creation:
* Start with an address that we want to work from, and the area we want to plot around (let's take boundary=200m!)
* search_address_mapbox(): will call mapbox's API to return the coordinates of the adress: (X, Y). it will add the boundary around that point to obtain a bounding box that we will plot (xMin, xMax, yMin, yMax)* delete row with outlier value (1€/house, unnatural area, ...)
* find_files(): it will loop through each MNS/MNT file to check if the bounding box fits within.
* create_chm(): it will first crop the MNS and MNT Tiff files to the correct size, and create the CHM by substracting them.
* create_plotly_map(): will create the map based on the CHM and save it to HTML in order to use it in Flask


#### Flask:

run app.py --> start Flask environment

Put any addresses from provinces previously downloaded in order to visualize 3D Map
![Logo](https://github.com/SamuelDodet/Belgium_3DHouses/blob/main/static/logo.png)
You can now visualize the address with the boundary
![Logo](https://github.com/SamuelDodet/Belgium_3DHouses/blob/main/static/example2.png)
Click on any red contour from any house to have all information about it (Area, Height, ...)



<!-- ROADMAP -->
## Conclusion

Great application to visualize with 3D any area in Belgium with information of building in this area.



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

### Team Members
Samuel Dodet - [@Linkedin](https://www.linkedin.com/in/samuel-dodet/) - samuel.dodet3@gmail.com


Project Link: [https://github.com/SamuelDodet/Belgium_3DHouses](https://github.com/SamuelDodet/Belgium_3DHouses)

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555


