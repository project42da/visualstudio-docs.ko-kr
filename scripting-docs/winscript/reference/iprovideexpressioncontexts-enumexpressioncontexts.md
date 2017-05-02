---
title: "IProvideExpressionContexts::EnumExpressionContexts | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IProvideExpressionContexts.EnumExpressionContexts
apilocation: jscript.dll
helpviewer_keywords: 
  - "IProvideExpressionContexts::EnumExpressionContexts"
ms.assetid: ec5f0065-00df-41e6-b480-4c04ba464872
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IProvideExpressionContexts::EnumExpressionContexts
이 구성 요소에 의해 알려져 식 컨텍스트는 열거자를 반환 합니다.  
  
## 구문  
  
```  
HRESULT EnumExpressionContexts(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### 매개 변수  
 `ppedec`  
 \[out\] 이 구성 요소에 의해 알려져 식 컨텍스트는 열거자입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 프로세스 디버그 관리자는이 메서드를 사용 하 여 특정된 스레드와 관련 된 모든 전역 식 컨텍스트를 찾을 수 있습니다.  
  
> [!NOTE]
>  이 메서드는 관심 있는 스레드 내에서 호출 됩니다.  구현자까지 현재 스레드를 식별 하 고 해당 하는 열거자를 반환 하는 것.  
  
## 참고 항목  
 [IProvideExpressionContexts 인터페이스](../../winscript/reference/iprovideexpressioncontexts-interface.md)