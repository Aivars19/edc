# StraGla

[Download StraGla.apk 3.3MB 2026-05-02](https://github.com/Aivars19/StraGla/releases/download/v0.0.1beta/StraGla-0.0.1beta-release.apk)

StraGla is a free and open-source Android application for **streaming and saving** your device screen and audio. 
It is derived from the excelent original [ScreenStream](https://play.google.com/store/apps/details?id=info.dvkr.screenstream) application, but with major re-focus. 

What StraGla does:
- stream to rtsp/rtsps endpoint (such as mediamtx server)
- save local file (mp4) with the same encoding as the stream
- tolerate network outage - saving is not affected, streaming resumed when the network is back

## rtsp / rtsps streaming endpoints
You must have an rtsp/rtsps server to stream to. 
Default addresses will look like this:
- rtsp://server1:8554/stream_name1
  - server1 - either dns name, or IP, or LAN name that maps to IP
  - 8554 - default rtsp port, but depends on your server configuration
  - stream_name1 - usually anything you want; some scenarios (youtube live) requires "secret key"
- rtsps://server2:8322/stream_name2
  - this is encrypted version of rtsp, so it requires TLS/SSL certificate on the server side; 
  - server2 - normally this is DNS (public signed TLS).   
## streaming resolution, framrate, bitrate 
Network speed is critically important. Usually you will compromise for size and quality.

Approximate streaming quality guide, for h.264 codec, no audio:

| Mbps | 1080p30 | 1080p16 | 720p30 | 720p16 | 540p30 | 540p16 |
|------|---------|---------|--------|--------|--------|--------|
| 0.8 | 🟥 Unusable | 🟥 Unusable | 🟥 Unusable | 🟨 Passable | 🟨 Passable | 🟩 Good |
| 1.2 | 🟥 Unusable | 🟥 Unusable | 🟨 Passable | 🟩 Good | 🟩 Good | 🟦 Perfect |
| 1.6 | 🟥 Unusable | 🟨 Passable | 🟨 Passable | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect |
| 2.0 | 🟥 Unusable | 🟩 Good | 🟩 Good | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect |
| 3.0 | 🟨 Passable | 🟩 Good | 🟩 Good | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect |
| 4.0 | 🟩 Good | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect |
| 5.0 | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect | 🟦 Perfect |
