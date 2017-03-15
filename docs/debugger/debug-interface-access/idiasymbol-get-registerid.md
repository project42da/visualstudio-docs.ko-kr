---
title: "IDiaSymbol::get_registerId | Microsoft Docs"
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
  - "IDiaSymbol::get_registerId 메서드"
ms.assetid: f881e793-eb9e-48dc-a847-dd61d77174fc
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_registerId
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

레지스터 지정자의 위치를 검색 하면는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 설정 되어 `LocIsEnregistered`.  
  
## 구문  
  
```cpp#  
HRESULT get_registerId (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 레지스터 지정자의 위치를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 설명  
 기호는 레지스터를 기준으로,이 경우 경우 심볼의 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 로 설정 됩니다 `LocIsRegRel`, 사용의 `get_registerId` 메서드를 차례로 호출 하 여는 [IDiaSymbol::get\_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md) 메서드 기호 되어 있는 레지스터에서의 오프셋을 가져올 수 있습니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)