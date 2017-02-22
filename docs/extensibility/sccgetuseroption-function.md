---
title: "SccGetUserOption 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccGetUserOption"
helpviewer_keywords: 
  - "SccGetUserOption 함수"
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# SccGetUserOption 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 다양 한 사용자 고유의 옵션을 가져옵니다.  
  
## 구문  
  
```cpp  
SCCRTN SccGetUserOption(  
   LPVOID pContext,  
   LONG nOption,  
   LPLONG lpVal  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nOption  
 \[in\] \(사용 가능한 옵션에 대 한 설명 참조\)를 검색 하는 옵션입니다.  
  
 lpVal  
 \[out\] 옵션과 관련 된 값입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|옵션 검색 되었습니다.|  
|SCC\_E\_OPNOTSUPPORTED|옵션은 지원 되지 않습니다.|  
|SCC\_E\_NONSPECIFICERROR|오류가 발생 했습니다.|  
  
## 설명  
 다음 옵션은이 명령에서 지원 됩니다.  
  
|사용자 옵션|설명|  
|------------|--------|  
|`SCC_USEROPT_CHECKOUT_LOCALVER`|사용자가 파일의 로컬 버전 체크 아웃 하는지 여부를 결정 합니다.`lpVal` 할당 된 `SCC_USEROPT_COLV_YES` \(사용자가 로컬 파일을 체크 아웃\) 또는 `SCC_USEROPT_COLV_NO`합니다.|  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [오류 코드](../extensibility/error-codes.md)