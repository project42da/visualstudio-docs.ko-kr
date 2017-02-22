---
title: "JMC_CODE_SPEC | Microsoft Docs"
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
  - "JMC_CODE_SPEC"
helpviewer_keywords: 
  - "JMC_CODE_SPEC 구조"
ms.assetid: d89498f1-4234-46d9-b4e2-abbcbca5068a
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# JMC_CODE_SPEC
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조를 사용 하 여 JustMyCode 정보 모듈에 대 한 설정 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _JMC_CODE_SPEC {  
   BOOL fIsUserCode;  
   BSTR bstrModuleName;  
} JMC_CODE_SPEC;  
```  
  
```c#  
public struct JMC_CODE_SPEC {  
   public int    fIsUserCode;  
   public string bstrModuleName;  
};  
```  
  
## Members  
 fIsUserCode  
 0이 아닌 \(`TRUE`\) 모듈 사용자 코드;으로 간주 하는 경우 그렇지 않으면 0 \(`FALSE`\) 모듈 외부 코드로 간주 하 고 디버깅할 수 없는 경우.  
  
 bstrModuleName  
 의심 되는 모듈의 이름입니다.  
  
## 설명  
 이 구조와 같은 구조를 목록으로 전달 되는 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md) 메서드가 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)