# Collect and Analyze Twitter Followers

Companion code for:
Alperin, J.P., Gomez, C.J. & Haustein, S. (2018). Identifying diffusion patterns of research articles on Twitter: A case study of online engagement with open access articles. *Public Understanding of Science*.

Given a list of tweets, collect the follower/followee networks and produce some network statistics and visualizations. 

To run, you should do the following: 

```
# Make a new config file from the template. 
# Edit the resulting file and fill in the account credentials
cp config.TEMPLATE.cnf config.cnf


# load the data file to the sqlite DB
python3 collect.py --input-file=data/bmcTwitter.tsv

# fetch the tweet info in batch + collect missing tweets individually to get errors
python3 collect.py --batch --individual

# then get the friends and follower networks
python3 collect.py --friends --followers

# Now crunch the stats
python3 make_graphs.py
```

