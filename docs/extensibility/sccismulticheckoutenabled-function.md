---
title: "SccIsMultiCheckoutEnabled 함수 | Microsoft Docs"
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
  - "SccIsMultiCheckoutEnabled"
helpviewer_keywords: 
  - "SccIsMultiCheckoutEnabled 함수"
ms.assetid: 6721639d-e475-4766-81b5-ee40a280fc70
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# SccIsMultiCheckoutEnabled 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어 플러그 인 파일에 여러 체크 아웃을 허용 하는지 여부를 확인 합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccIsMultiCheckoutEnabled(  
   LPVOID pContext,  
   LPBOOL pbMultiCheckout  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 pbMultiCheckout  
 \[out\] 이 프로젝트 \(여러 체크 아웃 지원 되는 0이 아닌 의미\)에 대해 여러 체크 아웃 사용 되는지 여부를 지정 합니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|확인에 성공 했습니다.|  
|SCC\_E\_NONSPECIFICERROR<br /><br /> SCC\_E\_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 IDE를 사용 하는 경우 파일이 체크 아웃할 수 동시에 둘 이상의 사용자가 확인 하는 두 가지 검사 합니다. 첫째, 소스 제어 시스템 여러 체크 아웃을 지원 해야 합니다. 소스 제어 플러그 인을 지정 하 여 초기화 하는 동안이 기능에 지정할 수는 `SCC_CAP_MULTICHECKOUT`합니다. 그런 후 확인을 두 번째 IDE 현재 프로젝트에 여러 체크 아웃 지원 여부를 확인 하려면이 함수를 호출 합니다. 플러그 인에서 성공 반환 코드 및 설정 하는 여러 체크 아웃 선택한 프로젝트를 지원 하는 경우 `pbMultiCheckout` 에 0이 아닌 \(`TRUE`\) 또는 `FALSE`합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)