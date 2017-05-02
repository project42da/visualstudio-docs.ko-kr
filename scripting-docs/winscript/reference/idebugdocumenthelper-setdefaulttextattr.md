---
title: "IDebugDocumentHelper::SetDefaultTextAttr | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.SetDefaultTextAttr
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::SetDefaultTextAttr"
ms.assetid: 019a4191-0019-4376-bf70-89b33e7369de
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::SetDefaultTextAttr
스크립트 블록에 있지 않은 텍스트를 사용 하는 기본 특성을 설정 합니다.  
  
## 구문  
  
```  
HRESULT SetDefaultTextAttr(  
   SOURCE_TEXT_ATTR  staTextAttr  
);  
```  
  
#### 매개 변수  
 `staTextAttr`  
 기본 소스 텍스트 속성  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 기본 특성에서이 메서드를 변경 하지 않는 한 텍스트 스크립트 블록 외부에 대 한 기본 특성 SOURCETEXT\_ATTR\_NONSOURCE입니다.  사용자 인터페이스 외부 스크립트 블록 읽기 전용 텍스트를 표시 하려면이 정보를 사용할 수 있습니다.  
  
## 참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [SOURCE\_TEXT\_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)