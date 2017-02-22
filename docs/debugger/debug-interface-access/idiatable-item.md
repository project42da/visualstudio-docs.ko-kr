---
title: "IDiaTable::Item | Microsoft Docs"
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
  - "IDiaTable::Item 메서드"
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaTable::Item
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

테이블에 지정 된 항목에 대 한 참조를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Item (   
   DWORD      index,  
   IUnknown** element  
);  
```  
  
#### 매개 변수  
 `index`  
 \[in\] 인덱스 테이블 항목에 0 범위에서를 `count`\-1, 어디 `count` 반환 하는 있는 [IDiaTable::get\_Count](../../debugger/debug-interface-access/idiatable-get-count.md)메서드.  
  
 `element`  
 \[out\] 반환 된 `IUnknown` 지정 된 테이블 항목을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 테이블 개체의 컬렉션을 나타냅니다.  이러한 개체에 따라 element 매개 변수를 해당 인터페이스에 캐스팅할 수 있습니다.  예를 들어, 테이블에 포함 되어 있는 경우 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) element 매개 변수를 캐스팅 한 후 개체를 `IDiaSegment` 인터페이스입니다.  
  
 호출 하는 일반적인 방법입니다의 `QueryInterface` 메서드에서 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 인터페이스에 대 한 적절 한 열거자 인터페이스 및 열거자의 특정 메서드를 사용 하 여 테이블 내용에 액세스할 수.  참조는 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) 예를 들어에 대 한 인터페이스.  
  
## 참고 항목  
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [IDiaTable::get\_Count](../../debugger/debug-interface-access/idiatable-get-count.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)