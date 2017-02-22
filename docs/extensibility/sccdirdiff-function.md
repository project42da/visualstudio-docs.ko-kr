---
title: "SccDirDiff 함수 | Microsoft Docs"
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
  - "SccDirDiff"
helpviewer_keywords: 
  - "SccDirDiff 함수"
ms.assetid: 26c9ba92-e3b9-4dd2-bd5e-76b17745e308
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# SccDirDiff 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 클라이언트 디스크에서 현재 로컬 디렉터리와 해당 하는 소스 제어에서 프로젝트의 차이 표시합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccDirDiff(  
   LPVOID    pContext,  
   HWND      hWnd,  
   LPCSTR    lpDirName,  
   LONG      dwFlags,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpDirName  
 \[in\] 정규화 된 경로 표시할 시각적 차이점에 대 한 로컬 디렉터리에 있습니다.  
  
 dwFlags  
 \[in\] 명령 플래그 \(설명 참조 섹션\).  
  
 pvOptions  
 \[in\] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|디스크의 디렉터리에 소스 코드 제어에 프로젝트와 같습니다.|  
|SCC\_I\_FILESDIFFER|디스크의 디렉터리에는 소스 코드 제어에 프로젝트와에서 다릅니다.|  
|SCC\_I\_RELOADFILE|파일이 나 프로젝트를 다시 로드 해야 합니다.|  
|SCC\_E\_FILENOTCONTROLLED|소스 코드 제어는 디렉터리가 되었습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_NONSPECIFICERROR<br /><br /> SCC\_E\_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
|SCC\_E\_FILENOTEXIST|로컬 디렉터리를 찾을 수 없습니다.|  
  
## 설명  
 소스 제어 플러그 인을 사용자에 게는 지정 된 디렉터리로 변경 내용 목록을 표시 하도록 지시 하려면이 함수가 사용 됩니다. 플러그 인 자체 창을 디스크에 대 한 사용자의 디렉터리와 해당 프로젝트를 버전 제어의 차이 표시 하려면 선택한 형식에서 열립니다.  
  
 모두에 있는 디렉터리의 플러그인 지원 비교를 지원 해야 비교 디렉터리의 파일 이름으로 "빠른 비교" 옵션 지원 되지 않는 경우에 합니다.  
  
|`dwFlags`|해석|  
|---------------|--------|  
|SCC\_DIFF\_IGNORECASE|대\/소문자 구분 비교 \(visual 또는 빠른 차이 대 한 사용할 수 있음\).|  
|SCC\_DIFF\_IGNORESPACE|공백 \(빠른 차이 또는 visual 사용할 수 있음\)을 무시 합니다.|  
|SCC\_DIFF\_QD\_CONTENTS|소스 제어 플러그 인에서 지 원하는, 자동으로 디렉터리를 바이트 단위로 비교 합니다.|  
|SCC\_DIFF\_QD\_CHECKSUM|플러그 인에서 지 원하는, 자동으로 체크섬을 통해 디렉터리를 비교 하거나, 지원 되지 않는 경우 SCC\_DIFF\_QD\_CONTENTS로 대체 합니다.|  
|SCC\_DIFF\_QD\_TIME|플러그 인에서 지 원하는, 자동으로 해당 타임 스탬프를 통해 디렉터리를 비교 또는, 지원 되지 않는 경우 SCC\_DIFF\_QD\_CHECKSUM 또는 SCC\_DIFF\_QD\_CONTENTS 대체 하는 경우.|  
  
> [!NOTE]
>  와 같은 명령 플래그를 사용 하는이 함수는 [SccDiff](../extensibility/sccdiff-function.md)합니다. 그러나 소스 제어 플러그 인 디렉터리에 대 한 "빠른 비교" 작업을 지원 하지 않도록 선택할 수 있습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)