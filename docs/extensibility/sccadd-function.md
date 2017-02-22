---
title: "SccAdd 함수 | Microsoft Docs"
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
  - "SccAdd"
helpviewer_keywords: 
  - "SccAdd 함수"
ms.assetid: 545268f3-8e83-446a-a398-1a9db9e866e8
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# SccAdd 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어 시스템에 새 파일을 추가합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccAdd(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG*     pfOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 nFiles  
 \[in\] 에 지정 된 대로 현재 프로젝트에 추가 하도록 선택한 파일의 수는 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 \[in\] 추가할 파일의 정규화 된 로컬 이름 배열입니다.  
  
 lpComment  
 \[in\] 모든 추가 파일에 적용 될 주석입니다.  
  
 pfOptions  
 \[in\] 파일 단위로에서 제공 하는 명령 플래그의 배열입니다.  
  
 pvOptions  
 \[in\] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|추가 작업이 완료 되었습니다.|  
|SCC\_E\_FILEALREADYEXISTS|선택한 파일이 소스 제어에서 이미 있습니다.|  
|SCC\_E\_TYPENOTSUPPORTED|형식 \(예: 이진\) 파일의 소스 제어 시스템에서 지원 되지 않습니다.|  
|SCC\_E\_OPNOTSUPPORTED|소스 제어 시스템에서이 작업을 지원 하지 않습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류입니다. 추가 수행 되지 않습니다.|  
|SCC\_I\_OPERATIONCANCELED|작업이 완료 되기 전에 취소 되었습니다.|  
|SCC\_I\_RELOADFILE|파일이 나 프로젝트를 다시 로드 해야 합니다.|  
|SCC\_E\_FILENOTEXIST|로컬 파일을 찾을 수 없습니다.|  
  
## 설명  
 일반적인 `fOptions` 바뀝니다 여기 배열이 `pfOptions`, 하나로 `LONG` 파일당 사양 옵션입니다. 즉, 파일 형식 파일 다를 수 있습니다.  
  
> [!NOTE]
>  모두 지정할 수 없는 `SCC_FILETYPE_TEXT` 및 `SCC_FILETYPE_BINARY` 하지만 동일한 파일에 대 한 옵션은 둘 다 지정할 수 있습니다. 둘 다 설정은 설정과 동일 `SCC_FILETYPE_AUTO`, 이 경우 소스 제어 플러그 인 autodetects 파일 형식입니다.  
  
 다음에 사용 된 플래그의 목록은 `pfOptions` 배열:  
  
|옵션|값|의미|  
|--------|-------|--------|  
|SCC\_FILETYPE\_AUTO|0 x 00|소스 제어 플러그 인 파일 유형을 검색 해야 합니다.|  
|SCC\_FILETYPE\_TEXT|0x01|ASCII 텍스트 파일을 나타냅니다.|  
|SCC\_FILETYPE\_BINARY|0x02|ASCII 텍스트 이외에 다른 파일 형식을 나타냅니다.|  
|SCC\_ADD\_STORELATEST|0 x 04|만 없습니다 델타 파일의 최신 복사본을 저장합니다.|  
|SCC\_FILETYPE\_TEXT\_ANSI|0x08|ANSI 텍스트 파일을 처리합니다.|  
|SCC\_FILETYPE\_UTF8|0x10|유니코드 텍스트 UTF8 형식에서으로 파일을 처리합니다.|  
|SCC\_FILETYPE\_UTF16LE|0x20|Little Endian 형식으로 UTF16에서 유니코드 텍스트 파일을 처리합니다.|  
|SCC\_FILETYPE\_UTF16BE|0x40|에서는 파일에 UTF16 Big Endian 유니코드 텍스트와 서식을 지정 합니다.|  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)