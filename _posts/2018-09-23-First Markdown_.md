---
layout: post
title:  "First Markdown"
date:   2018-09-23 20:16:01 +0830
categories: ETC
---
 
<hr>
=, 헤드라인
=
<b>나의</b> 첫번째 마크다운 포스트
<br>
<br>
<br>

# #, 헤드라인
#헤드라인이 더 직관적이다

-, 소제목
-

## ##, 소제목

### ###, 오오 신기하군
#### ####, 오오 신기하군
##### #####, 오오 신기하군
###### #######, 오오 신기하군

# >, BlockQuote
>나재은 그는 누구인가
>> 그는 과연..
>>> 너는 누구냐
>>>>>> 세 번 건너 뛰면?

# -, 목록
- Web application
	- Spring Framework
		- Spring Framework란?
		- 장점
		- 단점
		 	- 어디까지 가니
		 		- 어디까지 가니
		 			- 어디까지 가니
	- Node.js
		- Node.js란?
		- 장점
		- 단점

# 1, 순서 있는 목록
1. 목차
	1. 오늘 할 일
	3. 내일 할 일
	2. 모레 할 일
	4. 글피 할 일 
		1. 오 알파벳이다


# 대망의 코드!
<pre>
&lt;pre&gt;여긴 뭐징&lt;/pre&gt;
</pre>
```{.java}
class MySingletonObject extend MyParentClass implement MyInterFace{
	public static final int MY_CONSTANT = 100;          

	private static SingletonObject instance;      
	
	// Private Constructor
	private SingletonObject(){  
		super();
		}

	public static SingletonObject getInstance(){
		if(instance == null){
			instance = new SingletonObject();
		}
		return instance;
	}

	@override
	public void interfaceFunc(){
	
	}
}
```

## 문장 중간에 코드 블록
위의 코드에서 `MySingleObject.getInstance();`를 이용해서 해당 클래스를 생성 및 호출합니다.


## 이거슨 표
| head1 | head2 |
|------|-------|
| hello | foo |
| hi    | bar |

```
| head1 | head2 |
|------|-------|
| hello | foo |
| hi    | bar |
```