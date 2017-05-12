---
title: "IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSiteDebugEx.OnCanNotJITScriptErrorDebug
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug"
ms.assetid: 83f81476-bf12-47f2-897d-1d37d21137d4
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug
호스트 관리자는 프로세스를 디버깅할 때 스크립트 런타임 오류에 대 한 시간에만 스크립트 디버거를 찾지를 알립니다.  
  
 호스트에서 디버거를 구현 하려면 처리 해야 [IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md).  사용자 작업을 기반으로 호스트는 디버거를 연결할 수 있습니다 및 반환, 또는 Onscripterrordebug는 디버거에서 시작 반환 `pfEnterDebugger` 매개 변수.  또한 프로세스 디버그 관리자에 의해 해석 될 수 없는 외부 디버거 경우에 런타임 오류에 대 한 알림을 받으려면이 인터페이스를 구현 해야 합니다.  
  
## 구문  
  
```  
HRESULT OnCanNotJITScriptErrorDebug(  
   IActiveScriptErrorDebug*  pErrorDebug  
   BOOL *pfCallOnScriptErrorWhenContinuing  
);  
```  
  
#### 매개 변수  
 `pErrorDebug`  
 \[in\] 발생 한 런타임 오류입니다.  
  
 `pfCallOnScriptErrorWhenContinuingt`  
 \[out\] 호출 여부 [IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md) 없이 디버깅을 계속 하려면 사용자를 결정 하는 경우.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 또한 알림을 받으려면이 인터페이스를 구현 해야 합니다.  
  
## 참고 항목  
 [IActiveScriptSiteDebugEx 인터페이스](../../winscript/reference/iactivescriptsitedebugex-interface.md)