# AndroidPdfViewDowload
一行代码快速实现pdf下载与本地PDF快速预览，支持线上各种文件下载到本地


##一行代码快速实现PDF的在线下载与本地预览


##使用到的技术
1，Okhttp下载文件
2，pdfview显示PDF


#下面是效果图
##下载中

![image](https://github.com/qiushi123/AndroidPdfViewDowload/blob/master/qcl_images/1.png?raw=true)

##下载完成

![image](https://github.com/qiushi123/AndroidPdfViewDowload/blob/master/qcl_images/2.png?raw=true)

##显示效果

![image](https://github.com/qiushi123/AndroidPdfViewDowload/blob/master/qcl_images/3.png?raw=true)

##支持放大缩小显示

![image](https://github.com/qiushi123/AndroidPdfViewDowload/blob/master/qcl_images/4.png?raw=true)

#代码很简单，可以到下载demo查看，下面只贴出重要代码

#1，下载pdf
	OkHttpUtils.get(pdfUrl)//
                .tag(this)//
                .execute(new DownloadFileCallBack(Environment.getExternalStorageDirectory() +
                        "/temp", "qcl.pdf"));//保存到sd卡

#2，显示pdf
	 pdfView.fromFile(file)
                //                .pages(0, 0, 0, 0, 0, 0) // 默认全部显示，pages属性可以过滤性显示
                .defaultPage(1)//默认展示第一页
                .onPageChange(this)//监听页面切换
                .load();
				
#3，简单贴下布局代码
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
             android:layout_width="match_parent"
             android:layout_height="match_parent" >

    <com.joanzapata.pdfview.PDFView
        android:id="@+id/pdfView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

    <TextView
        android:id="@+id/text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="5dp"
        android:text="1/10"/>
</FrameLayout>







