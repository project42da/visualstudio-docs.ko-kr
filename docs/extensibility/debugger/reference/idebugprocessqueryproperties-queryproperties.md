---
title: "IDebugProcessQueryProperties::QueryProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugProcessQueryProperties::QueryProperties"
ms.assetid: 976a9962-b689-45bb-afb6-16b2c5dbc3b8
caps.latest.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 5
---
# IDebugProcessQueryProperties::QueryProperties
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 디버깅 프로세스는 지정 된 속성 값에 대 한 쿼리.  
  
## 구문  
  
```cpp#  
HRESULT QueryProperties(  
   ULONG                  celt,  
   PROCESS_PROPERTY_TYPE *rgdwPropTypes,  
   VARIANT               *rgtPropValues);  
```  
  
```c#  
int QueryProperties(  
   uint                       celt,  
   enum_PROCESS_PROPERTY_TYPE rgdwPropTypes,  
   out object[ ]              rgtPropValues);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 크기 속성 정 및 속성 값을 포함 하는 배열입니다.  
  
 `dwPropType`  
 \[in\] 쿼리 된 속성 정의 포함 하는 배열입니다.  가능한 값은 다음과 같습니다.  
  
-   PROCESS\_PROPERTY\_COMMAND\_LINE \= 1  
  
-   PROCESS\_PROPERTY\_CURRENT\_DIRECTORY \= 2  
  
-   PROCESS\_PROPERTY\_ENVIRONMENT\_VARIABLES \= 3  
  
 `pvarPropValue`  
 \[out\] 속성 값이 들어 있는 배열입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 거의 사용 됩니다.  
  
## 참고 항목  
 [IDebugProcessQueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties.md)