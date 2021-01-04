---
layout : post
categories : Spring
title: 뉴렉처 Spring 8강 메모.
excerpt: 
---

8강 내용 .
<pre>
ApplicationContext context = new ClassPathXmlApplicationContext("패키지명.지시서이름.xml");
</pre>

<pre>
ApplicationContext (인터페이스)
    - ClassPathXmlApplicationContext : 지시서.Xml 파일을 Application의 root(실행되는 위치에)에 두었다.
    - FileSystemXmlApplicationContext : xml의 실제 디렉토리 경로를 이용. 
    - XmlWebApplicationContext : Web xml이 있을때. 
    - AnnotationConfigApplicationContext : 어노테이션을 이용한 지시를 썼을때.
</pre>

ApplicationContext를 사용하기 위해서는 Spring 라이브러리를 프로젝트에 추가 해 주어야 한다. 메이븐을 이용해 dependency를 생성해 라이브러리를 가져온다.

Configure > convert메이븐프로젝트

pom file이 생성된다. 

google > Maven repository

version 과 build 사이 depnedencies추가.
<dependencies>
</dependencies>

dependencies 안에 repository에서 찾은 내용 복 붙.

Spring 라이브러리가 추가되면 
ApplicationContext를 import 할 수 있다.

이름으로 꺼내기 (object 형으로 반환된 객체를 형 변환 해주어야 함.)
<pre>
타입명 변수이름 = (형변환) context.getBean("console");
</pre>

타입으로 꺼내기 (선호 되는 방법 / 형 변환할 필요가 없다.)
이때 타입명에 인터페이스명을 써 주어도 괜찮다.
<pre>
타입명 변수이름 = context.getBean(타입명.class);
</pre>


이제 외부설정 만으로도 DI하는 객체를 변환 할 수 있게 된다.