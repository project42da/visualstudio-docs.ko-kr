---
title: "IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaPropertyStorage::ReadPropertyNames"
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaPropertyStorage::ReadPropertyNames
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

검색 문자열 이름에 대 한 해당 속성 식별자를 지정 합니다.  
  
## 구문  
  
```cpp  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### 매개 변수  
 `cpropid`  
 \[in\] 속성 id 수 `rgpropid`.  
  
 `rgpropid`  
 \[in\] 이름을 얻을 수에 대 한 속성 id의 배열 \(`PROPID` 로 Wtypes.h에 정의 되어 있는 `ULONG`\).  
  
 `rglpwstrName`  
 \[in, out\] 지정한 속성 id에 대 한 속성 이름의 배열입니다.  배열 속성 이름 요청된 수를 보유할 미리 할당 된 이어야 하며 적어도 채 수 있어야 `cpropid``BSTR` 문자열입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 반환 된 속성 이름을 해제 해야 \(전화는 `SysFreeString` 함수\)는 더 이상 필요할 때.  
  
## 참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)