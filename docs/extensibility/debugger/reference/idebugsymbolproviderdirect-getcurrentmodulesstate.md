---
title: "IDebugSymbolProviderDirect::GetCurrentModulesState | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetCurrentModulesState"
  - "IDebugSymbolProviderDirect::GetCurrentModulesState"
ms.assetid: a0c85318-5686-4eed-b213-21f2b9e681e6
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugSymbolProviderDirect::GetCurrentModulesState
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

기호 공급자의 구성원으로 있는 기호 그룹에 대 한 정보를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetCurrentModulesState(  
    DWORD*          pState,  
    unsigned long * count  
);  
```  
  
```c#  
int GetCurrentModulesState(  
    out uint pState,  
    out uint count  
);  
```  
  
#### 매개 변수  
 `pState`  
 \[out\] 기호 공급자 그룹의 상태입니다.  
  
 `count`  
 \[out\] 모듈에 있는 그룹의 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 모듈을 추가 하거나 기호 그룹에서 제거 될 때마다 상태를 변경 합니다.  따라서 기호 그룹 수정 했는지 여부를 검색 하려면이 메서드를 사용할 수 있습니다.  
  
## 참고 항목  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)