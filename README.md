# locating_ISS
import pandas as pd
import plotly.express as px
url="http://api.open-notify.org/iss-now.json" #Json file's address
df= pd.read_json #setting pandas data frame to read the Json file
df["latitude"]=df.loc["latitude","iss_position"] 
df["longitude"]=df.loc["longitude","iss_position"]
df.reset_index(inplace=True)
fig=px.scatter_geo(df, lat="latitude", lon="longitude")
fig.show()
