# Angel System ASR Server

## Running the Server

### Create conda environment

```
conda env create -f speech_server.yml
conda activate speech_server
sudo apt-get install ffmpeg
sudo apt-get install sox
```

The server can then be instantiated with:

```
export CUDA_VISIBLE_DEVICES=4; python speech_server.py
```

## Running the Client

### Create conda environment

```
conda env create -f speech_client.yml
conda activate speech_client
```

or

```
conda env create -n "speech_client" python=3.10.11 pip
conda activate speech_client
pip3 install -r requirements.txt
sudo apt install portaudio19-dev
pip3 install pyaudio 
```

Ensure the server is actively running on the server machine.
Also ensure the client is connected to a microphone peripheral.
This script will indicate when recording has begun. Otherwise, you can
optionally pass in a prerecorded file using the `-f/--file` flag.
```
python speech_client.py --asr/--vd
```
