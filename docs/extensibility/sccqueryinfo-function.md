---
title: "SccQueryInfo 함수 | Microsoft Docs"
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
  - "SccQueryInfo"
helpviewer_keywords: 
  - "SccQueryInfo 함수"
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# SccQueryInfo 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어에서 선택한 파일의 집합에 대 한 상태 정보를 가져옵니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccQueryInfo(  
   LPVOID  pvContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPLONG  lpStatus  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 nFiles  
 \[in\] 에 지정 된 파일의 수는 `lpFileNames` 배열과의 길이 `lpStatus` 배열입니다.  
  
 lpFileNames  
 \[in\] 배열을 쿼리할 수 있는 파일의 이름입니다.  
  
 lpStatus  
 \[에서, out\] 소스 제어 플러그 인 각 파일에 대 한 상태 플래그를 반환 하는 배열입니다. 자세한 내용은 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)을 참조하십시오.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|쿼리가 성공 했습니다.|  
|SCC\_E\_ACCESSFAILURE|네트워크 또는 경합 문제가 발생할 수 있는 소스 제어 시스템에 액세스 하는 문제가 발생 했습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_PROJNOTOPEN|프로젝트 소스 제어에서 열려 있지 않습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 경우 `lpFileName` 이 빈 문자열인 경우는 현재 업데이트 상태 정보가 없습니다. 그렇지 않은 경우 변경 된 상태 정보를 파일의 전체 경로 이름입니다.  
  
 반환 배열의 비트 마스크 수 `SCC_STATUS_xxxx` 비트입니다. 자세한 내용은 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)을 참조하십시오. 소스 제어 시스템에서 모든 비트 종류를 지원 하지 않습니다. 예를 들어 경우 `SCC_STATUS_OUTOFDATE` 는 제공 되지 않습니다, 비트가 사실은 그렇지 않습니다.  
  
 이 함수를 사용 하 여 파일을 체크 아웃, 다음을 유의 하십시오. `MSSCCI` 상태 요구 사항:  
  
-   `SCC_STATUS_OUTBYUSER` 현재 사용자가 파일을 체크 아웃 하는 경우 설정 됩니다.  
  
-   `SCC_STATUS_CHECKEDOUT` 아니면 설정할 수 없습니다 `SCC_STATUS_OUTBYUSER` 설정 됩니다.  
  
-   `SCC_STATUS_CHECKEDOUT` 파일은 체크 아웃할 때 지정 된 작업 디렉터리에만 설정 됩니다.  
  
-   하는 경우 파일은 체크 아웃 된 현재 사용자가 작업 디렉터리 이외의 디렉터리에 `SCC_STATUS_OUTBYUSER` 설정 되어 있지만 `SCC_STATUS_CHECKEDOUT` 않습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)