---
title: "IDebugProperty3::CreateObjectID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty3::CreateObjectID"
helpviewer_keywords: 
  - "IDebugProperty3::CreateObjectID"
ms.assetid: f2fa81e7-822f-456e-8729-a96a18eea771
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProperty3::CreateObjectID
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

다른 모든 속성 중에서 고유한 수 있도록이 속성에 대 한 고유 ID를 만듭니다.  
  
## 구문  
  
```cpp  
HRESULT CreateObjectID(  
   void  
);  
```  
  
```c#  
int CreateObjectID();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버그 세션이 다른 속성 중이 속성이 고유 하 게 식별 되는지 확인 하려는 경우이 메서드가 호출 됩니다.  디버그 엔진 \(DE\) 다룹니다 속성이 이미 고유 하 게 식별 되지 않은 경우이 메서드를 지원 합니다.  DE는이 방법을 지원 하지 않을 경우, 반환 `E_NOTIMPL`.  
  
 모든 고유 ID를 사용 하 여 만든 `CreateObjectID` 때 소멸 되는 [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md) 메서드가 호출 됩니다. 이 또한이 속성이 고유 하 게 식별 하는 데 필요의 끝을 알립니다.  
  
> [!NOTE]
>  DE 고유 Id에 대 한 원하는 모든 것을 수행할 수 있도록이 고유 ID를 검색할 수 있는 방법이 없을 때의 `CreateObjectID` 메서드가 호출 됩니다.  
  
## 참고 항목  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)