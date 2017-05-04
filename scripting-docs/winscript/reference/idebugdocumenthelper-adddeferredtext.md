---
title: "IDebugDocumentHelper::AddDeferredText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.AddDeferredText
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::AddDeferredText"
ms.assetid: 9463cfb0-76cc-45ee-b32c-f37dce2b2e0e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::AddDeferredText
지정 된 텍스트를 사용할 수 있지만 문자를 제공 도우미를 알립니다.  
  
## 구문  
  
```  
HRESULT AddDeferredText(  
   ULONG  cChars,  
   DWORD  dwTextStartCookie  
);  
```  
  
#### 매개 변수  
 `cChars`  
 \[in\] 추가 \(유니코드\) 문자의 수입니다.  
  
 `dwTextStartCookie`  
 \[in\] 텍스트의 시작 위치를 나타내는 호스트 정의 된 쿠키입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|메서드가 실패 했습니다.|  
  
## 설명  
 이 메서드는 문자를 정확 하 게 알림과 크기 정보를 생성 하는 도우미를 하면서 필요할 때까지 추가 제공 하는 호스트가 있습니다.  `dwTextStartCookie` 매개 변수는 텍스트의 시작 위치를 나타내는 호스트에서 정의 하는 쿠키입니다.  후속 호출을 `IDebugDocumentText::GetText` 이 쿠키를 제공 해야 합니다.  예를 들어, DBCS 텍스트를 나타내는 호스트에서 쿠키 바이트 오프셋 수 있습니다.  
  
 이 가정 단일 호출을 `IDebugDocumentText::GetText` 문자를 여러 번 호출에서 얻을 수 있습니다 `AddDeferredText`.  두 번 이상 도우미 클래스는 또한 지연 된 문자의 동일한 범위에 대 한 요청할 수 있습니다.  
  
> [!NOTE]
>  호출 `AddDeferredText` 를 호출 하는 혼합할 수 없습니다 `AddUnicodeText` 또는 `AddDBCSText`.  이 경우 `E_FAIL` 이 반환 됩니다.  
  
## 참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)