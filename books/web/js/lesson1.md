---
title: jquery操作form(select/radio/checkbox)
description: 总结一下jquery操作form，formdata+ajax提交表单
---

# jquery操作select

1、获取当前选中项的value
```js
$(".selector").val();
```

2、 获取当前选中项的text
```js
$(".selector").find("option:selected").text();
```

3、设置value为xx的项选中
```js
$(".selector").val("xx");
```
     

4、设置text为pxx的项选中
```js
$(".selector").find("option[text='pxx']").attr("selected",true);
```


5、清空select的option项,并添加新的option项，适用于select级联等场景
```js
$(".selector").empty();
var option = $("<option>").val(1).text("pxx");
$(".selector").append(option);
```

# jquery操作radio
1、获取radio选中的值
```js
$('input[name=radio]:checked').val();
```

2、设置某个radio选中
```js
$("input[name='radio'][value='value']").attr("checked",true);
```


# jquery操作checkbox
1、获取radio选中的值
```js
$('input[name=radio]:checked').val();
```

2、设置某个checkbox选中
```js
$('input:checkbox').attr("checked", 'checked');//or
$('input:checkbox').attr("checked", true);
```


# formdata+ajax提交表单
```js
var formData = new FormData(document.querySelector("#myform"));
$.ajax({
	url:url,
	type:'post',
	data:formData,
	processData: false,
	contentType: false,
	dataType:"json",
	success:function(response){
		if(response.code == 200){
			
		}else{
			
		}
	}
});
```




