---
title: "SccAddFilesFromSCC 함수 | Microsoft Docs"
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
  - "SccAddFilesFromSCC"
helpviewer_keywords: 
  - "SccAddFilesFromSCC 함수"
ms.assetid: f21a3500-ade8-4dd8-8647-10e2179be9c1
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# SccAddFilesFromSCC 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 현재 열려 있는 프로젝트를 소스 제어에서 파일 목록을 추가합니다.  
  
## 구문  
  
```cpp  
SCCRTN SccAddFilesFromSCC(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LPSTR   lpUser,  
   LPSTR   lpAuxProjPath,  
   LONG    cFiles,  
   LPCSTR* lpFilePaths,  
   LPCSTR  lpDestination,  
   LPCSTR  lpComment,  
   LPBOOL  pbResults  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpUser  
 \[에서, out\] SCC\_USER\_SIZE null 종결자 포함\) \(최대 사용자 이름입니다.  
  
 lpAuxProjPath  
 \[에서, out\] 프로젝트를 식별 하는 보조 문자열 \(최대 `SCC_PRJPATH_`크기, null 종결자 포함\).  
  
 cFiles  
 \[in\] 제공한 파일 수가 `lpFilePaths`합니다.  
  
 lpFilePaths  
 \[에서, out\] 현재 프로젝트에 추가할 파일 이름 배열입니다.  
  
 lpDestination  
 \[in\] 파일이 쓸 수 있는 대상 경로입니다.  
  
 lpComment  
 \[in\] 각 추가 되는 파일에 적용 될 주석입니다.  
  
 pbResults  
 \[에서, out\] \(0이 아닌 값 또는 TRUE\) 성공을 표시 하기 위해 설정 또는 실패 하는 플래그의 배열 \(0 또는 FALSE\) 각 파일에 대해 \(배열 크기 이상 이어야 합니다 `cFiles` long\)입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_E\_PROJNOTOPEN|프로젝트가 열려 있지 않습니다.|  
|SCC\_E\_OPNOTPERFORMED|연결에 지정 된 대로 동일한 프로젝트에 않습니다. `lpAuxProjPath.`|  
|SCC\_E\_NOTAUTHORIZED|사용자는 데이터베이스를 업데이트 하는 권한이 없습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
|SCC\_I\_RELOADFILE|파일이 나 프로젝트를 다시 로드 해야 합니다.|  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)