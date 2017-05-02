---
title: "IRemoteDebugApplication::EnumGlobalExpressionContexts | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplication.EnumGlobalExpressionContexts
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplication::EnumGlobalExpressionContexts"
ms.assetid: 61598a34-f409-42a2-810d-a9e92e2f4861
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplication::EnumGlobalExpressionContexts
이 응용 프로그램에서 실행 되는 모든 언어에 대 한 전역 식 컨텍스트를 열거 합니다.  
  
## 구문  
  
```  
HRESULT EnumGlobalExpressionContexts(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### 매개 변수  
 `ppedec`  
 \[out\] 이 응용 프로그램에서 실행 되는 모든 언어에 대 한 전역 식 컨텍스트를 나열 하는 열거자입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는이 응용 프로그램에서 실행 되는 모든 언어에 대 한 전역 식 컨텍스트를 열거 합니다.  
  
## 참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)