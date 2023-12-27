<h2> Contents </h2>     

- [File Structure](#file-structure)
- [Detailed Information of the Files](#detailed-information-of-the-files)
- [How to Run the Code](#how-to-run-the-code)


## File Structure

```python
Visualization_FinalProject
├──js                   # static .js files
    ├──d3.v5.min.js         # d3.js version 5
    └──topojson.js          # topojson for drawing map
├──output_csv           # csvs containing the information of given data
    ├──area.csv             # historical information of areaid in China
    ├──ID_NAME_convert.csv  # converter between the areaid and areaname
    ├──adult.csv            # information of the illegal adults
    ├──minor.csv            # information of the illegal minors
    ├──bar.csv              # information of the illegal bars
    ├──float.csv            # information of the migrant population
    └──all_info.csv         # information of bars' profile
├──pycode               # all the python codes for processing the data
    ├──__init__.py  
    ├──Problem1.py          # py code for problem 1, following are the same
    ├──Problem2.py          # ...
    ├──Problem3.py          # ...
    ├──Problem4.py          # ...
    ├──main.py              # process data for problem 1 to 4
    └──utils.py             # contains all auxiliary functions
└──templates            
    ├──main.html            # visualization system
    └──geo.json             # map data of chongqing in json format      
```

## Detailed Information of the Files
- output_csv
- pycode
- templates

## How to Run the Code
- Step 1
  - Open ```Visualization_FinalProject``` and set it as the working directory.
- Step 2 **(optional)**
  - Directly run ```main.py``` in ```pycode```.
  - Or you can input ```python ./pycode/main.py``` in terminal.
  > _Note_: 
  > - The original data are not included here, so you need to create a **data** file in the directory and save the swjl and wb data in this file. 
  > - The cleaning and process of the swjl and wb data may take several minutes, you can refer to the printed strings in terminal for the information of execution.
  > - Since the processed information is already contained in file ```output_csv```, you're free to jump to Step 3.
- Step 3
  - Open ```main.html``` in ```templates```.
  - Right click and choose <u>Open with Live Server</u>.   
  > _Note_: 
  > - There are about $15\mathbf{M}$ rows of data, so the initialization of the visulation system may take more than 30s. Some patience is needed here. 
  > - The expansion [Live Server](https://github.com/ritwickdey/vscode-live-server-plus-plus) is required here.
