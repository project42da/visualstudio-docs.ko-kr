---
title: "CvIsEnabled 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkers/CvIsEnabledEx"
  - "cvmarkers/CvIsEnabled"
helpviewer_keywords: 
  - "CvIsEnabled 메서드"
  - "CvIsEnabledEx 메서드"
ms.assetid: 2e4fea6d-758d-4150-8744-6102a1d58c1c
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# CvIsEnabled 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

세션에서 특정된 ETW 공급자를 활성화했는지 확인합니다.  
  
## 구문  
  
```  
HRESULT CvIsEnabled(  
   _In_ PCV_PROVIDER pProvider  
);  
HRESULT CvIsEnabledEx(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ CV_IMPORTANCE level,  
   _In_ int category  
);  
```  
  
#### 매개 변수  
 `category`  
 카테고리입니다.  
  
 `level`  
 중요도 수준입니다.  
  
 `pProvider`  
 유효한 공급자 개체입니다.  NULL 일 수 없습니다.  
  
## 반환 값  
 공급자가 현재 사용 하는 경우 S\_OK입니다.  공급자가 현재 사용 하지 않으면 S\_FALSE입니다.  오류가 있는 경우의 오류 코드입니다.  FAILED 매크로 사용 하 여 오류 조건을 확인 한 다음 S\_OK\/S\_FALSE 확인.  
  
## 요구 사항  
 **헤더:** cvmarkers.h  
  
## 참고 항목  
 [C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)