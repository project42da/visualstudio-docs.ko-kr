---
title: "SccPopulateDirList 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccPopulateDirList"
helpviewer_keywords: 
  - "SccPopulateDirList 함수"
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# SccPopulateDirList 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 디렉터리와 선택적으로 파일을 검사 하는 디렉터리의 목록을 제공 하는 소스 제어에 저장 됩니다 결정 합니다.  
  
## 구문  
  
```cpp  
SCCRTN SccPopulateDirList(  
   LPVOID        pContext,  
   LONG          nDirs,  
   LPCSTR*       lpDirPaths,  
   POPDIRLISTFUNCpfnPopulate,  
   LPVOID        pvCallerData,  
   LONG          fOptions  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nDirs  
 \[in\] 디렉터리 경로 수는 `lpDirPaths` 배열입니다.  
  
 lpDirPaths  
 \[in\] 검사 하려면 디렉터리 경로 배열입니다.  
  
 pfnPopulate  
 \[in\] 콜백 함수를 각 디렉터리 경로 및 \(선택적 요소\)에서 파일 이름에 대 한 호출 `lpDirPaths` \(참조 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) 대 한 자세한 내용은\).  
  
 pvCallerData  
 \[in\] 값 변경 되지 않은 콜백 함수에 전달 하는 것입니다.  
  
 옵션이  
 \[in\] 디렉터리의 처리 방식을 제어 하는 값의 조합 \(의 "PopulateDirList 플래그" 섹션을 참조 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md) 가능한 값에 대 한\).  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|작업을 완료 했습니다.|  
|SCC\_E\_UNKNOWNERROR|오류가 발생 했습니다.|  
  
## 설명  
 콜백 함수에만 이러한 디렉터리 및 \(선택적 요소\)은 실제로 소스 제어 저장소에 파일 이름을 전달 됩니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md)   
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)   
 [오류 코드](../extensibility/error-codes.md)