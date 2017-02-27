---
title: "SccDirQueryInfo 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccDirQueryInfo"
helpviewer_keywords: 
  - "SccDirQueryInfo 함수"
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# SccDirQueryInfo 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수에서는 현재 상태에 대 한 정규화 된 디렉터리의 목록을 검토합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 nDirs  
 \[in\] 쿼리할 선택한 디렉터리의 수입니다.  
  
 lpDirNames  
 \[in\] 배열을 쿼리할 수 있는 디렉터리의 정규화 된 경로입니다.  
  
 lpStatus  
 \[에서, out\] 상태 플래그를 반환 하는 플러그 인 소스 제어에 대 한 배열 구조 \(참조 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md) 대 한 자세한 내용은\).  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|쿼리가 성공 했습니다.|  
|SCC\_E\_OPNOTSUPPORTED|소스 코드 제어 시스템에서이 작업을 지원 하지 않습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_NONSPECIFICERROR<br /><br /> SCC\_E\_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 함수는 비트 마스크의 비트를 사용 하 여 반환 배열을 채웁니다는 `SCC_DIRSTATUS` 제품군 \(참조 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md)\)를 지정 하는 각 디렉터리에 대해 하나의 항목입니다. 에서는 상태 배열은 호출자가 할당 됩니다.  
  
 디렉터리 이름이 해당 프로젝트를 갖는지를 쿼리하여 소스 제어 디렉터리 인지 여부를 확인 하기 전에이 함수를 사용 하는 IDE입니다. 소스 제어의 디렉터리가 아닌 경우 IDE는 사용자에 게 적절 한 경고를 제공할 수 있습니다.  
  
> [!NOTE]
>  소스 제어 플러그 인을 보려면 상태 값 중 하나 이상을 구현 하지 하기로 구현 되지 않은 비트를 0으로 설정 되어야 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md)