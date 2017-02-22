---
title: "IDiaDataSource::get_lastError | Microsoft Docs"
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
  - "IDiaDataSource::get_lastError 메서드"
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaDataSource::get_lastError
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

마지막 로드 오류에 대 한 파일 이름을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_lastError (  
   BSTR* pRetVal  
);  
```  
  
#### 매개 변수  
 pRetVal  
 \[out\] 마지막 로드 오류와 관련 된.pdb 파일 이름이 들어 있는 문자열을 반환 합니다.  
  
## 반환 값  
 로드 작업에 의해 발생 한 마지막 오류 코드를 반환 합니다.  반환 `E_INVALIDARG` 경우는 `pRetVal` 매개 변수가 `NULL`.  
  
## 예제  
  
```cpp#  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## 참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)