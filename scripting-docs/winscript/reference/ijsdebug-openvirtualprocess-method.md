---
title: "IJsDebug::OpenVirtualProcess 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJSDebug.OpenVirtualProcess
apilocation: jscript9diag.dll
ms.assetid: 5612bf1b-a4e3-4eaf-ac5e-c2e1f147c395
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebug::OpenVirtualProcess 메서드
팩터리 메서드를 새 가상 프로세스 개체를 만드는 데 사용합니다.  
  
## 구문  
  
```  
 HRESULT OpenVirtualProcess(  
   DWORD processId,  
   UINT64 runtimeJsBaseAddress,  
   IJsDebugDataTarget *pDataTarget,  
   IJsDebugProcess **ppProcess  
);  
```  
  
#### 매개 변수  
 `processId`  
 \[in\] 디버거를 연결할 프로세스 Id입니다.  
  
 `runtimeJsBaseAddress`  
 \[in\] JavaScript 런타임에서 대상 프로세스로 로드되는 기준 주소입니다.  
  
 `pDataTarget`  
 \[in\] 프로세스 상태에 대해 쿼리하기 위한 디버거 제공 인터페이스입니다.  
  
 `ppProcess`  
 \[out\] 새 디버그 프로세스 개체  
  
## 반환 값  
  
## 설명  
 Jscript9diag 및 Jscript9와 일치하지 않으면 E\_JsDEBUG\_MISMATCHED\_RUNTIME를 반환합니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebug 인터페이스](../../winscript/reference/ijsdebug-interface.md)