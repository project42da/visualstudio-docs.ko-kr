---
title: "IActiveScriptDebug::EnumCodeContextsOfPosition | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptDebug.EnumCodeContextsOfPosition
apilocation: jscript.dll
helpviewer_keywords: 
  - "IActiveScriptDebug::EnumCodeContextsOfPosition"
ms.assetid: 19f44420-bcc8-4c10-8c38-378d96044117
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptDebug::EnumCodeContextsOfPosition
스마트 호스트에서 사용 되는 위임 하는 `IDebugDocumentContext::EnumCodeContexts` 메서드.  
  
## 구문  
  
```  
HRESULT EnumCodeContextsOfPosition(  
   DWORD_PTR                 dwSourceContext,  
   ULONG                     uCharacterOffset,  
   ULONG                     uNumChars,  
   IEnumDebugCodeContexts**  ppescc  
);  
```  
  
#### 매개 변수  
 `dwSourceContext`  
 \[in\] 원본 컨텍스트를 제공 하는 `IActiveScriptParse::ParseScriptText` 또는 `IActiveScriptParse::AddScriptlet`.  
  
 `uCharacterOffset`  
 \[in\] 문자를 기준으로 스크립트 텍스트의 시작 오프셋입니다.  
  
 `uNumChars`  
 \[in\] 이 컨텍스트에서 문자 수입니다.  
  
 `ppescc`  
 \[out\] 열거자는 코드 컨텍스트에서 지정 된 범위입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 스마트 호스트가이 메서드 사용 하 여 위임 하는 `IDebugDocumentContext::EnumCodeContexts` 메서드.  
  
## 참고 항목  
 [IActiveScriptDebug 인터페이스](../../winscript/reference/iactivescriptdebug-interface.md)   
 [IDebugDocumentContext::EnumCodeContexts](../../winscript/reference/idebugdocumentcontext-enumcodecontexts.md)