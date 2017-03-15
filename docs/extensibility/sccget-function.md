---
title: "SccGet 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccGet"
helpviewer_keywords: 
  - "SccGet 함수"
ms.assetid: 09a18bd2-b788-411a-9da6-067d806e46f6
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# SccGet 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수를 편집 하지 않는 보기 및 컴파일하고, 하나 이상의 파일의 복사본을 검색 합니다. 대부분의 시스템에서 파일 읽기 전용으로 태그가 지정 됩니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccGet(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 상황에 맞는 구조는 소스 제어 플러그 인입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 nFiles  
 \[in\] 에 지정 된 파일의 수는 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 \[in\] 검색할 파일의 정규화 된 이름의 배열입니다.  
  
 옵션이  
 \[in\] 명령 플래그 \(`SCC_GET_ALL`, `SCC_GET_RECURSIVE`\).  
  
 pvOptions  
 \[in\] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|가져오기 작업의 성공 합니다.|  
|SCC\_E\_FILENOTCONTROLLED|소스 제어는 파일이 아닙니다.|  
|SCC\_E\_OPNOTSUPPORTED|소스 제어 시스템에서이 작업을 지원 하지 않습니다.|  
|SCC\_E\_FILEISCHECKEDOUT|사용자 현재가 체크 아웃 된 파일을 가져올 수 없습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_NOSPECIFIEDVERSION|에 잘못 된 버전 또는 날짜\/시간을 지정 합니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류입니다. 파일 동기화 되지 않았습니다.|  
|SCC\_I\_OPERATIONCANCELED|작업이 완료 되기 전에 취소 합니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 권한이 없습니다.|  
  
## 설명  
 이 함수는 개수 및 검색할 파일의 이름 배열을 사용 하 여 호출 됩니다. IDE는 플래그를 전달 하는 경우 `SCC_GET_ALL`, 즉, 항목 `lpFileNames` 는 파일이 아니라 디렉터리 및 지정 된 디렉터리에서 소스 제어 아래에 있는 모든 파일 검색 됩니다.  
  
 `SCC_GET_ALL` 플래그 함께 사용할 수는 `SCC_GET_RECURSIVE` 플래그를 지정 된 디렉터리의 모든 파일 및 모든 하위 디렉터리도 검색 합니다.  
  
> [!NOTE]
>  `SCC_GET_RECURSIVE` 되지 않고 전달할지 `SCC_GET_ALL`합니다. 또한는 C:\\A\\B 및 C:\\A 디렉터리 재귀 전달 get 인 C:\\A\\B 및 모든 하위 디렉터리 실제로 검색 되므로 두 번 note 합니다. IDE의 책임\-하지는 소스 제어 플러그 인의 및\-배열과 이와 같은 중복 항목은 보관 하는 확인할 수 있도록 합니다.  
  
 소스 제어 플러그 인 경우에 지정 하는 마지막으로 `SCC_CAP_GET_NOUI` Get 명령에 대 한 사용자 인터페이스는 것을 파일을 검색 하는 IDE에서이 함수를 호출할 수 있습니다 나타내는 초기화에 대 한 플래그입니다. 플래그 단순히 의미 IDE Get 메뉴 항목을 표시 하지 않는 모든 UI 제공 하는 예상 된 플러그 인 없는 합니다.  
  
## 이름 바꾸기 및 SccGet  
 상황: 사용자 예를 들어 a.txt 파일을 체크 아웃 및 수정 하 고 있습니다. A.txt 체크 인할 수, 전에 두 번째 사용자 이름을 a.txt 소스 제어 데이터베이스에서 b.txt로, 체크 아웃 b.txt, 사항을 일부 파일을 수정 바꾼 파일을 검사 합니다. 첫 번째 사용자가 첫 번째 사용자 b.txt a.txt 파일의 로컬 버전 이름을 바꾼 파일에 대해 get 않습니다 하므로 두 번째 사용자가 수행한 변경 합니다. 그러나 버전 번호를 추적 하는 로컬 캐시 여전히 것으로 생각 a.txt의 첫 번째 버전 로컬로 저장 되 고 소스 제어의 차이 확인할 수 없습니다.  
  
 원본 제어 버전의 로컬 캐시가 소스 제어 데이터베이스와 동기화 되지이 문제를 해결 하는 방법은 두 가지가 있습니다.  
  
1.  현재 체크 아웃 된 소스 제어 데이터베이스에 파일 이름을 허용 하지 않습니다.  
  
2.  해당 하는 "이전"삭제 "새로 추가" 하 여 다음을 수행 합니다. 다음 알고리즘에는이를 위해 한 가지 방법은입니다.  
  
    1.  호출 된 [SccQueryChanges](../extensibility/sccquerychanges-function.md) a.txt 소스 제어 데이터베이스에서 b.txt로 이름을 변경 하는 방법에 대 한 자세한 함수입니다.  
  
    2.  로컬 a.txt을 b.txt로 이름을 바꿉니다.  
  
    3.  호출 된 `SccGet` a.txt 및 b.txt 모두에 대 한 함수입니다.  
  
    4.  A.txt 소스 제어 데이터베이스에 없기 때문에 로컬 버전 캐시 누락 a.txt 버전 정보 삭제 됩니다.  
  
    5.  B.txt 파일을 체크 아웃 되 고 로컬 b.txt 파일의 내용으로 병합 됩니다.  
  
    6.  업데이트 된 b.txt 파일을 체크 인 이제 수 있습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md)