# Repository for `Satellite Trees Wroclaw 2022/2024`

## Description

This repository contains the code for the project `Satellite Trees Wroclaw 2022/2024`. The project aims to create a dataset of trees details in Wroclaw based. The project is part of the spatial data course at the WUST.

## Examples

| Example 1                                         | Example 2                                         | Example 3                                         |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| ![ex1](/repo_assets/result_tile_143378_87589.jpg) | ![ex2](/repo_assets/result_tile_143473_87654.jpg) | ![ex3](/repo_assets/result_tile_143478_87625.jpg) |

## Download Dataset

Dataset is publicly available on [Satellite Trees Wroclaw 2022](https://huggingface.co/datasets/Filipstrozik/satellite_trees_wroclaw_2022)
and [Satellite Trees Wroclaw 2024](https://huggingface.co/datasets/Filipstrozik/satellite_trees_wroclaw_2024)

## Data

Satellite images come from [System Informacji Przestrzenej Wrocławia](https://geoportal.wroclaw.pl/mapy/ortofoto/). The data is publicly available and there are no restrictions on its use.

Trees data comes from [Mapa Koron Drzew](https://aplikacja.mapadrzew.com/). The data is available by making an api request to the server of application using `inGeometry` endpoint and providing corners of the area of interest. We believe that is legal to use this data, because no restrictions are mentioned on the website. Until 1000 trees where selected it is free of charge. Trees that has hight more then 4m and area of the crown more then 9m^2 are selected.

## Pipeline

Inside `scrape.ipynb` notebook, there is a pipeline that allows to gather satellite images and trees data for a given area.
We utilized a maximum zoom level of 18 for the tiles to ensure that the number of trees in the area of interest remained below 1000.

## Limitations

1. To keep our dataset small but precise we chose resolution for satellite image to 1024px x 1024px and the area of interest to 96m x 96m. This allows us to have a good resolution of the trees and the satellite image.

1. Also scanned only a part of the city with following coordinates:

- tile (x, y, z) = (lat, long, z)
- Starting tile (143379, 87582, 18) = (51.153502274010194, 16.90120694577385, 18)
- Finish tile (143541, 87686, 18) = (51.06355157265516, 17.12361013706642, 18)

Visualisation of the area of interest:

![Area of interest](/repo_assets/dataset_area.png)

## Authors

- Filip Strózik
- Dawid Wolkiewicz
- Izabela Majchorwska
