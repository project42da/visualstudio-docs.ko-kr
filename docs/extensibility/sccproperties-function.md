---
title: "SccProperties 함수 | Microsoft Docs"
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
  - "SccProperties"
helpviewer_keywords: 
  - "SccProperties 함수"
ms.assetid: 1bed38c9-73d2-4474-9717-f9dc26a89cbe
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# SccProperties 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 파일 또는 프로젝트에 대 한 소스 제어 속성을 표시합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccProperties (  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpFileName  
 \[in\] 파일이 나 프로젝트의 정규화 된 경로 이름입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|속성은 성공적으로 표시 되었습니다.|  
|SCC\_I\_RELOADFILE|버전 제어 시스템 IDE이이 파일을 다시 로드 해야 하므로 파일 속성을 수정 했습니다.|  
|SCC\_E\_PROJNOTOPEN|지정된 된 프로젝트 소스 제어에서 열리지 않았습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자는이 파일 또는 프로젝트의 속성을 볼 권한이 없습니다.|  
|SCC\_E\_FILENOTCONTROLLED|지정 된 파일이 나 프로젝트 없는 경우 소스 제어|  
|SCC\_E\_NONSPECIFICERROR<br /><br /> SCC\_E\_UNKNOWNERROR|알 수 없거나 일반 오류가 발생 했습니다.|  
  
## 설명  
 소스 제어 플러그 인 대화 상자에서 속성을 표시합니다.  
  
 소스 제어 플러그 인에서 정의 된 속성과 플러그 인에 플러그 인에서 다를 수 있습니다. 반환 해야 하는 경우 플러그 인 사용 하면 파일의 소스 제어 속성을 변경 하려면, `SCC_I_RELOAD` 이 파일이 나 프로젝트를 다시 로드 해야 하는 IDE를 알리기 위해.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)