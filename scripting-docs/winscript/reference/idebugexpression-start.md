---
title: "IDebugExpression::Start | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugExpression.Start
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugExpression::Start"
ms.assetid: a7af3470-62b5-40f0-987d-63b6b22538b3
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugExpression::Start
식의 평가 시작합니다.  
  
## 구문  
  
```  
HRESULT Start(  
   IDebugExpressionCallBack*  pdecb  
);  
```  
  
#### 매개 변수  
 `pdecb`  
 \[in\] 식 평가 완료 되 면 나타내는 콜백 합니다.  이 매개 변수가 `NULL`이벤트가 발생 하지 않습니다, 식 상태를 사용 하 여 클라이언트를 폴링하여 `QueryIsComplete`.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 식 계산 하는 시작합니다.  
  
## 참고 항목  
 [IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)   
 [IDebugExpression 인터페이스](../../winscript/reference/idebugexpression-interface.md)