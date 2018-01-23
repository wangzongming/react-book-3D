#---------------------------------------v0.1

##---------说明

	pc和移动动能用
	此项目就只提供了翻书效果，其余功能可根据提供的api自己实


##---------api:
###    配置项：
	images:[{//图片配置 每个图片就是一页
			src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/1.jpg'
		},{src：...},{src：...}]
	pageEnd:function(flag){/*翻书到第一页或者最后一页会触发  flag==='first' 是首页*/}
	touchPage:function(curPageIndex){/*翻页时回调函数  参数是当前页数*/}

###    方法：

	callback（回调）全部为可选参数

	.nextPage(callback);//下一页
	.prevPage(callback);//上一页
	.lastPage(callback);//去尾页
	.firstPage(callback);//去首页
	.gotoPage(pageNum, callback);//去指定页数 参数为（目标页数  翻页成后的回调）

###    属性：

	.pageIndex;  //当前页索引

## ---------eg: 

*	用户自定义的配置

	window.Wxx = window.wxx = w = { <br/>
		images:[{//图片配置 每个图片就是一页<br/>
			src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/1.jpg'<br/>
		},{<br/>
			src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/2.jpg'<br/>
		}], <br/>
		soundBaseURL:'./style/raw/mp3.mp3',//翻书声音路径<br/>
		pageEnd:function(flag){//翻书到第一页或者最后一页 <br/>
			if(flag === 'first'){<br/>
				console.log('翻到了第一页');<br/>
			}else{<br/>
				console.log('翻到了最后');<br/>
			}<br/>
		},<br/>
		touchPage:function(curPageIndex){//翻页时回调函数 <br/>
			console.log(`当前页数【${curPageIndex}】`)<br/>
		}<br/>
	}<br/>

	setTimeout(function(){<br/>
		window.Wxx.gotoPage(1, function(){<br/>
			console.log('跳转完成'); <br/>
		})<br/>
	}, 2000) <br/>
 
## ---------截图
    ![pc](./v0.1-1.jpg)
    ![mobile](./v0.1-2.jpg)

## ---------目录结构
*	file
	<ul>
		<li>
			-----javascript
				<p> ----config.js(用于修改配置的文件)</p>
				<p> ----jquery-1.9.1.min</p>
				<p> ----main.js(核心文件)</p>
				<p> ----loadindeJs.js(加载文件)</p>
		</li>
		<li>
			-----style
				<p> ----style.css(样式文件)</p>
				<p> ...</p>
		</li>
		<li>
			index.html
		</li>
	</ul> 


## --------------------------log:
+	v0.1:
        <p>1.提供正常翻书功能  
          
