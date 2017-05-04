---
title: "IDebugApplicationNode100 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationNode100 인터페이스"
ms.assetid: 43966d4e-5f89-4a04-a08d-782347d00c2d
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IDebugApplicationNode100 인터페이스
`IDebugApplicationNode100` 인터페이스 기능을 확장 하는 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md).  구현에서 Queryinterface를 호출 하 여이 인터페이스의 인스턴스를 가져올 수 있습니다 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md).  
  
> [!IMPORTANT]
>  PDM v 10.0이 고 큰이 인터페이스를 구현 합니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 메서드  
 `IDebugApplicationNode100` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)|지정 된 필터에 의해 숨겨진 된 텍스트 문서를 가져옵니다.|  
|[IDebugApplicationNode100::QueryIsChildNode](../../winscript/reference/idebugapplicationnode100-queryischildnode.md)|지정 된 문서를이 노드의 자식 노드 중 하나에 속하는지 여부를 결정 합니다.|  
|[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)|필터에서 특정 설정 [IDebugApplicationNodeEvents 인터페이스](../../winscript/reference/idebugapplicationnodeevents-interface.md) 구현.  이 스크립트 디버거를 노드 작성 또는 삭제할 때 이벤트는 PDM을 더 이상 보낼 수 응용 프로그램 컴파일러에서 생성 된 자식 노드를 필터링 할 수 없습니다.  기본적으로 모든 노드에 전송 됩니다.|