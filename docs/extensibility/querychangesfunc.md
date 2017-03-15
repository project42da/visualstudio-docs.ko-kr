---
title: "QUERYCHANGESFUNC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "QUERYCHANGESFUNC"
helpviewer_keywords: 
  - "QUERYCHANGESFUNC 콜백 함수"
  - "QUERYCHANGESDATA 구조"
ms.assetid: 9d383e2c-eee1-4996-973a-0652d4c5951c
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 16
---
# QUERYCHANGESFUNC
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용 하는 콜백 함수는 [SccQueryChanges](../extensibility/sccquerychanges-function.md) 파일 이름의 컬렉션을 열거 하 고 각 파일의 상태를 확인 하는 작업입니다.  
  
 `SccQueryChanges` 함수는 지정 하 여 파일 및에 대 한 포인터는 `QUERYCHANGESFUNC` 콜백 합니다. 소스 제어 플러그 인 지정된 된 목록을 열거 하 고 목록에서 각 파일에 대 한 \(이 콜백\)을 통해 상태를 제공 합니다.  
  
## Signature  
  
```cpp#  
typedef BOOL (*QUERYCHANGESFUNC)( LPVOID pvCallerData, QUERYCHANGESDATA * pChangesData );  
```  
  
## 매개 변수  
 pvCallerData  
 \[in\] `pvCallerData` \(IDE\) 호출자가 매개 변수가 전달 [SccQueryChanges](../extensibility/sccquerychanges-function.md)합니다. 소스 제어 플러그 인이 값의 내용에 대 한 가정 안 합니다.  
  
 pChangesData  
 \[in\] 에 대 한 포인터는 [QUERYCHANGESDATA 구조](#LinkQUERYCHANGESDATA) 파일에 변경 내용을 설명 하는 구조입니다.  
  
## 반환 값  
 IDE에서 적절 한 오류 코드를 반환합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|처리를 계속 합니다.|  
|SCC\_I\_OPERATIONCANCELED|처리를 중지 합니다.|  
|SCC\_E\_xxx|모든 적절 한 SCC 오류 처리를 중지 해야 합니다.|  
  
##  <a name="LinkQUERYCHANGESDATA"></a> QUERYCHANGESDATA 구조  
 각 파일에 전달 된 구조는 다음과 같습니다.  
  
```cpp#  
struct QUERYCHANGESDATA_A { DWORD  dwSize; LPCSTR lpFileName; DWORD  dwChangeType; LPCSTR lpLatestName; }; typedef struct QUERYCHANGESDATA_A QUERYCHANGESDATA; struct QUERYCHANGESDATA_W { DWORD   dwSize; LPCWSTR lpFileName; DWORD   dwChangeType; LPCWSTR lpLatestName; };  
```  
  
 dwSize  
 이 구조 \(바이트\)의 크기입니다.  
  
 lpFileName  
 이 항목에 대 한 원래 파일 이름입니다.  
  
 dwChangeType  
 파일의 상태를 나타내는 코드:  
  
|코드|설명|  
|--------|--------|  
|`SCC_CHANGE_UNKNOWN`|변경 내용을 인식할 수 없습니다.|  
|`SCC_CHANGE_UNCHANGED`|이 파일에 대 한 이름 변경 되지 않았습니다.|  
|`SCC_CHANGE_DIFFERENT`|다른 id 가진 파일 이름이 같은 데이터베이스에 존재 합니다.|  
|`SCC_CHANGE_NONEXISTENT`|파일에는 로컬로 또는 데이터베이스에 존재 하지 않습니다.|  
|`SCC_CHANGE_DATABASE_DELETED`|데이터베이스에서 삭제 된 파일입니다.|  
|`SCC_CHANGE_LOCAL_DELETED`|데이터베이스에 파일을 로컬에서 삭제 되었지만 파일이 여전히 존재 합니다. 이 확인할 수 없는 경우 반환할 `SCC_CHANGE_DATABASE_ADDED`합니다.|  
|`SCC_CHANGE_DATABASE_ADDED`|파일은 데이터베이스에 추가 되지만 로컬로 존재 하지 않습니다.|  
|`SCC_CHANGE_LOCAL_ADDED`|데이터베이스에 존재 하지 않는 파일과 새 로컬 파일이 있습니다.|  
|`SCC_CHANGE_RENAMED_TO`|파일 데이터베이스에 이동 되거나 이름이 바뀌지 `lpLatestName`합니다.|  
|`SCC_CHANGE_RENAMED_FROM`|파일에서 데이터베이스에 이동 되거나 이름이 바뀌지 `lpLatestName`;이를 추적 하려면 비용이 너무 높을 경우 다른 플래그와 같이 반환 `SCC_CHANGE_DATABASE_ADDED`합니다.|  
  
 lpLatestName  
 이 항목에 대 한 현재 파일 이름입니다.  
  
## 참고 항목  
 [IDE에 의해 구현 되는 콜백 함수](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)   
 [오류 코드](../extensibility/error-codes.md)