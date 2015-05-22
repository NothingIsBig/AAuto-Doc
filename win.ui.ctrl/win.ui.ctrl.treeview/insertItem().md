#insertItem 方法  
   添加新的节点
   
###语法
* **insertItem**(string nodeText [ ,pointer parentItem , pointer prevItem])：pointer

    添加一个文本是nodeText的节点。
 
	**参数**  
	
	_nodeText_：string，节点文本  
	
	_parentItem_：pointer，可选，父节点。若不填则添加第一级节点  
	
	_prevItem_：pointer，可选，插入位置前面节点，新建节点在此节点之后。若父节点为空，此项无效。   

	**返回值**  
	pointer，节点句柄，新建节点的句柄


* **insertItem**(table tableItem [ ,pointer parentItem , pointer prevItem])：pointer

    添加一个文本是nodeText的节点。
 
	**参数**  
	_tableItem_：table，节点文本  
	
	_parentItem_：pointer，可选，父节点。若不填则添加第一级节点  
	
	_prevItem_：pointer，可选，插入位置前面节点，新建节点在此节点之后。若父节点为空，此项无效。   

	**返回值**  
	>pointer，节点句柄，新建节点的句柄

* **insertItem(tableItem [ ,parentItem , prevItem])：hItem**

	 添加一个文本是nodeText的节点。若只有nodeText参数则添加第一级节点
 
	**参数**  
	_tableItem_
	>table，指定成员的table。  
	
	_parentItem_
	>pointer，可选，父节点。若不填则添加第一级节点  
	
	_prevItem_
	>pointer，可选，插入位置前面节点，新建节点在此节点之后。若父节点为空，此项无效。   

	**返回值**  
	_hitem_
	>pointer，节点句柄，新建节点的句柄
* **insertItem(table)：hItem**  
 添加一个根节点  
 
	**参数**  
	_nodeText_：string类型，节点文本  
	
	**返回值**  
	_hitem_：节点句柄



