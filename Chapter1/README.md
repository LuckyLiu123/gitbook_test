# 第一章

## **这是第一章节的内容**

`function deepClone(value){`

​	`if(Array.isArray(value)){`

​		`return value.map(deepClone);`

​	`}else if(value && typeof value === 'object'){`

​		`var res = {};`

​		`for(var key in value){`

​			`res[key] = deepClone(value[key]);`	

​		`}`

​		`return res;`

​	`}else{`

​		`return value;`

​	`}`

`}`