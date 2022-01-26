# RTSPtoHTTP-Streaming

# 설치 방법 (How to install VLC)
- Windows
   > VLC 설치 후, 환경 변수 설정

- Linux (Ubuntu)
   > sudo apt-get install vlc 

- Linux (Amazon Linux 2, Red Hat)
   > sudo yum install libwayland-client

   > wget http://mirror.centos.org/centos/7/os/x86_64/Packages/libva-1.8.3-1.el7.x86_64.rpm

   > sudo rpm -i libva-1.8.3-1.el7.x86_64.rpm

   > sudo yum install vlc





# 사용 방법 (How to streaming RTSP to HTTP)
- Windows
   > vlc "{Source RTSP URL}" :sout=#transcode{vcodec=theo,vb=800,acodec=vorb,ab=128,channels=2,samplerate=44100,scodec=none}:http{mux=ogg,dst=:{access port}/{Sub URL}} :no-sout-all :sout-keep

- Example for Windows 
   > vlc "rtsp://wowzaec2demo.streamlock.net/vod/mp4:BigBuckBunny_115k.mov" :sout=#transcode{vcodec=theo,vb=800,acodec=vorb,ab=128,channels=2,samplerate=44100,scodec=none}:http{mux=ogg,dst=:8181/test} :no-sout-all :sout-keep


- Linux (Ubuntu)
   > vlc -vvv "{Source RTSP URL}" --sout "#transcode{vcodec=theo,vb=800,acodec=vorb,ab=128,channels=2,samplerate=44100,scodec=none,fps=30}:http{mux=ogg,dst=:{access port}/{Sub URL}}" --no-sout-all --sout-keep

- Example for Linux (Ubuntu)
   > vlc -vvv "rtsp://wowzaec2demo.streamlock.net/vod/mp4:BigBuckBunny_115k.mov" --sout "#transcode{vcodec=theo,vb=800,acodec=vorb,ab=128,channels=2,samplerate=44100,scodec=none,fps=30}:http{mux=ogg,dst=:8181/test}" --no-sout-all --sout-keep


- Linux (Amazon Linux 2, Red Hat)
   > cvlc -vvv "{Source RTSP URL}" --sout "#transcode{vcodec=theo,vb=800,acodec=vorb,ab=128,channels=2,samplerate=44100,scodec=none,fps=30}:http{mux=ogg,dst=:{access port}/{Sub URL}}" --no-sout-all --sout-keep --no-one-instance

- Example for Linux (Amazon Linux 2, Red Hat)
   > cvlc -vvv "rtsp://wowzaec2demo.streamlock.net/vod/mp4:BigBuckBunny_115k.mov" --sout "#transcode{vcodec=theo,vb=800,acodec=vorb,ab=128,channels=2,samplerate=44100,scodec=none,fps=30}:http{mux=ogg,dst=:8181/test}" --no-sout-all --sout-keep --no-one-instance
