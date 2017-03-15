---
title: "IDiaPropertyStorage::ReadMultiple | Microsoft Docs"
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
  - "IDiaPropertyStorage::ReadMultiple"
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaPropertyStorage::ReadMultiple
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 현재 속성 집합에서 속성을 읽습니다.  
  
## 구문  
  
```cpp#  
HRESULT ReadMultiple(   
   ULONG          cpspec,  
   PROPSPEC const rgpspec,  
   PROPVARIANT    rgvar  
);  
```  
  
#### 매개 변수  
 `cpspec`  
 \[in\] Count에 지정 된 속성은 `rgpspec` 배열입니다.  0 이면 메서드가 속성이 반환 하지만 반환 하지 `S_OK` 로 성공 코드입니다.  
  
 `rgpspec`  
 \[in\] 읽을 수 있도록 속성의 배열입니다.  속성 ID 또는 선택적 문자열 이름 속성을 지정할 수 있습니다.  특정 순서로 배열에서 속성을 지정할 필요가 없습니다.  배열에 간단한 속성에 대 한 중복 된 속성 값의 중복 속성을 포함할 수 있습니다.  비\-간단 등록 정보 열기를 다시 하려고 할 때 액세스 거부 반환 해야 합니다.  배열 속성 Id와 Id 문자열을 함께 포함 될 수 있습니다.  이 배열에는 적어도 있어야 합니다 `cpspec` 속성 값을 표시 합니다.  
  
 `rgvar`  
 \[in, out\] 배열 `PROPVARIANT` 구조 \(Microsoft.VisualStudio.OLE.Interop 네임 스페이스에\) 데이터를 사용 하 여 각 속성의 값을 입력할 수 있습니다.  배열에는 `cpspec` 요소의 크기입니다.  호출자는 배열 값을 초기화할 필요가 없습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 속성 중 하나 이상이 없는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 속성 찾을 수 없습니다 하는 경우, 해당 항목에는 `rgvar` 배열에 포함 된 `VARIANT` 형식으로 `VT_EMPTY`.  
  
## 참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)