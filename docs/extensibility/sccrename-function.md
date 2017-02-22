---
title: "SccRename 함수 | Microsoft Docs"
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
  - "SccRename"
helpviewer_keywords: 
  - "SccRename 함수"
ms.assetid: b467ade6-a1db-4c0b-b60f-7850ec4f79eb
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# SccRename 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

소스 제어 시스템에서이 함수에는 파일을 이름을 바꿉니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccRename(  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName,  
   LPCSTR lpNewName  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpFileName  
 \[in\] 이름을 바꿀 파일의 정규화 된 파일 이름입니다.  
  
 lpNewName  
 \[in\] 정규화 된 새 이름입니다. 디렉터리 경로가 다른 경우 다음 파일이 이동 한 하위 디렉터리에서 다른 합니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|이름 바꾸기 작업이 완료 되었습니다.|  
|SCC\_E\_PROJNOTOPEN|프로젝트 소스 제어에서 열려 있지 않습니다.|  
|SCC\_E\_FILENOTCONTROLLED|소스 제어는 파일이 아닙니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자는이 작업을 완료할 권한이 없습니다.|  
|SCC\_E\_COULDNOTCREATEPROJECT|프로젝트 이름 바꾸기 프로세스의 일부로 만들 수 없습니다.|  
|SCC\_E\_OPNOTPERFORMED|작업을 수행 하지 못했습니다.|  
|SCC\_E\_NONSPECIFICERROR|지정 되지 않은 또는 일반 오류가 발생 했습니다.|  
  
## 설명  
 파일 이름 바꾸기 또는 이동 하 한 위치에서 다른 소스 제어 시스템에서이 함수를 사용할 수 있습니다. 소스 제어 플러그 인 디스크에 있는 파일에 액세스 하지 않아야 합니다. 것은 로컬 파일의 이름을 바꾸려면 IDE의 책임입니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)