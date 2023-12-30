<h2> Contents </h2>     

- [File Structure](#file-structure)
- [Detailed Information of the Files](#detailed-information-of-the-files)
- [How to Run the Code](#how-to-run-the-code)
- [Visualization System](#visualization-system)


## File Structure

```python
Visualization-Final-Project
├──js                   # static .js files
    ├──d3.v5.min.js         # d3.js version 5
    ├──d3.v6.js             # d3.js version 6
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
    ├──Problem1.py          # python code for problem 1, following are the same
    ├──Problem2.py          # ...
    ├──Problem3.py          # ...
    ├──Problem4.py          # ...
    ├──main.py              # process data from problem 1 to 4
    └──utils.py             # contains all auxiliary functions
└──templates            
    ├──main.html            # visualization system
    ├──relationship.html    # the relationship visualization sub-page
    ├──geo.json             # map data of chongqing in geojson format     
    └──weighted_graph.json  # relationship between people 
```

## Detailed Information of the Files
- output_csv
  - area.csv/ID_NAME_convert.csv
    - The data of ```area.csv``` is downloaded from [here](https://pan.baidu.com/link/zhihu/7VhWzVuMhUiVb0UG9GdR9tRjSWTxpkawd4Rn==).
    - A converter between area-id and area-name is generated by finding the first nonempty column(year) in each row.
  - adult.csv/minor.csv/bar.csv
    - These csv files store the answer for Problem 1.
    - The columns of the adult and minor are ```[id, name, times]```, with the meaning of ```personal-id, name, illegal-times``` respectively.
    - The columns of the bar also include ```[adult, minor, lng, lat]```, which stand for ```adult-illegal-times, minor-illegal-times, longitude, latitude```.
  - float.csv
    - Contains ```[area, hour, duration, age, xb]```
  - all_info.csv
    - Contains ```[siteid, xb, duration, area, age, hour]```
- pycode
  - Refer to the comment in section [file structure](#file-structure).
- templates
  - main.html
    - Contains five separate divs: map, board, time, age, people. They are used for displaying map, leaderboard, curve line, bar plot and pie respectively.
  - relationship.html
    - Contains one div, displaying the relationship between people.
  - geo.json
    - The data of Chongqing's map in GeoJSON format. Downloaded from [here](https://geojson.cn/api/data/500000.json).
  - weighted_graph.json
    - Relationship between people with weight information. Generated by the sliding window method.
## How to Run the Code
- Step 1
  - Open ```Visualization_FinalProject``` and set it as the working directory.
- Step 2 **(optional)**
  - Directly run ```main.py``` in ```pycode```.
  - Or you can input ```python ./pycode/main.py``` in terminal.
  - The output in terminal should be like this: ![Output](https://github.com/Dasher-mango/Visualization-Final-Project/blob/main/img/output.png)
  > _Note_: 
  > - The original data are not included here, so you need to create a **data** file in the directory and save the swjl and wb data in this file. The original data can be downloaded from the following two links: [Challenge 2.1](http://chinavis.org/2017/challenge2017/2017年数据可视分析挑战赛-挑战2_1-数据.zip), [Challenge 2.2](http://chinavis.org/2017/challenge2017/2017年数据可视分析挑战赛-挑战2_2-数据.zip).
  > - The cleaning and process of the swjl and wb data may take several minutes, you can refer to the output in terminal for the information of execution. 
  > - Since the processed information is already contained in file ```output_csv```, you're free to jump to Step 3.
- Step 3
  - Open ```main.html``` in ```templates```.
  - Right click and choose <ins>Open with Live Server</ins>.   
  > _Note_: 
  > - There are about $15\text{M}$ rows of data(if you use the full data set), so the initialization of the visulation system may take more than 30s. Some patience is needed here. 
  > - For the purpose of presentation, I have selectively utilized four csv files as the foundational dataset.
  > - The expansion [Live Server](https://github.com/ritwickdey/vscode-live-server-plus-plus) is required here.

## Visualization System
- Snap shot on full data set
  ![Full](https://github.com/Dasher-mango/Visualization-Final-Project/blob/main/img/full.png)
  ![Community](https://github.com/Dasher-mango/Visualization-Final-Project/blob/main/img/community.png)
- Demo video
  - Venice
  - https://www.youtube.com/watch?v=gqmpDG4ewzc
  - ![](https://github.com/Dasher-mango/Visualization-Final-Project/blob/main/img/Venice_2.mp4)
