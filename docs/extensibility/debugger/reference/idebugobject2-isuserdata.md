---
title: "IDebugObject2::IsUserData | Microsoft Docs"
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
  - "IDebugObject2::IsUserData"
helpviewer_keywords: 
  - "IDebugObject2::IsUserData 메서드"
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugObject2::IsUserData
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 데이터 개체를 나타내는지 여부를 확인 합니다.  
  
## 구문  
  
```cpp  
HRESULT IsUserData(  
   BOOL* pfUser  
);  
```  
  
```c#  
int IsUserData(  
   out int pfUser  
);  
```  
  
#### 매개 변수  
 `pfUser`  
 \[out\] 0이 아닌 반환 \(`TRUE`\) 사용자 데이터 개체를 나타내는 경우 0 \(`FALSE`\) 표시 되지 않는 경우.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 사용자 데이터 JustMyCode \(사용자 코드와 스택 추적에 표시 되므로 모듈 표시 사용자 구성 가능 옵션\)로 지정 된 모듈의 일부인 개체입니다.  
  
## 참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)