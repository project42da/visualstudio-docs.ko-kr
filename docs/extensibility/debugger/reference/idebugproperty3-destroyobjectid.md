---
title: "IDebugProperty3::DestroyObjectID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty3::DestroyObjectID"
helpviewer_keywords: 
  - "IDebugProperty3::DestroyObjectID"
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugProperty3::DestroyObjectID
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 속성을 다른 모든 속성을 고유 하 게 식별 하 더 이상 호출자가 존중 한다는 나타내는이 속성에 연결 된 고유 ID를 소멸 시킵니다.  
  
## 구문  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```c#  
int DestroyObjectID();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버그 엔진 \(이 이미를 고유 하 게 내부적으로 추적 하기 때문에\) 고유 Id에 대 한 속성을 지원 하기 위해 필요 하지 않은 경우, 반환할 수 있습니다 간단 하 게 한 다음 `E_NOTIMPL` 이 메서드에 대 한.  
  
 고유 Id를 생성을 호출 하는 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) 메서드는 호출자가 다른 속성 중이 속성이 고유 하 게 식별 되는지 확인 하려는 경우.  
  
## 참고 항목  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)