# offline-tangram.js

Notes on setting up a small localized demo of tangram.js.  To go fully offline, you'll need to download and locally access the leaflet resources, as well.


## To run locally

Download this repo, then start a web server in its directory:
```
python -m SimpleHTTPServer 8000
```

If that doesn't work, try:
```
python -m http.server 8000
```

Then navigate to: http://localhost:8000



## To fetch a subset of tiles using [tilepacks](https://github.com/tilezen/tilepacks)

Clone tilepacks
```
git clone https://github.com/tilezen/tilepacks.git
cd tilepacks
```

Set up virtualenv (requires python3 and [virtualenv](https://packaging.python.org/guides/installing-using-pip-and-virtualenv/))
```
python3 -m virtualenv env
source env/bin/activate
pip install -e .
```

Tilepack example: fetch tiles for San Francisco
```
MAPZEN_API_KEY=mapzen-6VCZ2xH tilepack -122.51489 37.70808 -122.35698 37.83239 10 15 sf_mvt_10_15 --tile-size 512
```

Tilepack example: fetch tiles for New York
```
MAPZEN_API_KEY=mapzen-6VCZ2xH tilepack -74.13574 40.614995 -73.84289 40.81693 10 15 ny_mvt_10_15 --tile-size 512
```
