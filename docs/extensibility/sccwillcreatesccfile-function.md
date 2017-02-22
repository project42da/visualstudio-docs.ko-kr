---
title: "SccWillCreateSccFile 함수 | Microsoft Docs"
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
  - "SccWillCreateSccFile"
helpviewer_keywords: 
  - "SccWillCreateSccFile 함수"
ms.assetid: 0d7542f0-4351-41b3-b24c-960ab99c05a1
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# SccWillCreateSccFile 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어 플러그 인은 MSSCCPRJ 만들기를 지원 하는지 여부를 결정 합니다. SCC 파일 각각의 지정 된 파일입니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccWillCreateSccFile(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPBOOL  pbSccFiles  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nFiles  
 \[in\] 파일 이름에 포함 된 수의 `lpFileNames` 의 길이와 배열는 `pbSccFiles` 배열입니다.  
  
 lpFileNames  
 \[in\] 확인 하려면 정규화 된 파일 이름 배열을 \(배열 호출자가 할당 해야 합니다\).  
  
 pbSccFiles  
 \[에서, out\] 결과 저장할 배열입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|명령 실행 성공|  
|SCC\_E\_INVALIDFILEPATH|배열에 있는 경로 중 하나가 올바르지 않습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 이 함수는 소스 제어 플러그 인은 MSSCCPRJ에서 지원 되는 확인 하는 파일 목록과 함께 호출 됩니다. 각 \(에 대 한 자세한 내용은 MSSCCPRJ 지정 된 파일에 대 한 SCC 파일. SCC 파일 참조 [MSSCCPRJ 합니다. SCC 파일](../extensibility/mssccprj-scc-file.md)\). 소스 제어 플러그 인 MSSCCPRJ 만드는 기능이 있는지 선언할 수 있습니다. SCC 파일 선언 하 여 `SCC_CAP_SCCFILE` 초기화 하는 동안. 플러그 인 반환 `TRUE` 또는 `FALSE` 각 파일에는 `pbSccFiles` MSSCCPRJ 지정 된 파일 중 어떤 나타내기 위해 배열입니다. SCC 지원 합니다. 플러그 인을 반환할 경우 성공 코드 함수에서 반환 배열에 값을 적용할 수 있습니다. 오류 시 배열은 무시 됩니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [MSSCCPRJ 합니다. SCC 파일](../extensibility/mssccprj-scc-file.md)