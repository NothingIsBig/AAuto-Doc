# picturebox-图像控件

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>image</td><td>string，指定在控件上显示的图像文件的路径</td></tr>
	<tr><td>autosize</td><td>1/0，自适应图片，根据图片大小自动调整控件大小，禁用该选项则自动缩放图片到控件大小。</td></tr>
	<tr><td>center</td><td>1/0，图片是否垂直并水平居中，启用则同时禁用控件自适应、或图片自动缩放功能。</td></tr>
	<tr><td>notify</td><td>1/0，是否启用事件回调函数oncommand。</td></tr>
</table>
###成员
<table>
	<tr><td>picturebox.image</td><td>按钮图片或图标,赋值必须是图片文件路径或数据,位图句柄由窗体负责销毁,取值时返回位图句柄</td></tr>
	<tr><td>picturebox.autosize</td><td>是否允许控件自适应图片大小，设置center属性为true时,autosize属性无效</td></tr>
	<tr><td>picturebox.setIcon(__/*图标句柄*/)</td><td>设置图标,成功返回true,自动销毁原来的位图</td></tr>
	<tr><td>picturebox.setImage(__/*图片句柄*/)</td><td>设置图片,成功返回true,自动销毁原来的位图</td></tr>
	<tr><td>picturebox.setIcon(__/*图标句柄*/,false)</td><td>设置图标,成功返回控件原来的位图句柄,必须调用::DeleteObject()函数销毁该句柄</td></tr>
	<tr><td>picturebox.setImage(__/*图片句柄*/,false)</td><td>设置图片,成功返回控件原来的位图句柄,必须调用::DeleteObject()函数销毁该句柄</td></tr>
</table>

* 显示图片

		winform.picturebox.image=$"C:\1.jpg"; 
		winform.picturebox.image="C:\1.jpg";  
		winform.picturebox.image=string.load("C:\1.jpg"); 
		winform.picturebox.image=con.picture.load("C:\1.jpg").CopyHandle()

* 改变控件大小

		winform.picturebox.setPos(,,400,400);
		winform.picturebox.redraw();
* 删除图片显示

		winform.picturebox.image=null;
		//或
		//winform.picturebox.setImage(null);

## 示例

* **picturebox显示png**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 
		picturebox={ bottom=141;right=252;left=70;top=41;transparent=1;z=1;text="picturebox";cls="picturebox" }
		)
		/*}}*/		
		winform.show() 		
		import gdip;
		import inet.http; 		
		var imgData = inet.http().get("http://www.meituan.com/account/captcha");
		var img = gdip.image(imgData)	
		var graphics = gdip.graphics(winform.picturebox) 
		gdip.DrawImage(graphics,img,0,0)		
		win.loopMessage();

* **显示网络图片**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( right=687;bottom=610;parent=...;text="AAuto Form" )
		winform.add( 
		button2={ bottom=385;text="button2";left=614;top=355;z=3;right=671;cls="button" };
		picturebox={ bottom=184;right=608;left=344;top=24;z=1;edge=1;cls="picturebox" };
		button={ bottom=344;text="button";left=614;top=319;z=2;right=670;cls="button" }
		)
		/*}}*/
		import inet.http; 
		import soImage;
		//创建图像
		var img = soImage();
		//内存加载图像文件
		img.setBytes(
		   inet.http().get("https://pay.sdo.com/Deposit/newvalidatecode1.aspx?")
		   ,"*.jpg"
		   ); 
		//在屏幕上显示图片 
		winform.picturebox.image  = img.getBytes("*.bmp")
		winform.show() 
		win.loopMessage();
		return winform;

* **按比例缩放图片**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=553;parent=...;right=728;text="AAuto Form" )
		winform.add( 
		trackbar={ dr=1;dl=1;bottom=35;max=100;right=694;left=90;dt=1;top=5;z=2;min=0;cls="trackbar" };
		picturebox={ dr=1;dl=1;bottom=537;right=706;left=23;dt=1;top=57;transparent=1;z=1;cls="picturebox" };
		static={ dl=1;bottom=44;text="缩放比例";left=20;dt=1;top=17;z=3;right=83;transparent=1;cls="static" }
		)
		/*}}*/
		import gdip;  
		var img = gdip.image("1.bmp"); 
		winform.picturebox.image="1.bmp" 
		winform.trackbar.onnotify = function(id,code,ptr){
		    var r = winform.trackbar.pos / 100
		    winform.picturebox.setPos( , ,img.width * r,img.height * r )  
		}
		winform.trackbar.pos = 50;
		winform.picturebox.setPos( , ,img.width/2,img.height/2 ) 
		winform.show() 
		win.loopMessage();