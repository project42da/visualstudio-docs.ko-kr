---
title: "IDebugPortPicker::SetSite | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugPortPicker::SetSite"
ms.assetid: 7319e187-adfe-4b3f-aec9-521356fb5a8a
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugPortPicker::SetSite
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

서비스 공급자를 설정합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetSite(  
   IServiceProvider * pSP  
);  
```  
  
```c#  
public int SetSite(  
   IServiceProvider pSP  
);  
```  
  
#### 매개 변수  
 `pSP`  
 \[in\] 서비스 공급자의 인터페이스에 대 한 참조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 다른 메서드가 호출 되기 전에이 메서드를 호출 합니다.  
  
## 참고 항목  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)