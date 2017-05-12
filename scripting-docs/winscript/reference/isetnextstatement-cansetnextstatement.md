---
title: "ISetNextStatement::CanSetNextStatement | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ISetNextStatement.CanSetNextStatement
apilocation: scrobj.dll
ms.assetid: e2a54634-31ec-4d16-84e8-2b123845d876
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# ISetNextStatement::CanSetNextStatement
이 메서드가 지정 된 위치에 다음 문을 실행할 코드를 결정 하는 실행 위치를 설정할 수 있는지 여부를 결정 합니다.  
  
## 구문  
  
```  
HRESULT CanSetNextStatement(  
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
|`S_OK`|다음 문은 지정한 코드 컨텍스트를 업데이트할 수 있습니다.|  
|`S_FALSE`|다음 문은 지정한 코드 컨텍스트를 업데이트할 수 없습니다.|  
  
## 설명  
  
## 참고 항목  
 [ISetNextStatement 인터페이스](../../winscript/reference/isetnextstatement-interface.md)