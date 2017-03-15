---
title: "IDiaInjectedSource::get_sourceCompression | Microsoft Docs"
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
  - "IDiaInjectedSource::get_sourceCompression 메서드"
ms.assetid: 854b142f-23a9-466c-bf7f-98e581d5abcd
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaInjectedSource::get_sourceCompression
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

표시기에 사용 되는 원본 압축을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_sourceCompression (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 표시기에 사용 되는 원본 압축을 반환 합니다.  값이 0 이면 원본 압축 없음 사용 되었음을 나타냅니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에 의해 반환 되는 값은 컴파일러에 사용 되는 특정입니다.  예를 들어, 컴파일러는 실행 길이 인코딩 또는 스타일 Huffman 압축을 사용할 수 있습니다.  
  
## 참고 항목  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)