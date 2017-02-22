---
title: "IDebugCustomAttribute::GetName | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCustomAttribute::GetName"
helpviewer_keywords: 
  - "IDebugCustomAttribute::GetName"
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCustomAttribute::GetName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 특성의 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetName(   
   BSTR* bstrName  
);  
```  
  
```c#  
int GetName(  
   out string bstrName  
);  
```  
  
#### 매개 변수  
 `bstrName`  
 \[out\] 사용자 지정 특성의 이름이 들어 있는 문자열을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에서 반환 된 명명 된 특성을 선언 하는 데 사용 되는 클래스의 이름에 해당 합니다.  C\#는 "Attribute" 접미사를 선언에 사용 하는 경우 사용자 지정 특성 이름에서 삭제 하도록 허용 하는이 정확 하 게 사용자 지정 특성 클래스의 이름에 해당 합니다.  
  
## 참고 항목  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)