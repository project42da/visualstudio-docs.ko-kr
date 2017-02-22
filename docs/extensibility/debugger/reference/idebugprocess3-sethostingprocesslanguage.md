---
title: "IDebugProcess3::SetHostingProcessLanguage | Microsoft Docs"
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
  - "IDebugProcess3::SetHostingProcessLanguage"
helpviewer_keywords: 
  - "IDebugProcess3::SetHostingProcessLanguage"
ms.assetid: e42f33ed-f29c-4e45-92ce-ab504b72d77c
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcess3::SetHostingProcessLanguage
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 프로세스에서 호스팅되는 언어를 설정 합니다.  이 언어는 적절 한 식 계산기를 로드 하는 디버그 엔진 \(DE\) 사용할 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT SetHostingProcessLanguage(  
   REFGUID guidLang  
);  
```  
  
```c#  
int SetHostingProcessLanguage(  
   ref Guid guidLang  
);  
```  
  
#### 매개 변수  
 `guidLang`  
 \[in\] `GUID` DE를 사용 해야 하는 언어입니다.  지정한 `GUID_NULL` \(c \+ \+\) 또는 `Guid.Empty` \(C\#를 사용 하는 기본 언어를 DE\).  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 [GetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-gethostingprocesslanguage.md)현재 언어 설정을 검색을 사용할 수 있습니다.  
  
## 참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [GetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-gethostingprocesslanguage.md)