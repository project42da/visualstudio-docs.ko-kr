---
title: "SccAddFromScc 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccAddFromScc"
helpviewer_keywords: 
  - "SccAddFromScc 함수"
ms.assetid: 902e764d-200e-46e1-8c42-4da7b037f9a0
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# SccAddFromScc 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수를 소스 제어 시스템에 이미 있는 파일을 찾아보려면 허용 하 고 이후에 현재 프로젝트 부분에서는 이러한 파일을 확인 합니다. 예를 들어이 함수 파일을 복사 하지 않고 현재 프로젝트에 공통 헤더 파일을 가져올 수 있습니다. 파일의 반환 배열 `lplpFileNames`, IDE 프로젝트에 추가 하는 사용자가 파일의 목록을 포함 합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccAddFromScc (  
   LPVOID   pvContext,  
   HWND     hWnd,  
   LPLONG   lpnFiles,  
   LPCSTR** lplpFileNames  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpnFiles  
 \[에서, out\] 에 추가 되는 파일의 수에 대 한 버퍼입니다. \(이 `NULL` 가리키는 메모리 경우 `lplpFileNames` 해제 되어야 하는 것입니다. 주의 참조 대 한 자세한 내용은.\)  
  
 lplpFileNames  
 \[에서, out\] 디렉터리 경로 없이 모든 파일 이름에 대 한 포인터의 배열입니다. 이 배열은 할당 되 고 소스 제어 플러그 인에 의해 해제 됩니다. 경우 `lpnFiles` \= 1 및 `lplpFileNames` 없는 `NULL`, 를 가리키는 배열에 있는 첫 번째 이름 `lplpFileNames` 대상 폴더를 포함 합니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|성공적으로 파일이 있으며 프로젝트에 추가 되었습니다.|  
|SCC\_I\_OPERATIONCANCELED|영향을 주지 작업이 취소 되었습니다.|  
|SCC\_I\_RELOADFILE|파일이 나 프로젝트를 다시 로드 해야 합니다.|  
  
## 설명  
 IDE는이 함수를 호출합니다. IDE를 전달 하는 소스 제어 플러그 인이 로컬 대상 폴더를 지정 하를 지 원하는 경우 `lpnFiles` \= 1 및 전달에 로컬 폴더 이름을 `lplpFileNames`합니다.  
  
 경우에 대 한 호출의 `SccAddFromScc` 플러그 인에 값을 할당, 함수 반환 `lpnFiles` 및 `lplpFileNames`, 필요에 따라 파일 이름 배열에 대 한 메모리를 할당 \(이 할당에 대 한 포인터를 대체 하 `lplpFileNames`\). 소스 제어 플러그 인은 사용자의 디렉터리에 있거나 지정 된 대상 폴더에 모든 파일을 배치 하는 일을 담당 합니다. IDE는 그런 다음 IDE 프로젝트에 파일을 추가합니다.  
  
 마지막으로, IDE 호출이 함수를 다시 한 번 전달 `NULL` 에 대 한 `lpnFiles`합니다. 이것은 특별 한 신호 소스 제어에서 파일 이름 배열에 할당 된 메모리를 해제 하려면 플러그 인 `lplpFileNames``.`  
  
 `lplpFileNames` 한 `char ***` 포인터입니다. 따라서이 API에 대 한 목록 표준 방식으로 전달 되는 파일 이름에 대 한 포인터의 배열에 대 한 포인터를 배치 하는 소스 제어 플러그 인 합니다.  
  
> [!NOTE]
>  VSSCI API의 초기 버전에 추가 된 파일에 대 한 대상 프로젝트를 지정 하는 방법을 제공 하지 않았습니다. 이 의미 체계는 `lplpFIleNames` 매개 변수는 출력 매개 변수를 사용 하지 않고\/out 매개 변수 확인 하도록 향상 되었습니다. 단일 파일을 지정 하는 경우만, 즉 값 가리키는 `lpnFiles` 의 첫 번째 요소를 1 \= `lplpFileNames` 대상 폴더를 포함 합니다. 이러한 새로운 의미 체계를 호출 하 여 IDE 사용 하는 `SccSetOption` 함수는 `nOption`매개 변수 설정 `SCC_OPT_SHARESUBPROJ`합니다. 소스 제어 플러그 인 의미 체계를 지원 하지 않는 경우 반환 `SCC_E_OPTNOTSUPPORTED`합니다. 따라서 사용 하지 않도록 설정의 사용을 수행 하는 **소스 제어에서 추가** 기능입니다. 플러그 인을 지 원하는 경우는 **소스 제어에서 추가** 기능 \(`SCC_CAP_ADDFROMSCC`\), 새 의미 체계를 지원 하 고 반환 해야 합니다 `SCC_I_SHARESUBPROJOK`합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)