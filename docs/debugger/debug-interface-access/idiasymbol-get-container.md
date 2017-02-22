---
title: "IDiaSymbol::get_container | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSymbol::get_container 메서드"
ms.assetid: 24e832eb-80b3-484c-a41b-11477ec9de99
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_container
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 함수 기호가 부모 컨테이너를 나타내는 기호에 대 한 포인터를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT get_container(  
   IDiaSymbol **pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 에 대 한 포인터를 반환 된 `IDiaSymbol` 이 기호에는 컨테이너에 대 한 정보가 포함 된.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 S\_FALSE 또는 오류 코드를 반환합니다.  
  
> [!NOTE]
>  S\_FALSE 반환 값이 속성에 사용할 수 없습니다 의미 합니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)