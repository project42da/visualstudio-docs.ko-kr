---
title: "&#39;&lt;classname&gt;&#39; 클래스의 &#39;Microsoft.VisualBasic.ComClassAttribute&#39;가 &lt;type&gt; &#39;&lt;typename&gt;&#39;에서 동일한 이름의 멤버와 충돌하는 &lt;type&gt; &#39;&lt;membername&gt;&#39;를 암시적으로 선언함 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BC42101"
ms.assetid: 001c8eaa-19b6-44fa-8056-4186ecffbda8
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname&gt;&#39; 클래스의 &#39;Microsoft.VisualBasic.ComClassAttribute&#39;가 &lt;type&gt; &#39;&lt;typename&gt;&#39;에서 동일한 이름의 멤버와 충돌하는 &lt;type&gt; &#39;&lt;membername&gt;&#39;를 암시적으로 선언함
'\<classname\>' 클래스의 'Microsoft.VisualBasic.ComClassAttribute'가 \<type\> '\<typename\>'에서 동일한 이름의 멤버와 충돌하는 \<type\> '\<membername\>'를 암시적으로 선언합니다. 기본 '\<typename\>'의 이름을 숨기려는 경우 'Microsoft.VisualBasic.ComClassAttribute\(InterfaceShadows:\=True\)'를 사용합니다.  
  
 `COMClassAttribute` 특성 블록을 사용하는 클래스가 동일한 이름을 기본 클래스의 멤버로 지정하여 인터페이스를 암시적으로 정의합니다. 이 경우 인터페이스 이름이 기본 클래스 멤버를 숨겨야 합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42101  
  
### 이 오류를 해결하려면  
  
1.  기본 클래스 멤버를 숨기려면 `ComClassAttribute` 특성 블록에서 `InterfaceShadows:=True`를 설정합니다.  
  
2.  기본 클래스 멤버를 숨기지 않으려면 클래스 이름을 변경합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic에서 사용되는 특성](http://msdn.microsoft.com/ko-kr/22231318-8a40-49af-9245-e0aab723563b)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [ComClassAttribute 클래스](http://msdn.microsoft.com/ko-kr/5c2f0835-9210-47dc-bc59-5c1769953574)   
 [ComClassAttribute.InterfaceShadows 속성](http://msdn.microsoft.com/ko-kr/0fae25bd-e0ba-4755-a76c-3b526b1ac795)