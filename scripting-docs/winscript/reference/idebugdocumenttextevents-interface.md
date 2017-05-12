---
title: "IDebugDocumentTextEvents 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugDocumentTextEvents 인터페이스"
ms.assetid: 341b20fd-994c-4030-a06b-6c66ad38c35d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentTextEvents 인터페이스
연결 된 텍스트 문서의 변경 내용을 나타내는 이벤트를 제공 합니다.  
  
> [!NOTE]
>  화재 이벤트에서이 인터페이스는 때 문서 텍스트를 변경 합니다.  이벤트 처리기 사용 하 여 새 텍스트를 검색할 수 있는 `IDebugDocumentText` 인터페이스.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugDocumentTextEvents` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugDocumentTextEvents::onDestroy](../../winscript/reference/idebugdocumenttextevents-ondestroy.md)|기본 문서 소멸 된 및 더 이상 유효 하지 나타냅니다.|  
|[IDebugDocumentTextEvents::onInsertText](../../winscript/reference/idebugdocumenttextevents-oninserttext.md)|새 텍스트 문서에 추가 되었음을 나타냅니다.|  
|[IDebugDocumentTextEvents::onRemoveText](../../winscript/reference/idebugdocumenttextevents-onremovetext.md)|텍스트 문서에서 제거 되었음을 나타냅니다.|  
|[IDebugDocumentTextEvents::onReplaceText](../../winscript/reference/idebugdocumenttextevents-onreplacetext.md)|텍스트를 교체한 적이 있는지를 나타냅니다.|  
|[IDebugDocumentTextEvents::onUpdateTextAttributes](../../winscript/reference/idebugdocumenttextevents-onupdatetextattributes.md)|기본 문자 위치 범위와 관련 된 텍스트 속성 변경 되었음을 나타냅니다.|  
|[IDebugDocumentTextEvents::onUpdateDocumentAttributes](../../winscript/reference/idebugdocumenttextevents-onupdatedocumentattributes.md)|문서 속성을 변경 했음을 나타냅니다.|