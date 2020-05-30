# day1

​	console.log(exports)//第一个参数 对象

​	console.log(require)//第二个参数 函数

​	console.log(module) //对象console.log(__filename)  文件路径(绝对路径)__

​	console.log(__dirname)   文件夹路径(绝对路径)

1. exports    //类似于ESModule中的 export

2.require 导入模块
	let obj=require("./b.js"); 
	console.log(num); 
	console.log(obj);

3.module    
id,path当前文件(夹)路径    //exports:{}    //parent:父模块

4.__filename当前文件所在路径

5.__dirname当前文件夹所在路径


console.log(require.main);//返回主模块
// 主模块:node命令调用的哪个模块哪个就是主模块

// console.log(require.resolve("./a.js"));//传相对路径,返回绝对路径

// console.log(require.cache);
//当前所有依赖模块的对象
//模块的路径是属性,值是模块对象
// 返回所有已经被加载的模块


// module 模块化对象
    //id "." 代表当前模块是主模块
    //module.exports 正真导出去的对象