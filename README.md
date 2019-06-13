The European Joint Research Center seeks to identify field boundaries across the European Union and use crowd sourced data to determine agricultural data for these fields; "Ultimately, the resulting datasets should serve as  parcel-level ground-truth for Copernicus Sentinel-1 and-2 based EO products."

The essensce of the effort is to create both boundaries and seasonally accurate data about the plantings in those fields. It could be thought of as a combination of [OneSoil](https://onesoil.ai/en/) field boundary extraction combined with more accurate machine learning based extraction of crop typing.

OneSoil has created beautiful field boundary maps:

<img src=images/Biella_OneSoil.jpg>

But, their crop data is not always accurate. In this image, the crop map from OneSoil shows maize growing between the villages of Puligny-Montrachet and Chassagne-Montrachet. As my friend would say: "Interesting, if true.":

<center><img src=images/not_likely_true.jpg></center>

Other efforts such as [EuroSat](https://github.com/phelber/eurosat#) have created datasets for machine learning based on image chips, but not for labeled extraction of crop types. Running fastai's library against these training data and an rgb chipset of the area around Biella gave solid results for identifying the majority feature of each chip, but doesn't do much for identifying the fields themselves or the crops that are growing in them. 

How can these two methods be combined? One solution is to combine high resolution orthophotos with ground truth classified raster data. This example uses NAIP 1m imagery from the USDA and ground truth data from the Chesapeake Conservancy to create a set of raster mask image tiles that allow for the training of a deep learnign u-net model.

