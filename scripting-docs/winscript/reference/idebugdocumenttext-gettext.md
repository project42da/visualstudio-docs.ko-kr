---
title: "IDebugDocumentText::GetText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentText.GetText
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentText::GetText"
ms.assetid: 3c940a30-6c0f-4deb-aa4d-21a0bdef8461
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentText::GetText
문자 및 문자 위치 범위와 관련 된 문자 특성을 검색 합니다.  
  
## 구문  
  
```  
HRESULT GetText(  
   ULONG              cCharacterPosition,  
   WCHAR*             pcharText,  
   SOURCE_TEXT_ATTR*  pstaTextAttr,  
   ULONG*             pcNumChars,  
   ULONG              cMaxChars  
);  
```  
  
#### 매개 변수  
 `cCharacterPosition`  
 \[in\] 위치 문자 범위의 위치를 시작 합니다.  
  
 `pcharText`  
 \[in, out\] 문자 텍스트 버퍼입니다.  버퍼 보유할 수 있을 정도로 `cMaxChars` 자.  이 매개 변수가 NULL 이면 메서드는 문자를 반환 하지 않습니다.  
  
 `pstaTextAttr`  
 \[in, out\] 문자 특성 버퍼입니다.  버퍼 보유할 수 있을 정도로 `cMaxChars` 자.  이 매개 변수가 NULL 이면 메서드는 특성을 반환 하지 않습니다.  
  
 `pcNumChars`  
 \[in, out\] 문자\/특성 수를 반환 했습니다.  이 매개 변수는이 메서드를 호출 하기 전에 0으로 설정 되어야 합니다.  
  
 `cMaxChars`  
 \[in\] 문자 범위에 있는 문자 위치 수입니다.  또한 반환할 문자의 최대 수를 지정 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 문자 또는 문자 위치 범위와 관련 된 문자 특성 검색 합니다.  문자 위치 범위 문자 위치와 문자 개수 지정 됩니다.  
  
## 참고 항목  
 [IDebugDocumentText 인터페이스](../../winscript/reference/idebugdocumenttext-interface.md)   
 [SOURCE\_TEXT\_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)