---
title: "IDebugDocumentTextExternalAuthor 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugDocumentTextExternalAuthor 인터페이스"
ms.assetid: 0b04de1b-f922-4526-af4e-c0af2b7c1ce4
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentTextExternalAuthor 인터페이스
외부 편집기를 소스 파일이 변경 되 면 문서를 알림으로써 파일 기반 디버거 문서를 안전 하 게 편집할 수 있습니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugDocumentTextExternalAuthor` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugDocumentTextExternalAuthor::GetPathName](../../winscript/reference/idebugdocumenttextexternalauthor-getpathname.md)|문서의 전체 경로 파일 이름을 반환합니다.|  
|[IDebugDocumentTextExternalAuthor::GetFileName](../../winscript/reference/idebugdocumenttextexternalauthor-getfilename.md)|경로 정보 없이 문서의 이름을 반환합니다.|  
|[IDebugDocumentTextExternalAuthor::NotifyChanged](../../winscript/reference/idebugdocumenttextexternalauthor-notifychanged.md)|문서 원본 변경 되었음을 호스트에 알립니다.|