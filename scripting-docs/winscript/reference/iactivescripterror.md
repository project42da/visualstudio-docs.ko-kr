---
title: "IActiveScriptError | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptError 인터페이스"
ms.assetid: c8e0288d-38ff-4145-a7e3-f8cdfb72eefe
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptError
이 인터페이스를 구현 하는 개체에 전달 되는 [IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md) 메서드를 스크립트 엔진에서 처리 되지 않은 오류가 발견 될 때마다.  다음 호스트에서 발생 한 오류에 대 한 정보를 얻으려면이 개체 메서드를 호출 합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptError::GetExceptionInfo](../../winscript/reference/iactivescripterror-getexceptioninfo.md)|오류에 대 한 정보를 검색합니다.|  
|[IActiveScriptError::GetSourcePosition](../../winscript/reference/iactivescripterror-getsourceposition.md)|소스 코드에서 오류가 발생 한 위치 위치를 검색 합니다.|  
|[IActiveScriptError::GetSourceLineText](../../winscript/reference/iactivescripterror-getsourcelinetext.md)|줄에 오류가 발생 한 위치는 소스 파일을 검색 합니다.|  
  
## 참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)