---
title: "TEXT_DOC_ATTR_2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TEXT_DOC_ATTR_2"
helpviewer_keywords: 
  - "TEXT_DOC_ATTR_2 열거형"
ms.assetid: 2333b33b-042b-4ac6-9ebe-e66f95f52f51
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# TEXT_DOC_ATTR_2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서의 특성을 설명합니다.  
  
## 구문  
  
```cpp#  
typedef DWORD TEXT_DOC_ATTR_2;  
const TEXT_DOC_ATTR_2 TEXT_DOC_ATTR_READONLY_2 = 0x00000001;  
```  
  
```c#  
public const uint TEXT_DOC_ATTR_READONLY_2 = 0x00000001;  
```  
  
## Members  
 TEXT\_DOC\_ATTR\_READONLY\_2  
 문서를 읽기 전용입니다.  
  
## 설명  
  
> [!NOTE]
>  이 값이 실제로 C\#에 대 한 어셈블리에서 정의 되지 않았습니다.  대신 소스 파일에 정의 복사 해야 합니다.  
  
 인수로 전달 되는 [onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md)