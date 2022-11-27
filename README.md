# An Analysis to Decide on a Mobile Carrier for Business Phones

## Motivation
Company X is a manufacturing company in Hamilton, ON, Canada. The management plans to provide mobile phones for their employees and they need to decide on a Mobile Network Operator (MNO) to contract for the cell service on these mobile phones. In this project, we analyze the infrastructure of the MNOs in Canada to help the management make an informed decision.

This project will answer the following questions to help them choose an MNO:
1. The sales representatives of Company X travel across Canada for client meetings and Company X wants to provide them with cell service with the widest coverage across Canada, so they ask: Which MNO has the widest coverage across Canada in terms of the number of ISED Service Areas covered?
2. Company X wants the engineers to be reachable by their work phones during the weekends in case of emergencies. The engineers are known to travel around Southern Ontario on weekends, so the management wants to choose the MNO with the most reliable coverage in Southern Ontario region and they ask: Which MNO has the widest bandwidth per person (in MHz/people based on 2016 census) at Southern Ontario?
3. Management is also concerned about the privacy concerns raised in media about Huawei branded cell tower equipment. They want to know: What the proportion of each MNO's hardware is Huawei branded?

## Results
Our results show that TELUS has the widest coverage across Canada and the 4th widest bandwidth per person in Southern Ontario, but 93% percent of their hardware is Huawei branded. Rogers has the 2nd widest bandwidth per person and the 3rd widest coverage across Canada. 24% of their hardware is made by Huawei. Bell has the widest bandwidth per person and the 2nd widest coverage across Canada. 39% of their hardware is made by Huawei.

Between Rogers and Bell, our recommendation would depend on the relative importance of these 3 factors. If Company X prioritizes choosing an MNO which has the smallest percentage of Huawei branded hardware among the ones with the widest coverage, we would recommend Rogers. However, if the coverage across Canada and the reliability in Southern Ontario is more important, we would recommend Bell.

The steps of analysis taken for this project are described in detail in the Jupyter notebook named project.ipynb. This analysis and its conclusions are also summarized in [my blog post](https://cacarer.com/choosing-a-mobile-carrier-for-business-phones/).

## Files Used
The file size of one of the data files used in this project exceeds the GitHub's file size limit of 100MBs; therefore, they are shipped in the zip file named `datasets.zip` in this repository and extracted by the code. The contents of these files are described below, the sources of these files are linked in the Jupyter notebook.
- `datasets/spectrum-licenses.csv`: This file is the main dataset used in the analysis. It contains the records of the coordinates of every licensed broadcasting hardware operated in Canada, the MNO who is providing mobile service with it, and the brand of the hardware. 
- `datasets/ised-service-areas.xlsx`: This file contains the service area names defined by ISED (Innovation, Science and Economic Development Canada) and the populations of these areas. 
- `datasets/ised-maps/tel-2019.KML`, `datasets/ised-maps/tier1.KML`, `datasets/ised-maps/tier2-1-14.KML`, `datasets/ised-maps/tier2-17-18.KML`, `datasets/ised-maps/tier3.KML`, `datasets/ised-maps/tier4.KML`, `datasets/ised-maps/tier5.KML`: These map files contain the polygons which shows the boundaries of the service areas at different tiers.
## Dependencies
- Pandas: Used to read and manipulate datasets.
- Numpy: Used for array operations.
- Zipfile: Used to unzip the `datasets.zip`.
- BeautifulSoup: Used to parse the polygon names from html strings.
- Geopandas: Used to read the map files.
- Shapely: Used to perform Point in Polygon checks which allowed us to find which coordinates match with which shapes.
- Matplotlib: Used for creating plots.

Installing GeoPandas can be a little tricky; if you have any issues related to dependencies, please see [this page](https://cacarer.com/tip/installing-geopandas-with-its-dependencies-without-installing-microsoft-visual-c/) for further instructions. The other packages imported in the notebook can be installed with `pip install packageName`, assuming your path variables are set correctly.

## Note
All code and analysis on this GitHub repository and the related blog post on cacarer.com are an original work of Cansin Cagan Acarer independently done using publicly available data from on the website of Innovation, Science And Economic Development Canada (ISED). The findings and opinions expressed in the scope of this project on this GitHub repository and the related blog post on cacarer.com solely belong to Cansin Cagan Acarer; they neither represent the opinion of nor are done in cooperation with any corporation.
