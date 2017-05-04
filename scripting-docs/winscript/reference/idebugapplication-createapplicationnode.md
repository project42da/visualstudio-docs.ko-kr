---
title: "IDebugApplication::CreateApplicationNode | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.CreateApplicationNode
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::CreateApplicationNode"
ms.assetid: 1a1414f6-df14-4c56-b39a-8384cf16174a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::CreateApplicationNode
문서를 특정 공급자와 관련 된 새 응용 프로그램 노드를 만듭니다.  
  
## 구문  
  
```  
HRESULT CreateApplicationNode(  
   IDebugApplicationNode**  ppdanNew  
);  
```  
  
#### 매개 변수  
 `ppdanNew`  
 \[out\] 이 문서의 공급자와 관련 된 응용 프로그램 노드입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 부모 노드에 연결 될 때까지 새 응용 프로그램 노드가 표시 되지 않습니다.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)