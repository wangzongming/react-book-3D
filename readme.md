---------------------------------------v0.1

---------说明
    pc和移动动能用
    此项目就只提供了翻书效果，其余功能可根据提供的api自己实


---------api:
    配置项：images:[{//图片配置 每个图片就是一页
                src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/1.jpg'
            },{src：...},{src：...}]
            pageEnd:function(flag){/*翻书到第一页或者最后一页会触发  flag==='first' 是首页*/}
            touchPage:function(curPageIndex){/*翻页时回调函数  参数是当前页数*/}

    方法：
        callback（回调）全部为可选参数
        
        .nextPage(callback);//下一页
        .prevPage(callback);//上一页
        .lastPage(callback);//去尾页
        .firstPage(callback);//去首页
        .gotoPage(pageNum, callback);//去指定页数 参数为（目标页数  翻页成后的回调）

    属性：
        .pageIndex;  //当前页索引


---------eg:
//用户自定义的配置
window.Wxx = window.wxx = w = {
	images:[{//图片配置 每个图片就是一页
		src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/1.jpg'
	},{
		src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/2.jpg'
	},{
		src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/3.jpg'
	},{
		src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/4.jpg'
	},{
		src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/5.jpg'
	},{
		src:'http://books.mingbianji.com/showbox/iPhone6&AppleWatch/files/mobile/6.jpg'
	}], 
	soundBaseURL:'./style/raw/mp3.mp3',//翻书声音路径
	pageEnd:function(flag){//翻书到第一页或者最后一页 
		if(flag === 'first'){
			console.log('翻到了第一页');
		}else{
			console.log('翻到了最后');
		}
	},
	touchPage:function(curPageIndex){//翻页时回调函数 
		console.log(`当前页数【${curPageIndex}】`)
	}
}
setTimeout(function(){
	window.Wxx.gotoPage(1, function(){
		console.log('跳转完成');
		// window.Wxx.lastPage();
	})
}, 2000)

---------截图
    ![测试](./v0.1-1.jpg)
    ![测试](./v0.1-1.jpg)

---------目录结构
	-----javascript
		----config.js(用于修改配置的文件)
		----jquery-1.9.1.min
		----main.js(核心文件)
		----loadindeJs.js(加载文件)
	-----style
		----style.css(样式文件)
			...
	index.html


---------log:
    v0.1:
        1.提供正常翻书功能  
          