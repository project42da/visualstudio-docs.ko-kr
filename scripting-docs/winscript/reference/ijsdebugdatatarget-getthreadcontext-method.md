---
title: "IJsDebugDataTarget::GetThreadContext 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.GetThreadContext
apilocation: jscript9diag.dll
ms.assetid: faf2a689-6c49-4a7d-b5a6-2b323e2257a7
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::GetThreadContext 메서드
스레드가 제공하는 컨텍스트를 검색합니다.  
  
## 구문  
  
```  
HRESULT GetThreadContext(  
   DWORD threadId,  
   ULONG32 contextFlags,  
   ULONG32 contextSize,  
   void *pContext  
);  
```  
  
#### 매개 변수  
 `threadId`  
 \[in\] 대상 프로세스에서 실행되는 스레드입니다.  
  
 `contextFlags`  
 \[in\] 컨텍스트 플래그를 지정합니다.  이것은 CONTEXT의 ContextFlags 필드와 동일합니다\(자세한 내용은 winnt.h에서 CONTEXT\_ALL 검색\).  
  
 `contextSize`  
 \[in\] pContext가 지정한 버퍼의 크기입니다.  
  
 `pContext`  
 \[out\] 플랫폼별 컨텍스트 구조체를 pContext 지정한 버퍼로 받습니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)