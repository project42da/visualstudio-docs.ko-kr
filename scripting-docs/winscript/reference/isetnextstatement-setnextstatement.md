---
title: "ISetNextStatement::SetNextStatement | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ISetNextStatement.SetNextStatement
apilocation: scrobj.dll
ms.assetid: c5534f3b-39a5-4466-b8fc-69b717c6eee9
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# ISetNextStatement::SetNextStatement
이 메서드는 스크립트 인터프리터 실행할 수 있는 다음 코드 컨텍스트를 업데이트 합니다.  
  
## 구문  
  
```  
HRESULT SetNextStatement(  
   IDebugStackFrame*  pStackFrame,  
   IDebugCodeContext*  pCodeContext  
)  
```  
  
#### 매개 변수  
 `pStackFrame`  
 \[in\] 스택 프레임 개체에 대 한 포인터입니다.  
  
 `pCodeContext`  
 \[in\] 코드 컨텍스트 개체에 대 한 포인터입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [ISetNextStatement 인터페이스](../../winscript/reference/isetnextstatement-interface.md)