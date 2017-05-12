---
title: "IActiveScriptSiteDebug::GetDocumentContextFromPosition | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSiteDebug.GetDocumentContextFromPosition
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSiteDebug::GetDocumentContextFromPosition"
ms.assetid: ba5f7348-0107-4b12-b949-79a012476cf7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptSiteDebug::GetDocumentContextFromPosition
언어 엔진에서 위임 사용 `IDebugCodeContext::GetSourceContext`.  
  
## 구문  
  
```  
HRESULT GetDocumentContextFromPosition(  
   DWORD_PTR                dwSourceContext,  
   ULONG                    uCharacterOffset,  
   ULONG                    uNumChars,  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### 매개 변수  
 `dwSourceContext`  
 \[in\] 원본 콘텐츠를 제공한 `ParseScriptText` 또는 `AddScriptlet`.  
  
 `uCharacterOffset`  
 \[in\] 문자 스크립트릿 스크립트 블록의 시작에 상대적인 오프셋입니다.  
  
 `uNumChars`  
 \[in\] 이 컨텍스트에서 문자 수입니다.  
  
 `ppsc`  
 \[out\] 이 문자 위치 범위에 해당 하는 문서 컨텍스트.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 언어 엔진을 위임 하려면이 방법을 사용 `IDebugCodeContext::GetSourceContext`.  
  
## 참고 항목  
 [IActiveScriptSiteDebug 인터페이스](../../winscript/reference/iactivescriptsitedebug-interface.md)