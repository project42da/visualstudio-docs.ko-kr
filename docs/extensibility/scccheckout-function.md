---
title: "SccCheckout 함수 | Microsoft Docs"
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
  - "SccCheckout"
helpviewer_keywords: 
  - "SccCheckout 함수"
ms.assetid: 06e9ecd7-fc09-40c1-9dd1-2b56c622c80b
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# SccCheckout 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

정규화 된 파일 이름의 목록을 주어진 경우이 함수 확인에 로컬 드라이브입니다. 메모는 체크 아웃 되 고 모든 파일에 적용 됩니다. 주석 인수 수는 `null` 문자열입니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccCheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 nFiles  
 \[in\] 체크 아웃 하기 위해 선택한 파일 수입니다.  
  
 lpFileNames  
 \[in\] 체크 아웃할 파일의 정규화 된 로컬 경로 이름의 배열입니다.  
  
 lpComment  
 \[in\] 각 체크 아웃 되 고 선택한 파일에 적용 될 주석입니다.  
  
 옵션이  
 \[in\] 명령 플래그 \(참조 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md)\).  
  
 pvOptions  
 \[in\] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|체크 아웃 했습니다.|  
|SCC\_E\_FILENOTCONTROLLED|선택한 파일이 소스 코드 제어 하지 않습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다. 파일 체크 아웃 되지 않았습니다.|  
|SCC\_E\_ALREADYCHECKEDOUT|사용자가 이미 파일을 체크 아웃 합니다.|  
|SCC\_E\_FILEISLOCKED|새 버전 생성 등의 금지는 파일이 잠겨 있습니다.|  
|SCC\_E\_FILEOUTEXCLUSIVE|다른 사용자는이 파일에는 단독 체크 아웃을 종료 했습니다.|  
|SCC\_I\_OPERATIONCANCELED|작업이 완료 되기 전에 취소 되었습니다.|  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md)