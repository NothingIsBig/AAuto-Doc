#tab-ѡ��ؼ�


###�������  
<table>	
	<tr><td>������</td><td>���ƣ�ָ���ؼ����Ʊ���ʹ�úϷ��ı�����</td></tr>
</table>


###��Ա
<table>
	<tr><td>tab.loadForm("__/*������aau�ļ�·��*/")</td><td>�����ⲿ�����ļ�����ӵ�tabҳ.,��ע�Ᵽ���ⲿ�����ļ��Ժ��������.</td></tr>
	<tr><td>tab.remove(__)</td><td>����Ϊ��ֵ���Ƴ�ָ��������ѡ��ҳ</td></tr>
	<tr><td>tab.removeAll()</td><td>�Ƴ�����ѡ�</td></tr>
	<tr><td>tab.items</td><td>�����Ӵ����б�ֻ������</td></tr>
	<tr><td>tab.items[]</td><td>!winform.</td></tr>
	<tr><td>tab.adjustRect()</td><td>�����Ӵ��ڴ�С����Ӧ�ͻ���</td></tr>
	<tr><td>tab.selIndex</td><td>��ȡ�����õ�ǰѡ������,��ʼ����Ϊ1</td></tr>
	<tr><td>tab.add(__)</td><td>�����ô�����������ɴ���������룬,Ȼ�󽫴��������win.form�����滻Ϊ�˺�����,������������win.form�Ĳ���(text������ʾѡ�����)��</td></tr>
	<tr><td>tab.hitTest(.(x����,y����,�Ƿ���Ļ����)</td><td>��������ָ���ѡ������,��������ʡ��,Ĭ��Ϊfalse.,�����ָ���κβ��������Զ����� win.getMessagePos() ��ȡ��Ϣ����</td></tr>
	<tr><td>tab.setItem(__/*����*/,"")</td><td>����ѡ��ṹ��</td></tr>
	<tr><td>tab.getItem(__/*����*/)</td><td>��ȡѡ��ṹ��</td></tr>
	<tr><td>tab.setItemText(__/*����*/,"")</td><td>����ѡ�����</td></tr>
	<tr><td>tab.getItemText(__/*����*/)</td><td>��ȡѡ����� </td></tr>
	<tr><td>tab.getItemRect(__/*����*/)</td><td>��ȡѡ�����λ��</td></tr>
	<tr><td>win.ui.ctrl.tab.TCITEM()</td><td>ѡ��ṹ��</td></tr>
</table>
###�÷�
* ����tab
* �޸�tab
* tab��Ŀؼ�


##ʾ��

* **Tab�ؼ�ʾ��**

		import win;
		import win.ui; 
		import win.ui.menu
		import win.ole.image
		/*DSG{{*/
		var winform = win.form(parent=...; top=0;bottom=249;text="AAuto Form";left=0;right=349 )
		winform.add( 
		tab={ bottom=221;right=318;left=22;top=26;z=1;text="tab";edge=1;cls="tab" }
		)
		/*}}*/		
		winform.tab.onnotify = function(id,code,ptr){
		    //var nmdr = win.ui.NMHDR(); raw.convert( ptr,nmdr );
		    if(code==0xFFFFFDD9/*_TCN_SELCHANGE*/) 
		        win.msgbox("�л�") 
		}//endproc		
		
		/*
		ΪTABѡ��ؼ����һ��ҳ�档
		һ��ҳ��ʵ���Ͼ���һ����ͨ�Ĵ��壬����ʹ�ô�����������ɣ�Ȼ��win.form�����滻Ϊwinform.tab.add���ɡ�
		����ָ��text����(ѡ�����)���Լ�bottom(�߶�)��right(���)
		*/
		page = winform.tab.add(  text="ѡ��";bottom=140;right=325 )
		page.add( 
			button={ bottom=49;text="���";left=36;right=135;top=21;z=1;cls="button" } 
		) 
		page.button.oncommand = function(id,event){
		    win.msgbox( page.button.text,"Ҳ����ʹ�ûص�����" ); 
		}//endproc		
		page2 = winform.tab.add(  text="������";bottom=140;right=325  )
		page2.add( 
		button={ bottom=49;text="Hello";left=36;right=135;top=21;z=1;cls="button" }
		) 
		page2.button.oncommand = function(id,event){
		    win.msgbox( page2.button.text,"Hello!" ); 
		}//endproc		
		winform.show(true) 
		win.loopMessage( winform );

* **����Tabѡ�ҳ�еĿؼ�����**

		page = winform.tab.add(  text="ѡ��";bottom=140;right=325 )
		page.add( 
		button={ 
			bottom=49;text="���";left=36;right=135;top=21;z=1;cls="button" };
		 	edit={ ah=1;bottom=61;right=205;left=113;top=38;z=23;aw=1;edge=1;cls="edit" };
		 ) 
		 //������ʽ��ʹ��page.edit.text="this"�Ϳ��Զ�ѡ���еĿؼ����Խ�������

* **Tabѡ�ҳ�еİ�ť**

		import win.ui;
		 var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		 winform.add( 
		       tab1={ bottom=368;right=560;left=16;top=24;z=1;edge=1;cls="tab" }
		 )
		 page1 = winform.tab1.add(  text="ITEM1";bottom=128;right=224)
		 page1.add(
		       button1={ bottom=100;right=224;left=56;top=72;z=2;text="��ť";cls="button" };
		       edit={ bottom=128;text="������ť";left=80;multiline=1;top=88;z=2;right=408;edge=1;cls="edit" };
		 )
		 page1.button1.oncommand = function(id,event){
		    page1.edit.text="����ɹ���";
		 }
		 winform.show() 
		 win.loopMessage();

* **�л���ͬѡ�**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=293;parent=...;right=461;text="AAuto Form" )
		winform.add( 
		tab={ bottom=234;right=393;left=30;top=25;z=1;edge=1;cls="tab" }
		)
		/*}}*/

		winform.tab.onnotify = function(id,code,ptr){
			if(code==0xFFFFFDD9/*_TCN_SELCHANGE*/)//�л�ѡ�
			select(winform.tab.selIndex) {
				case 1 {
				    win.msgbox("ѡ�1")
				}
				case 2 {
				    win.msgbox("ѡ�2")
				}
				case 3 {
				    win.msgbox("ѡ�3")
				}
			}
		}
		//���ѡ�
		page1 = winform.tab.add(text="ѡ�1");
		page2 = winform.tab.add(text="ѡ�2");
		page3 = winform.tab.add(text="ѡ�3");

		winform.show() 
		win.loopMessage();

* **�����ͣ��ѡ���ǩ����ʾ��Ϣ**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;text="AAuto Form";right=599 )
		winform.add( 
		tab={ bottom=368;right=552;left=40;top=24;z=1;edge=1;cls="tab" }
		)
		/*}}*/

		winform.tab.add({ text = "��һҳ" });
		winform.tab.add({ text = "�ڶ�ҳ" });
		winform.tab.add({ text = "����ҳ" });
		winform.tab.wndproc = {
			[0x200/*_WM_MOUSEMOVE*/] = function (hwnd, message, wParam, lParam) {
				winform.text = string.format(
					"�����ͣ�ڵ� %d ��ѡ���",
					winform.tab.hitTest( win.getMessagePos(lParam) )
				);
			}
		}
		winform.show();
		win.loopMessage();

