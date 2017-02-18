###生成[1,2,3,4,5,6,7,8,9]的随机不重复数组
```js
	var arr=[],count=0;
	
	while(count<9){
	    var n=Math.floor(Math.random()*9+1);   //生成随机数1-9
	    if(arr.join().indexOf(n)==-1){   //去掉重复的数字
	        arr.push(n)  ;//不重复放进数组
	        count++;    //计数器加1，
	    }
	}
	console.log(arr)
```	
输出的结果是：
```js
    //[8, 9, 1, 4, 5, 7, 2, 3, 6]
```
###生成指定范围制定个数的不重复的随机数
例：生成1-100范围内的10个不重复随机数


	var arr = [];
    for(var i = 1; i <= 100; i += 1){
        arr.push(i);
    };

    arr.sort(function(){
        return 0.5 - Math.random();  //将获取到100个数字打乱顺序
    });

    arr.length = 10;   //取出10个数字

    console.log(arr);

输出的结果：

    //[51, 89, 57, 8, 75, 30, 59, 11, 65, 22]

> 关于sort方法 [w3school对sort方法的说明](http://www.w3school.com.cn/jsref/jsref_sort.asp)

>如果调用该方法时没有参数，将按照字母顺序对数组中的元素惊醒排序，说确切点，是按照字符编码的顺序排序，要实现这一点，首先应把数组的元素都转换成字符串（如果有必要），以方便进行比较。

>如果想按照其他的标准进行排序，就需要提供比较函数，该函数要比较两个值，然后返回一个用于说明两个值相对顺序的数字。比较函数应该有两个参数a和b，期返回值如下：

>>若a小于b，在排序后的数组中a应该出现在b之前，则返回一个小于0的值。

>>若a等于b，则返回0。

>>若a大于b，则返回一个大于0的值。

>例1 我们将创建一个数组，并按字母顺序进行排序：

	var arr = new Array(6)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    arr[3] = "James"
    arr[4] = "Adrew"
    arr[5] = "Martin"

    document.write(arr + "<br />")
    document.write(arr.sort())

输出的结果是：

	// George,John,Thomas,James,Adrew,Martin,
    // Adrew,George,James,John,Martin,Thomas

例 2：我们将创建一个数组，并按字母顺序进行排序：

	var arr = new Array(6)
    arr[0] = "10"
    arr[1] = "5"
    arr[2] = "40"
    arr[3] = "25"
    arr[4] = "1000"
    arr[5] = "1"

    document.write(arr + "<br />")
    document.write(arr.sort())

输出的结果是：

	//10,5,40,25,1000,1
	//1,10,1000,25,40,5

请注意，上面的代码没有按照数值的大小对数字进行排序，要实现这一点，就必须使用一个排序函数：

	function sortNumber(a,b){
		return a - b
 	}

    var arr = new Array(6)
    arr[0] = "10"
    arr[1] = "5"
    arr[2] = "40"
    arr[3] = "25"
    arr[4] = "1000"
    arr[5] = "1"

    document.write(arr + "<br />")
    document.write(arr.sort(sortNumber))

输出的结果是：

	// 10,5,40,25,1000,1
    // 1,5,10,25,40,1000
