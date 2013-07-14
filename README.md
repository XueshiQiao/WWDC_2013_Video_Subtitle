WWDC 2013 视频字幕（英文，共100个）
========================


###1. How I get them? 

这要从下面1和2两个gist说起。。。

1. [extract.py][1] (fork from [Nicholas Riley](https://gist.github.com/nriley)'s [extract.py](https://gist.github.com/nriley/5874460))  用来获取视频的`fileSequence*.webvtt`文件，该文件是web格式的英文字幕文件，苹果把字幕文件切分成了很多小段，每一段是一个独立的`fileSequence*.webvtt`文件。(`*`表示序号，从0开始)，使用的方法我写在了Comment里了。这个脚本我没做贡献，直接fork的，非常感谢[Nicholas Riley](https://gist.github.com/nriley)
	

2. [wwdc_combine_webvtt.rb](https://gist.github.com/qiaoxueshi/5992949) 这个gist的功能是将上面获得的很多`fileSequence*.webvtt`文件合并一整个文件，其实格式理论上还是webvtt，不过我试了一下，在MPlayerX中是可以完美的显示出来的。这个script是现学的ruby现用，欢迎批评、pull request以及**改成python版**（偶是python文盲）。。。。 

3. 下载的字幕是以Video的序号命名的, [@lexrus](https://github.com/lexrus) 童鞋的这个[gist](https://gist.github.com/lexrus/5792296#file-title-txt)里提供了序号和Video名称的对应表, 感谢他。 

###2.欢迎大家提交pull request补充其他video字幕

~~在用[extract.py][1]脚本获得字幕的时候比较慢，可能是我这边网络的问题，从上面的第3项的对应表可以看出来WWDC2013 一共差不多有100个视频，目前已经获得的字幕文件是33个，还差了67个，大家如果通过上面的两个脚本拿到了剩余Video的字幕欢迎pull request和大家分享。~~

``至此，所有的100字幕文件都已经完全提交，Enjoy!!!``


###3. 有图有真相

![Pic1](sample_wwdc_subtitle.jpg "Pic1")

![Pic2](sample_wwdc_subtitle2.jpg "Pic2")


[1]: https://gist.github.com/qiaoxueshi/5976402