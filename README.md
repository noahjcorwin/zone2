# zone2

lazy api for starting mplayer on raspberry pi driving zone 2 on an audio receiver

## requirements
python
```
pip install flask flask_restful psutil
```
mplayer
```
apt-get install mplayer
```
## stations
extract from radio webpage and adding streaming url to stations.py. mplayer doesnt like https, so make sure to use http.
```
callsigns = {
'stop': 'mplayer',
'live105': 'http://playerservices.streamtheworld.com/api/livestream-redirect/KITSFM_TLRAAC.aac',
'krty953': 'http://live.wostreaming.net/direct/empirebroadcasting-krtyfmaac-ibc1'
}

```
## usage
to start a stream, specify key name in url `http://127.0.0.1/zone2/<key>`
```
curl http://127.0.0.1/zone2/live105
{"live105": "http://playerservices.streamtheworld.com/api/livestream-redirect/KITSFM_TLRAAC.aac"}
```
to stop the stream, specify `stop` for the key name.
```
curl http://127.0.0.1/zone2/stop
{"stop": "mplayer"}
```

## license
[MIT](https://choosealicense.com/licenses/mit/)
