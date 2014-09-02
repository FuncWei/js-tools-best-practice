# refact



## 为什么要重构？

重构是个很大的话题，

当你发现一样的代码出现了3次或更多，你是否觉得它看起来重复的太多了？
当你发现一样的代码出现了3次或更多，你是否觉得不舒服？
当你发现一样的代码出现了3次或更多，你是否觉得这代码质量不高？


### 例子

下面是我模拟的一段h5里的localStorage里的代码

	localStorage.setItem('name','柯织');
	localStorage.setItem('sex','女');
	localStorage.setItem('Marrid',false);
	
这段代码看起来没有太大问题，那么继续看

	localStorage.setItem('name','柯织');
	localStorage.setItem('sex','女');
	localStorage.setItem('Marrid',false);
	localStorage.setItem('身高','160');
	localStorage.setItem('体重','45kg ');
	localStorage.setItem('爱好','旅游');
	localStorage.setItem('有车否','无');
	localStorage.setItem('有房否','无');

是不是有点烦了呢？

### 方式1，改变参数类型

	<script>

	var data = {
		'ddd':'sddsdsds',
		"kehzi":"sdsddsdsds"
	}

	setObjInLocalStorage = function(obj){
		for (var key in obj) {
			var val = obj[key];
			console.log(k+' - '+v);
			localStorage.setItem(k,v);
		}
	}

	setObjInLocalStorage(data);

	</script>
	
### 方式2，使用web SQL实现



## 总结

重构应该是每一个好的程序员在骨子里的意识，这样才能提高代码质量，提高和更新自身知识水平。