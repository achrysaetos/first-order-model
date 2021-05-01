
## How it works:
Traditional deepfake technology requires many source videos in order to learn enough about a subject to map his or her characteristics onto the driving video. First order motion models, on the other hand, works by transferring key points from the driving video onto a single source image. The result is that first order motion models often take much less time to train, while still retaining high output credibility. However, the source image for a first order motion model must be similar to the first frame of the driving video; and with unlimited resources, deepfake technology will eventually surpass first order motion models in terms of output credibility.

## Running the demo:
Create virtual env: `python3 -m venv scrapy-env`\
**Activate virtual env:** `source scrapy-env/bin/activate`\
Install dependencies: `pip install -r requirements.txt`\
Download sources: (from link to google drive)\
Download ffmpeg with python: (if necessary; import imageio first)\
**Run demo:** `python demo.py  --config config/dataset_name.yaml --driving_video path/to/driving --source_image path/to/source --checkpoint path/to/checkpoint --relative --adapt_scale`\
*ie.* `python demo.py  --config config/vox-256.yaml --driving_video sources/00.mp4 --source_image sources/statue-04.png --checkpoint sources/vox-cpk.pth.tar --relative --adapt_scale --cpu`\

## Running with your own driving video and source image:
Activate virtual env: `source scrapy-env/bin/activate`\
**Get a source image:** (resize it to 256x256 and put it in the source folder)\
**Get a driver video:** (download from youtube or record one with your camera)\
Install face_alignment (if necessary): `git clone https://github.com/1adrianb/face-alignment`; `cd face-alignment`; `pip install -r requirements.txt`; `python setup.py install`\
**Get crop suggestions (takes around 15 minutes for a 10 second video):** `python crop-video.py --inp video_name.mp4 --cpu`\
Install ffmpeg (if necessary): `brew install ffmpeg`\
**Run ffmpeg suggestion:** `ffmpeg ...`\
**Run demo:** `python demo.py  --config config/vox-256.yaml.yaml --driving_video sources/driving_vid.mp4 --source_image sources/source_img.png --checkpoint sources/vox-cpk.pth.tar --relative --adapt_scale --cpu`\
