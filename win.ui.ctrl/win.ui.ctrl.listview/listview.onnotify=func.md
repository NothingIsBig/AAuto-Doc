


		winform.listview1.onnotify = function(id,code,ptr){// 选中某行后static显示该行的行号
		       select(code) {
		             case  0xFFFFFF9B/*_LVN_ITEMCHANGED*/ {
		                 var h = winform.listview1.selIndex
		                 if(h){
		                        winform.static.text=h 
		                        }  
		                 }
		        }
		 }