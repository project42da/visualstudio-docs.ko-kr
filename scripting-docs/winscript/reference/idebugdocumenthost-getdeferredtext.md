---
title: "IDebugDocumentHost::GetDeferredText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHost.GetDeferredText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugDocumentHost::GetDeferredText"
ms.assetid: 527da666-fef5-4db3-a319-e68d466a7721
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHost::GetDeferredText
사용 하 여 추가 된 문자의 범위를 반환 된 `IDebugDocumentHelper::AddDeferredText` 메서드는 원본 호스트 문서에.  
  
## 구문  
  
```  
HRESULT GetDeferredText(  
   DWORD              dwTextStartCookie,  
   WCHAR*             pcharText,  
   SOURCE_TEXT_ATTR*  pstaTextAttr,  
   ULONG*             pcNumChars,  
   ULONG              cMaxChars  
);  
```  
  
#### 매개 변수  
 `dwTextStartCookie`  
 \[in\] 텍스트의 시작 위치를 나타내는 호스트 정의 된 쿠키입니다.  
  
 `pcharText`  
 \[in, out\] 문자 텍스트 버퍼입니다.  이 매개 변수가 있으면이 메서드는 문자 반환 하지 않습니다 `NULL`.  
  
 `pstaTextAttr`  
 \[in, out\] 문자 특성 버퍼입니다.  이 매개 변수가 없으면이 메서드는 특성 반환 하지 않습니다 `NULL`.  
  
 `pcNumChars`  
 \[in, out\] 반환 되는 문자\/특성의 실제 번호를 나타냅니다.  이 매개 변수는이 메서드를 호출 하기 전에 0으로 설정 되어야 합니다.  
  
 `cMaxChars`  
 \[in\] 최대 수의 문자를 반환 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|메서드가 구현되지 않았습니다.|  
  
## 설명  
 이 메서드는 반환 `E_NOTIMPL`, 호스트를 호출 하지 않은 경우 `IDebugDocumentHelper::AddDeferredText`.  
  
> [!NOTE]
>  이 메서드는 원래 문서에서 텍스트를 반환합니다.  호스트 편집 또는 변경 문서를 추적 하지 않습니다.  
  
## 참고 항목  
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)   
 [IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [SOURCE\_TEXT\_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)