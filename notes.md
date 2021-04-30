Create virtual env: `python3 -m venv scrapy-env`\
Activate virtual env: `source scrapy-env/bin/activate`\
Install dependencies: `pip install -r requirements.txt`\
Download sources: (from link to google drive)\
Download ffmpeg with python: (if necessary; import imageio first)\
Run demo: `python demo.py  --config config/dataset_name.yaml --driving_video path/to/driving --source_image path/to/source --checkpoint path/to/checkpoint --relative --adapt_scale`\
ie. `python demo.py  --config config/vox-256.yaml --driving_video sources/00.mp4 --source_image sources/statue-04.png --checkpoint sources/vox-cpk.pth.tar --relative --adapt_scale --cpu`\