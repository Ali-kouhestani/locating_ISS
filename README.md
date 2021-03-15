# locating_ISS
import pandas as pd
import plotly.express as px
url="http://api.open-notify.org/iss-now.json" #Json file's address
df= pd.read_json #reading the Json file
df["latitude"]=df.loc["latitude","iss_position"] #setting the data frame latitude and longitude to ISS location
df["longitude"]=df.loc["longitude","iss_position"]
df.reset_index(inplace=True)
fig=px.scatter_geo(df, lat="latitude", lon="longitude")
fig.show()
