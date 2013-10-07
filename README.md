WWDC 2013 视频字幕（英文，共100个）
========================


###1. How I get them? 

这要从下面1和2两个gist说起。。。

1. [extract.py][1] (fork from [Nicholas Riley](https://gist.github.com/nriley)'s [extract.py](https://gist.github.com/nriley/5874460))  用来获取视频的`fileSequence*.webvtt`文件，该文件是web格式的英文字幕文件，苹果把字幕文件切分成了很多小段，每一段是一个独立的`fileSequence*.webvtt`文件。(`*`表示序号，从0开始)，使用的方法我写在了Comment里了。这个脚本我没做贡献，直接fork的，非常感谢[Nicholas Riley](https://gist.github.com/nriley)
	

2. [wwdc_combine_webvtt.rb](https://gist.github.com/qiaoxueshi/5992949) 这个gist的功能是将上面获得的很多`fileSequence*.webvtt`文件合并一整个文件，其实格式理论上还是webvtt，不过我试了一下，在MPlayerX中是可以完美的显示出来的。这个script是现学的ruby现用，欢迎批评、pull request以及**改成python版**（偶是python文盲）。。。。 

3. 下载的字幕是以Video的序号命名的, [@lexrus](https://github.com/lexrus) 童鞋的这个[gist](https://gist.github.com/lexrus/5792296#file-title-txt)里提供了序号和Video名称的对应表, 感谢他。 另外[@puttin](https://github.com/puttin)同学提供了一个批量修改文件名的[脚本](https://gist.github.com/puttin/6547007),点进去有图有真相哦，非常实用，Thx~4. 



###2.欢迎大家提交pull request补充其他video字幕

~~在用[extract.py][1]脚本获得字幕的时候比较慢，可能是我这边网络的问题，从上面的第3项的对应表可以看出来WWDC2013 一共差不多有100个视频，目前已经获得的字幕文件是33个，还差了67个，大家如果通过上面的两个脚本拿到了剩余Video的字幕欢迎pull request和大家分享。~~

``至此，所有的100字幕文件都已经完全提交，Enjoy!!!``

##3.TODO
###3.1 去重和格式化为真正srt格式的字幕文件（以支持手机播放）
看了一天的Bash相关的命令，写下了下面的脚本来去重和格式化为srt格式的字幕文件，下面的`408.srt`改为你想格式化的文件名：

```
awk -v RS="" '{gsub("\n", "-Z"); print}' 408.srt | awk '$0 !~/^WEB/ {print $0}' | uniq | awk '{printf "\n%s-Z%s", NR,$0 }'  | awk -v ORS="\n\n" '{gsub("-Z", "\n"); print}' >> 408-SD.srt
```
逐行解释下:

```
awk -v RS="" '{gsub("\n", "-Z"); print}' 408.srt   把换行换为-Z，在后面还要换回来
awk '$0 !~/^WEB/ {print $0}'  去掉以WEB开头的
uniq   去重
awk '{printf "\n%s-Z%s", NR,$0 }' 加上行号
awk -v ORS="\n\n" '{gsub("-Z", "\n"); print}' >> 408-SD.srt 格式化并把—Z换成\n
```




###4. 有图有真相

![Pic1](sample_wwdc_subtitle.jpg "Pic1")

![Pic2](sample_wwdc_subtitle2.jpg "Pic2")


[1]: https://gist.github.com/qiaoxueshi/5976402