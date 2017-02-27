---
title: "SccInitialize 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccInitialize"
helpviewer_keywords: 
  - "SccInitialize 함수"
ms.assetid: 5bc0d28b-2c68-4d43-9e51-541506a8f76e
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# SccInitialize 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수 소스 제어 플러그 인을 초기화 하 고 기능 및 통합된 개발 환경 \(IDE\)에 대 한 제한을 제공 합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccInitialize (  
   LPVOID* ppvContext,  
   HWND    hWnd,  
   LPCSTR  lpCallerName,  
   LPSTR   lpSccName,  
   LPLONG  lpSccCaps,  
   LPSTR   lpAuxPathLabel,  
   LPLONG  pnCheckoutCommentLen,  
   LPLONG  pnCommentLen  
);  
```  
  
#### 매개 변수  
 `ppvContext`  
 \[in\] 소스 제어 플러그 인 여기 해당 상황에 맞는 구조에 대 한 포인터를 배치할 수 있습니다.  
  
 `hWnd`  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 `lpCallerName`  
 \[in\] 소스 제어 플러그 인을 호출 하는 프로그램의 이름입니다.  
  
 `lpSccName`  
 \[에서, out\] 소스 제어 플러그 인 이름 자체를 배치 하는 위치 버퍼 \(이내임 `SCC_NAME_LEN`\).  
  
 `lpSccCaps`  
 \[out\] 소스 제어 플러그 인의 기능 플래그를 반환합니다.  
  
 `lpAuxPathLabel`  
 \[에서, out\] 소스 제어 플러그 인에 대해 설명 하는 문자열을 배치 하는 위치는 버퍼는 `lpAuxProjPath` 매개 변수에서 반환 되는 [SccOpenProject](../extensibility/sccopenproject-function.md) 및 [SccGetProjPath](../extensibility/sccgetprojpath-function.md) \(이내임 `SCC_AUXLABEL_LEN`\).  
  
 `pnCheckoutCommentLen`  
 \[out\] 체크 아웃 설명에 대 한 최대 허용 길이 반환합니다.  
  
 `pnCommentLen`  
 \[out\] 다른 의견에 대 한 최대 허용 길이 반환합니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|소스 제어 초기화에 성공 했습니다.|  
|SCC\_E\_INITIALIZEFAILED|시스템을 초기화할 수 없습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자 지정된 작업을 수행할 수 없습니다.|  
|SCC\_E\_NONSPECFICERROR|알 수 없는 오류입니다. 소스 제어 시스템을 초기화 하지 못했습니다.|  
  
## 설명  
 IDE에서 소스 제어 플러그 인를 처음 로드 될 때이 함수를 호출 합니다. IDE에서를이 플러그 인에 호출자에 게 이름, 같은 특정 정보를 전달할 수 있습니다. IDE도 다시 가져온 주석 및 기능에 대 한 플러그 인에 대 한 허용 가능한 최대 길이 등의 특정 정보가 합니다.  
  
 `ppvContext` 가리키는 `NULL` 포인터입니다. 소스 제어 플러그 인 수 자체 용도에 구조를 할당 하 고 해당 구조에 대 한 포인터를 저장 `ppvContext`합니다. IDE는 플러그 인 전역 저장소에 문의 하지 않고 컨텍스트 정보를 알고 있어야 하 고 플러그 인의 여러 인스턴스를 지원 하도록 허용이 포인터를 다른 모든 VSSCI API 함수를 전달 합니다. 이 구조를 할당 취소 될 때의 [SccUninitialize](../extensibility/sccuninitialize-function.md) 라고 합니다.  
  
 `lpCallerName` 및 `lpSccName` IDE와 소스 제어 플러그 인 이름 교환할 수 매개 변수를 사용 합니다. 메뉴 또는 대화 상자에서 실제로 표시 될 수 또는 여러 인스턴스를 구별 하는 단순히 이러한 이름은 사용할 수 있습니다.  
  
 `lpAuxPathLabel` 매개 변수는 솔루션 파일에 저장 되 고 소스 제어 플러그 인에 대 한 호출에 전달 되는 보조 프로젝트 경로 확인 하는 주석으로 사용 되는 문자열은 [SccOpenProject](../extensibility/sccopenproject-function.md)합니다.[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] 문자열을 사용 하 여 "SourceSafe 프로젝트:"; 이 특정 문자열을 사용 하 여 다른 소스 제어 플러그 인이 포함 되지 않습니다 해야 합니다.  
  
 `lpSccCaps` 매개 변수를 제공 하는 소스 제어 플러그 인 기능에 대 한 플러그 인을 나타내는 비트를 저장 합니다. \(기능 비트 형식의 전체 목록을 보려면 참조 [기능 플래그](../extensibility/capability-flags.md)\). 예를 들어, 호출자가 제공한 콜백 함수에 결과 기록 하는 기능을 설정 플러그 인에 대 한 플러그 인 않으려는 SCC\_CAP\_TEXTOUT 비트 경우. 버전 제어 결과 대 한 창을 만드는 데 IDE를 신호로 알리는 것이 있습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccUninitialize](../extensibility/sccuninitialize-function.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [기능 플래그](../extensibility/capability-flags.md)