# all-is-one
user interface for AI image generation

Installation:
- cd all-is-one/server
    - for now, server/ is the working folder (sorry)
- conda env create -n ai1 --file environment.yaml
- conda activate ai1
- get token from https://huggingface.co/settings/tokens
- create .env file in the server/ folder with "HF_TOKEN=[your_token]"
- ~~python setup.py (no longer needed, go to Select Model in the UI to download/configure models)
    - this downloads the base model. instead, you can convert your own model with
    - python scripts/sd_to_diffusers.py --checkpoint_path [path to your model, i.e. models/model.ckpt] --original_config_file models/v1-inference.yaml --scheduler_type ddim --dump_path cache/[converted_model_name]
    - then in opts.py, change "model_cache_path='cache/sd'" to "model_cache_path='cache/[converted_model_name]',"
    - https://rentry.org/sdmodels has some better models to start with. Download one then convert it.~~
- python server.py
    - leave this running in the background
- go to http://localhost:5050/
    - Done!
    - The first run will take you to the "Select Model" tab, where you can download models from HuggingFace or convert .ckpt files