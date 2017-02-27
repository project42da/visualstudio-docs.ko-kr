---
title: "IDebugCoreServer3::QueryIsLocal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCoreServer3::QueryIsLocal"
helpviewer_keywords: 
  - "IDebugCoreServer3::QueryIsLocal"
ms.assetid: cca030de-f853-4ed7-b2fb-395f08a6b884
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugCoreServer3::QueryIsLocal
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

로컬 호출자에 게 서버 인지 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```c#  
int QueryIsLocal();  
```  
  
## 반환 값  
 반환 `S_OK` 서버 로컬 수를 나타낼 수 있습니다.  반환 `S_FALSE` 서버는 일반적으로 원격 디버깅에 사용 됩니다 msvsmon.exe의 인스턴스를 실행 하는 경우.  
  
## 참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)