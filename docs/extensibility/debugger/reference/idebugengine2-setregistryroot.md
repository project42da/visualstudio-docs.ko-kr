---
title: "IDebugEngine2::SetRegistryRoot | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine2::SetRegistryRoot"
helpviewer_keywords: 
  - "IDebugEngine2::SetRegistryRoot"
ms.assetid: d0d81202-8a4a-4bc3-b297-30a047c5ec60
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugEngine2::SetRegistryRoot
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\)에 사용할 레지스트리 루트를 설정합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetRegistryRoot(   
   LPCOLESTR pszRegistryRoot  
);  
```  
  
```c#  
int SetRegistryRoot(   
   string pszRegistryRoot  
);  
```  
  
#### 매개 변수  
 `pszRegistryRoot`  
 \[in\] 레지스트리 루트를 사용 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 방법을 수 있습니다 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 는 DE 레지스트리 설정; 얻을 수를 사용 해야 하는 대체 레지스트리 루트를 지정 합니다 예를 들어, "HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\8.0Exp"입니다.  
  
## 참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)