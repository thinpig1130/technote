---
layout : post
categories : Spring
title: 뉴렉처 Spring 9강~10강 메모.
excerpt: 
---

Setter를 이용한 값 셋팅
<bean id="exam" class="spring.di.entity.NewlecExam">
    <property name="kor">
        <value>10</value>
    </property>
    <property name="eng" value="10"/>
    <property name="math" value="10"/>
    <property name="com" value="10"/>
</bean>

property를 이용해 값을 설정할 때, setter가 없으면 error 발생한다.
BeanCreationException


생성자를 이용한 값 셋팅 (값 4개를 받는 생성자를 이용 / 순서대로 들어감)
<bean id="exam" class="spring.di.entity.NewlecExam">
    <constructor-arg value="10">
    <constructor-arg value="10">
    <constructor-arg value="10">
    <constructor-arg value="10">
</bean>

index를 이용해서 값이 들어가는 순서를 지정할 수 있다. 
<bean id="exam" class="spring.di.entity.NewlecExam">
    <constructor-arg index="0" value="10">
    <constructor-arg index="3" value="10">
    <constructor-arg index="1" value="10">
    <constructor-arg index="2" value="10">
</bean>

(선호되는 방법)
생성자의 변수명을 name 속성에 지정하여 이용하는 방법.
장점 : 들어가는 값의 의미를 지시서에서도 유추 할 수 있다.
<bean id="exam" class="spring.di.entity.NewlecExam">
    <constructor-arg name="kor" value="10">
    <constructor-arg name="eng" value="10">
    <constructor-arg name="com" value="10">
    <constructor-arg name="math" value="10">
</bean>

생성자의 값의 갯수는 동일하나 타입이 다른 생성자가 있는 경우.
type을 이용하여 지정할 수 있다.
<bean id="exam" class="spring.di.entity.NewlecExam">
    <constructor-arg name="kor" type="float" value="10">
    <constructor-arg name="eng" type="float" value="10">
    <constructor-arg name="com" type="float" value="10">
    <constructor-arg name="math" type="float" value="10">
</bean>


좀더 편하게!! 
속성을 지정하기 위한 네임스페이스

Setter를 이용하여 값을 setting.
<bean id="exam" class="spring.di.entity.NewlecExam" p:kor="10" p:eng="10"/>

<property name="eng" value="10"/> = 좌우 동일한 의미 = p:eng="10"




위와 같이 편리하게 지시서를 작성하려면 추가적인 처리기의 도움을 받아야 한다.

이클립스 XML 파일 아래 > Namespaces Click! 
> p - http://www.springframework.org/schema/p Check!


소스 코드로 돌아가면 beans 태그의 속성 안에 아래 내용이 추가 된 것을 확인 할 수 있다.
xmlns:p="http://www.springframework.org/schema/p"



