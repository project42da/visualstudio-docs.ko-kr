---
title: "IDebugApplicationNode::Close | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplicationNode.Close
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplicationNode::Close"
ms.assetid: ea8db480-2344-4c7b-960c-4fa97fa6c1b7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplicationNode::Close
이 응용 프로그램에 대 한 모든 참조를 해제 하 고 비활성 상태가 됩니다.  
  
## 구문  
  
```  
HRESULT Close();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 일반적으로 응용 프로그램을 종료할 때 응용 프로그램의 소유자는이 메서드를 호출 합니다.  
  
## 참고 항목  
 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md)