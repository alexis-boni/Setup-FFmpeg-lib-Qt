# Intro
How to setup ffmpeg lib for windows (and use them in Qt)

# Setup
Download a MinGW terminal \
Download FFmpeg from github

# Compile and build
Open a MinGW terminal \
cd into the FFmpeg folder
type:
```
./configure --prefix=ffmpeg/ --disable-network --disable-debug --disable-yasm --disable-zlib
make -j12
make install -j12
```

# Qt link
In Qt in the pro file (replace <DOWNLOADED_DIR> with your path):
```
LIBS += -L<DOWNLOADED_DIR>/ffmpeg/lib/ -lavformat -lavdevice -lavfilter -lavcodec -lavutil -lswresample -lswscale

INCLUDEPATH += <DOWNLOADED_DIR>/FFmpeg-master/ffmpeg/include
DEPENDPATH += <DOWNLOADED_DIR>/FFmpeg-master/ffmpeg/include

unix|win32: LIBS += -ldxva2 -lMf -lMfplat -lmfuuid -levr -lbcrypt -lstrmiids -lkernel32 -liconv -lquartz -lShLwApi -lGdi32 -lVfw32 -lOle32 -lOleAut32 -lUuid #-lmfplay -lmfreadwrite
```

# Thanks
https://ffmpeg.org \
https://www.youtube.com/watch?v=3yhkX0uaQGk \
https://docs.microsoft.com \
