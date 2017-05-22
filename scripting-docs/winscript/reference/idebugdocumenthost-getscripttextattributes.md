---
title: "IDebugDocumentHost::GetScriptTextAttributes | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHost.GetScriptTextAttributes
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugDocumentHost::GetScriptTextAttributes"
ms.assetid: fe459d0d-937f-4176-be81-99d5cca121a1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHost::GetScriptTextAttributes
문서의 텍스트 블록에 대 한 텍스트 특성을 반환합니다.  
  
## 구문  
  
```  
HRESULT GetScriptTextAttributes(  
   LPCOLESTR          pstrCode,  
   ULONG              uNumCodeChars,  
   LPCOLESTR          pstrDelimiter,  
   DWORD              dwFlags,  
   SOURCE_TEXT_ATTR*  pattr  
);  
```  
  
#### 매개 변수  
 `pstrCode`  
 \[in\] 스크립트 블록 텍스트입니다.  이 문자열이 null 종료 될 필요가 없습니다.  
  
 `uNumCodeChars`  
 \[in\] 스크립트 블록 텍스트의 문자 수입니다.  
  
 `pstrDelimiter`  
 \[in\] 주소 끝의 스크립트 블록 구분 기호입니다.  때 `pstrCode` 구문 분석 스크립트 블록의 끝을 검색 합니다 \('\) 작은따옴표 2 개 같은 텍스트 스트림에서 호스트 일반적으로 구분 기호를 사용 합니다.  호스트 허용 일부 조건부 기본 전처리를 제공 하는 스크립팅 엔진 사용 구분이 매개이 변수를 지정 \(예를 들어, 작은 따옴표 \['\]에 두 개의 작은따옴표를 구분 기호로 사용 대체\).  정확 하 게 하는 방법 \(및 if\) 스크립팅 엔진 사용 스크립팅 엔진에서이 정보에 따라 다릅니다.  호스트 스크립트 블록의 끝을 표시 하는 구분 기호로 사용 하지 않은 경우이 매개 변수는 NULL로 설정 합니다.  
  
 `dwFlags`  
 \[in\] 스크립트 블록에 연결 된 플래그입니다.  이러한 값의 조합을 사용할 수 있습니다.  
  
|상수|값|설명|  
|--------|-------|--------|  
|GETATTRTYPE\_DEPSCAN|0x0001|도트 연산자 및 식별자와 SOURCETEXT\_ATTR\_IDENTIFIER 및 SOURCETEXT\_ATTR\_MEMBERLOOKUP 플래그를 각각 식별할 수를 나타냅니다.|  
|GETATTRFLAG\_THIS|0x0100|현재 개체에 대 한 식별자 SOURCETEXT\_ATTR\_THIS 플래그와 함께 식별을 나타냅니다.|  
|GETATTRFLAG\_HUMANTEXT|0x8000|나타내는 문자열 내용 및 메모 텍스트는 SOURCETEXT\_ATTR\_HUMANTEXT 플래그와 함께 식별 되어야 합니다.|  
  
 `pattr`  
 \[in, out\] 반환 된 특성을 포함 하는 버퍼입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|호스트는 기본 특성을 사용 합니다.|  
  
## 설명  
 이 메서드는 임의의 블록 문서 텍스트의 텍스트 특성을 반환합니다.  반환할 호스트에 대 한 적합 `E_NOTIMPL`, 경우에 기본 특성이 사용 됩니다.  
  
## 참고 항목  
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)   
 [SOURCE\_TEXT\_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)