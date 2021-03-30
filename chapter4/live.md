# Sonic Pi与Ableton Live通讯

之前我曾经尝试用midibus的方式，让sonic pi发送midi信号给Ableton Live。

作为PC用户，我使用了loopMIDI创建虚拟MIDI端口。

苹果用户实现过程应该比PC更方便。



创建流程请参见视频教程：

https://www.bilibili.com/video/BV1t7411K7JM/



## 完整程序

```ruby
live_loop :notes do ; tick
    midi(ring :c4,:eb4,:f4,:g4).look,port: :kittyPord, channel: 1
    midi_cc 0,(line 50,100, steps: 40).look, port: :kittyPort, channel: 1
    sleep 0.25
end
```

