---
title: "IRemoteDebugApplicationThreadEx:EnumGlobalContexts | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplicationThreadEx:EnumGlobalContexts
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IRemoteDebugApplicationThreadEx:EnumGlobalContexts"
ms.assetid: a6c0bc3f-4afc-41e1-b734-06e252c5b171
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IRemoteDebugApplicationThreadEx:EnumGlobalContexts
이 스레드에서 실행 되는 모든 언어에 대 한 전역 식 컨텍스트를 열거 합니다.  
  
## 구문  
  
```  
HRESULT EnumGlobalExpressionContexts(  
   IEnumDebugExpressionContexts**  ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 이 스레드에서 실행 되는 모든 언어에 대 한 전역 식 컨텍스트를 나열 하는 열거자입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명