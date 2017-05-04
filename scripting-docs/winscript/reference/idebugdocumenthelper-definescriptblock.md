---
title: "IDebugDocumentHelper::DefineScriptBlock | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.DefineScriptBlock
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::DefineScriptBlock"
ms.assetid: e4120377-f04f-44b1-950b-2beba06c9c12
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::DefineScriptBlock
도우미에 특정 문자 범위를 지정 된 스크립트 엔진에 의해 처리 되는 스크립트 블록입니다.  
  
## 구문  
  
```  
HRESULT DefineScriptBlock(  
   ULONG           ulCharOffset,  
   ULONG           cChars,  
   IActiveScript*  pas,  
   BOOL            fScriptlet,  
   DWORD_PTR*      pdwSourceContext  
);  
```  
  
#### 매개 변수  
 `ulCharOffset`  
 \[in\] 스크립트 블록의 시작 위치입니다.  
  
 `cChars`  
 \[in\] 스크립트 블록의 문자 수입니다.  
  
 `pas`  
 \[in\] 이 스크립트 블록에 스크립트 엔진입니다.  
  
 `fScriptlet`  
 \[in\] 스크립트 블록은 스크립트릿 인지 여부를 나타내는 플래그입니다.  
  
 `pdwSourceContext`  
 \[out\] 소스 스크립트 블록에 대 한 컨텍스트입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 포함 된 스크립트 블록을 문서에 포함 될 때 스마트 호스트는이 메서드를 사용할 수 있습니다.  언어 엔진 다른 언어에 포함 된 스크립트 코드를 포함 하는 경우이 메서드를 사용할 수 있습니다.  
  
 스크립트 엔진이 모든 구문 색상 표시 및 코드 컨텍스트 조회 스크립트 블록에서에 대 한 책임이 있습니다.  
  
 `DefineScriptBlock` 텍스트를 추가한 후 메서드를 호출 해야 \(예를 들어, 사용 하는 `IDebugDocumentHelper::AddDBCSText` 메서드\) 하지만 이전 스크립트 블록 구문 분석 된 \(예를 들어, 사용 하는 `IActiveScriptParse ::ParseScriptText` 메서드\).  
  
## 참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)