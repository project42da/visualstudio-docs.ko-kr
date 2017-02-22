---
title: "IDiaSession::put_loadAddress | Microsoft Docs"
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
  - "IDiaSession::put_loadAddress 메서드"
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSession::put_loadAddress
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

로드 주소에 해당 하는 실행 파일에 대 한 기호를이 기호 저장소에 설정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### 매개 변수  
 `NewVal`  
 \[in\] 실행 파일에 대 한 주소를 로드 합니다.  
  
## 설명  
 심볼 가상 주소 \(VA\) 속성 값이이 메서드를 사용 하 여 계산 됩니다.  0이 아닌 값이이 속성을 설정는 경우 가상 주소 계산 되지 않습니다.  
  
> [!NOTE]
>  사용자를 가져올 때이 메서드를 호출 해야 합니다는 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 전에 가상 속성에서 기호를 사용 하는 경우 개체를 사용 하 여 및 개체입니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)