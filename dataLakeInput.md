Input for data for data lake:

import deeplake 
api_key = os.getenv("<deeplake_api>")

# create an empty "data store" on deeplake. overwrite=True so I could keep reusing it
ds = deeplake.empty('hub://<your organization from deeplake>/<whatever you want to call it>', token=api_key, overwrite=True)

# create tensors mimicking the output sample from github.py
ds.create_tensor("ids")
ds.create_tensor("metadata")
ds.create_tensor("embedding")
ds.create_tensor("text", htype="text")
