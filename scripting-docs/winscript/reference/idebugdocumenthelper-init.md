---
title: "IDebugDocumentHelper::Init | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.Init
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::Init"
ms.assetid: 1dd5a01f-0779-4109-8c6c-f16f5a3835bf
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::Init
`Init` 메서드는 디버그 문서 도우미 이름과 초기 특성을 초기화 합니다.  
  
## 구문  
  
```  
HRESULT Init(  
   IDebugApplication*  pda,  
   LPCOLESTR           pszShortName,  
   LPCOLESTR           pszLongName,  
   TEXT_DOC_ATTR       docAttr  
);  
```  
  
#### 매개 변수  
 `pda`  
 \[in\] 이 문서와 관련 된 디버그 응용 프로그램입니다.  
  
 `pszShortName`  
 \[in\] 짧은 문서 이름이 포함 된 null로 끝나는 문자열입니다.  
  
 `pszLongName`  
 \[in\] 긴 문서 이름이 포함 된 null로 끝나는 문자열입니다.  
  
 `docAttr`  
 \[in\] 텍스트 문서의 속성을 지정합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 디버그 문서 도우미 이름과 초기 특성을 초기화합니다.  
  
 이 문서 트리까지 나타나지 `IDebugDocumentHelper::Attach` 라고 합니다.  
  
## 참고 항목  
 [IDebugDocumentHelper::Attach](../../winscript/reference/idebugdocumenthelper-attach.md)   
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [TEXT\_DOC\_ATTR 상수](../../winscript/reference/text-doc-attr-constants.md)