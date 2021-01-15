---
layout : post
categories : Spring
title: 뉴렉처 Spring 11강 메모.
excerpt: 콜렉션 생성과 목록 DI
---

DI를 위해 ArrayList를 XML 코드로 생성 후 주입 ㅏㅎㄹ 수 있음

<pre>
ApplicationContext context = new ClassPathXmlApplicationContext("spring/di/setting.xml");
</pre>

ArrayList의 컬렉션형의 인자를 이용하는 생성자를 통해서 셋팅 
<bean id='exams' class="java.util.ArrayList">
    <constructor-arg>
        <list>
            <bean class="spring.di.entity.NewlecExam" p:kor="10" p:eng="20"></bean>
            <ref bean="exam"/>
        </list>
    </constructor-arg>
</bean>

<bean class="spring.di.entity.NewlecExam" p:kor="10" p:eng="20"></bean> 컬렉션에 빈을 직접 생성
<ref bean="exam"/> 위에 있는 bean 객체를 참조하여 컬렉션에 포함시킴