```c++
#include <bits/stdc++.h>
using namespace std;
class MediaPlayer {
public:
    virtual void play(string audioType, string fileName) = 0;
};

class AdvancedMediaPlayer {
public:
    virtual void playVlc(string fileName) = 0;
    virtual void playMp4(string fileName) = 0;
};

class VlcPlayer : public AdvancedMediaPlayer {
public:
    void playVlc(string fileName) {
        cout << "Playing vlc file name: " << fileName << endl;
    }
    void playMp4(string fileName) {
        // cout << "Playing mp4 file name: " << fileName << endl;
    }
};

class Mp4Player : public AdvancedMediaPlayer {
public:
    void playVlc(string fileName) {
        // cout << "Playing vlc file name: " << fileName << endl;
    }
    void playMp4(string fileName) {
        cout << "Playing mp4 file name: " << fileName << endl;
    }
};

class MediaAdapter : public MediaPlayer {
private:
    AdvancedMediaPlayer *advancedMusicPlayer;
public:
    MediaAdapter(string audioType) {
        if(audioType == "vlc") {
            advancedMusicPlayer = new VlcPlayer();
        }
        else if(audioType == "mp4") {
            advancedMusicPlayer = new Mp4Player();
        }
    }
    void play(string audioType, string fileName) {
        if(audioType == "vlc") {
            advancedMusicPlayer->playVlc(fileName);
        }
        else if(audioType == "mp4") {
            advancedMusicPlayer->playMp4(fileName);
        }
    }
};

class AudioPlayer : public MediaPlayer {
private:
    MediaAdapter *mediaAdapter;
public:
    void play(string audioType, string fileName) {
        if(audioType == "mp3") {
            cout << "Playing mp3 file name: " << fileName << endl;
        }
        else if(audioType == "vlc" || audioType == "mp4") {
            mediaAdapter = new MediaAdapter(audioType);
            mediaAdapter->play(audioType, fileName);
        }
        else {
            cout << "Invalid media !!!!!!!!!!" << endl;
        }
    }
};

int main() {
    AudioPlayer *audioPlayer = new AudioPlayer();
    audioPlayer->play("mp3", "beyond the horizon.mp3");
    audioPlayer->play("mp4", "alone.mp4");
    audioPlayer->play("vlc", "far far away.vlc");
    audioPlayer->play("avi", "mind me.avi");
    return 0;
}
```
