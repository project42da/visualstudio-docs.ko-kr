---
title: "IActiveScriptSiteDebug::OnScriptErrorDebug | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSiteDebug.OnScriptErrorDebug
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSiteDebug::OnScriptErrorDebug"
ms.assetid: 87f201da-36eb-49a2-b000-e1e1e8c4cdb7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptSiteDebug::OnScriptErrorDebug
스마트 호스트를 런타임 오류를 처리 하는 방법을 결정할 수 있습니다.  
  
## 구문  
  
```  
HRESULT OnScriptErrorDebug(  
   IActiveScriptErrorDebug*  pErrorDebug,  
   BOOL*                     pfEnterDebugger,  
   BOOL*                     pfCallOnScriptErrorWhenContinuing  
);  
```  
  
#### 매개 변수  
 `pErrorDebug`  
 \[in\] 발생 한 런타임 오류  
  
 `pfEnterDebugger`  
 \[out\] JIT 디버깅을 디버거에 오류를 전달 하는지 여부를 나타내는 플래그입니다.  
  
 `pfCallOnScriptErrorWhenContinuing`  
 \[out\] 호출 하는지 여부를 나타내는 플래그 `IActiveScriptSite::OnScriptError` 때 사용자를 결정 하지 않고 디버깅을 계속 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값은 포함 되지만 다음 표에 있는 값으로 제한 되지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 스마트 호스트는이 메서드는 런타임 오류를 처리 하는 방법을 결정 합니다 수 있습니다.  
  
## 참고 항목  
 [IActiveScriptSiteDebug 인터페이스](../../winscript/reference/iactivescriptsitedebug-interface.md)