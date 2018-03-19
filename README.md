本来写了很长一段文字，来吹捧下本适配方案简单易用效果好，最终还是删掉了，直接上传代码，说明下用法，大家可自行下载，和网上各种适配方案进行对比，择优选取适配方案。（本适配方案目前博主已运用于几百万日活app上，没有出现任何适配上的问题，此方案也是从网上摘取下来，在此给大家做个简单的总结归纳）

1.修改Config文件下的path路径，最好是自己项目的路径，如：

```
    public final static String path = "/Users/AJiang/Downloads/AndroidDimensUtils/app/src/main/res/values" ;

```
2.项目的values目录下必须存在一个dimens文件，存放

```
	<dimen name="base0.5dp">.50dp</dimen>
    <dimen name="base1dp">1.00dp</dimen>
    <dimen name="base1.5dp">1.5dp</dimen>
    <dimen name="base2dp">2.00dp</dimen>
    <dimen name="base3dp">3.00dp</dimen>
    <dimen name="base4dp">4.00dp</dimen>
    ...
```
作为基础模板，供生成其他分辨率下的文件，具体详见demo
3.运行Test文件，则会生成对应Config下几个设备配置信息

```
public final static int[] supportDevices = {240, 270, 320, 360, 400};

```
此处可根据需求更改，比如增加384，820等。


----------


****
<div align="center">  
使用前          <img src="http://img.blog.csdn.net/20180319171802466?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXF5YW5qaWFuZw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast" width="40%" height="100%"/><text>   					  使用后					</text><img src="http://img.blog.csdn.net/20180319171829489?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXF5YW5qaWFuZw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast" width="40%" height="100%" /></div> 



----------


**我们查看下w240下文件：**


![这里写图片描述](http://img.blog.csdn.net/20180319171955877?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXF5YW5qaWFuZw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

我们看到生成的几个文件下，都生成了各自对应分辨率下的dp文件，ok，大功告成了，我们看下如何使用。

```
 <TextView
        android:id="@+id/textView2"
        android:layout_width="@dimen/base80dp"
        android:layout_height="wrap_content"
        android:text="Android"
       />
```
就是这么简单，直接将80dp转换成dimen文件下80dp的引入，手机会自动去根据分辨率情况去寻找对应文件下的大小，是不是超级简单！赶紧去试试吧！

[Demo](https://github.com/AndroidJiang/AndroidDimensUtils)下载
