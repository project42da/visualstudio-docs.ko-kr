---
title: "포함하는 형식 &#39;&lt;typename&gt;&#39;이 CLS 규격이 아니므로 &#39;&lt;eventname&gt;&#39; 이벤트의 &#39;&lt;procedurename&gt;&#39;메서드를 CLS 규격으로 표시할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40053"
  - "bc40053"
helpviewer_keywords: 
  - "BC40053"
ms.assetid: 5f7aaf64-b5e6-4f97-9ebd-44cd4c7e8bf5
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 포함하는 형식 &#39;&lt;typename&gt;&#39;이 CLS 규격이 아니므로 &#39;&lt;eventname&gt;&#39; 이벤트의 &#39;&lt;procedurename&gt;&#39;메서드를 CLS 규격으로 표시할 수 없습니다.
사용자 지정 이벤트는 `AddHandler` 또는 `RemoveHandler` 프로시저를 선언하고 `<CLSCompliant(True)>`로 표시하지만 해당 이벤트가 `<CLSCompliant(False)>`로 표시되거나 표시되지 않는 형식으로 정의되었습니다.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute>를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40053  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요하면 CLS 규격인 형식 내에서 이벤트를 정의합니다.  
  
-   이 이벤트를 포함 형식 내에 유지하려면 해당 정의에서 <xref:System.CLSCompliantAttribute>를 제거하거나 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [How to: Declare Custom Events To Avoid Blocking](../Topic/How%20to:%20Declare%20Custom%20Events%20To%20Avoid%20Blocking%20\(Visual%20Basic\).md)   
 [How to: Declare Custom Events To Conserve Memory](../Topic/How%20to:%20Declare%20Custom%20Events%20To%20Conserve%20Memory%20\(Visual%20Basic\).md)   
 [빌드에 없음: AddHandler 및 RemoveHandler](http://msdn.microsoft.com/ko-kr/a7a24bd2-519a-46fe-8a2c-2b9df2ca28ef)   
 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)