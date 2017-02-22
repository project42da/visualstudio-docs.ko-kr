---
title: "특정 명령에서 사용 하는 비트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 플러그 인, 특정 명령에서 사용 하는 비트"
ms.assetid: 37969977-6f7d-45c9-ba03-1306ae71f5d1
caps.latest.revision: 24
caps.handback.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
---
# 특정 명령에서 사용 하는 비트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

단일 값에서 하나 이상의 비트를 설정 하 여 다양 한 소스 제어 플러그 인 API의 함수 동작을 수정할 수 있습니다. 이러한 값을 비트 라고 합니다. 소스 제어 플러그 인 API에서 사용 하는 다양 한 비트를 사용 하는 기능에 따라 그룹화 여기에서 자세히 나와 있습니다.  
  
## 체크 아웃 플래그  
 에 대 한이 플래그를 설정할 수는 [SccAdd](../extensibility/sccadd-function.md) 또는 [SccCheckin](../extensibility/scccheckin-function.md)합니다.  
  
|플래그|값|설명|  
|---------|-------|--------|  
|`SCC_KEEP_CHECKEDOUT`|0x1000|파일을 체크 아웃을 유지 합니다.|  
  
## 플래그 추가  
 이러한 플래그를 사용 하 여는 [SccAdd](../extensibility/sccadd-function.md)합니다.  
  
|플래그|값|설명|  
|---------|-------|--------|  
|`SCC_FILETYPE_AUTO`|0 x 00|소스 제어 플러그 인은 텍스트 또는 이진 인지를 자동으로 검색 해야 합니다.|  
|`SCC_FILETYPE_TEXT`|0x01|파일 형식은 텍스트입니다.|  
|`SCC_FILETYPE_BINARY`|0 x 04|이진 파일 형식이입니다. **Note:**  `SCC_FILETYPE_TEXT` 및 `SCC_FILETYPE_BINARY` 플래그는 함께 사용할 수 없습니다. 정확히 하나 또는 둘 다 설정 합니다.|  
|`SCC_ADD_STORELATEST`|0x02|최신 버전 \(델타 제외\)만 저장 합니다.|  
  
## 비교 플래그  
 [SccDiff](../extensibility/sccdiff-function.md) 이러한 플래그를 사용 하 여 비교 작업의 범위를 정의 합니다.`SCC_DIFF_QD_xxx` 플래그는 함께 사용할 수 없습니다. 그 중 하나를 지정 하는 경우 제공 될 시각적 알려가 됩니다. "빠른 diff"에서 \(QD\) 플러그 인이 결정 하지 파일은 다른 경우에 다른 방법입니다. 물론 이러한 플래그 지정 되 면 "시각적 diff" 수행 됩니다. 자세한 파일 차이 계산 하 고 표시 합니다. 요청한 QD 지원 되지 않는 경우, 다음 가장 적합 한 플러그 인 이동 합니다. 예를 들어, IDE는 체크섬을 요청 하는 경우 플러그 인이 지원 하지 플러그 인은 전체 내용이 확인 \(여전히 보다 훨씬 더 빠르게 시각적 표시\).  
  
|플래그|값|설명|  
|---------|-------|--------|  
|`SCC_DIFF_IGNORECASE`|0x0002|대\/소문자 차이 무시 합니다.|  
|`SCC_DIFF_IGNORESPACE`|0x0004|공백 차이 무시 합니다. **Note:**  `SCC_DIFF_IGNORECASE` 및 `SCC_DIFF_IGNORESPACE` 플래그는 선택 사항 비트입니다.|  
|`SCC_DIFF_QD_CONTENTS`|0x0010|전체 파일의 내용을 비교 하 여 QD 합니다.|  
|`SCC_DIFF_QD_CHECKSUM`|0x0020|체크섬으로 QD 합니다.|  
|`SCC_DIFF_QD_TIME`|0x0040|날짜\/시간 스탬프를 파일에 의해 QD 합니다.|  
|`SCC_DIFF_QUICK_DIFF`|0x0070|모든 QD 비트를 확인 하는 데 사용 하는 마스크입니다. 함수에 전달 되지 않습니다. 세 가지 QD 비트는 함께 사용할 수 없습니다. 항상 QD ui 없는 디스플레이 의미합니다.|  
  
## PopulateList 플래그  
 이 플래그는 사용 하 여는 [SccPopulateList](../extensibility/sccpopulatelist-function.md) 에 `fOptions` 매개 변수입니다.  
  
|플래그|값|설명|  
|---------|-------|--------|  
|`SCC_PL_DIR`|0x00000001L|IDE는 파일이 아닌 디렉터리를 전달 합니다.|  
  
## PopulateDirList 플래그  
 이러한 플래그를 사용 하 여는 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) 에 `fOptions` 매개 변수입니다.  
  
|옵션 값|값|설명|  
|----------|-------|--------|  
|SCC\_PDL\_ONELEVEL|0x0000|한 수준의 디렉터리 \(기본값은\)에 대 한 디렉터리를 검사 합니다.|  
|SCC\_PDL\_RECURSIVE|0x0001|재귀적으로 지정 된 각 디렉터리 아래에 있는 모든 디렉터리를 검사 합니다.|  
|SCC\_PDL\_INCLUDEFILES|0x0002|검사 프로세스에서 파일 이름을 포함 합니다.|  
  
## OpenProject 플래그  
 이러한 플래그를 사용 하 여는 [SccOpenProject](../extensibility/sccopenproject-function.md) 에 `dwFlags` 매개 변수입니다.  
  
|옵션 값|값|설명|  
|----------|-------|--------|  
|SCC\_OP\_CREATEIFNEW|0x00000001L|프로젝트 소스 제어에 없으면 만듭니다. 이 플래그가 설정 되지 않은 경우 메시지를 만드는 프로젝트에 대 한 사용자 \(하지 않는 한 `SCC_OP_SILENTOPEN` 플래그를 지정\).|  
|SCC\_OP\_SILENTOPEN|0x00000002L|사용자에 게; 프로젝트를 만들려면 반환 `SCC_E_UNKNOWNPROJECT`합니다.|  
  
## 플래그 가져오기  
 이러한 플래그를 사용 하 여는 [SccGet](../extensibility/sccget-function.md) 및 [SccCheckout](../extensibility/scccheckout-function.md)합니다.  
  
|플래그|값|설명|  
|---------|-------|--------|  
|`SCC_GET_ALL`|0x00000001L|IDE 디렉터리를 전달 하는, 파일이 아닌: 이러한 디렉터리에 모든 파일을 가져옵니다.|  
|`SCC_GET_RECURSIVE`|0x00000002L|디렉터리를 전달 하는 IDE: 이러한 디렉터리 및 모든 하위 디렉터리를 가져옵니다.|  
  
## nOption 값  
 이러한 플래그를 사용 하 여는 [SccSetOption](../extensibility/sccsetoption-function.md) 에 `nOption` 매개 변수입니다.  
  
|플래그|값|설명|  
|---------|-------|--------|  
|`SCC_OPT_EVENTQUEUE`|0x00000001L|이벤트 큐의 상태를 설정 합니다.|  
|`SCC_OPT_USERDATA`|0x00000002L|사용자 데이터에 대 한 지정 `SCC_OPT_NAMECHANGEPFN`합니다.|  
|`SCC_OPT_HASCANCELMODE`|0x00000003L|IDE 취소 처리할 수 있습니다.|  
|`SCC_OPT_NAMECHANGEPFN`|0x00000004L|이름 변경에 대 한 콜백을 설정 합니다.|  
|`SCC_OPT_SCCCHECKOUTONLY`|0x00000005L|소스 제어 플러그 인 UI 체크 아웃을 사용 하지 않도록 설정 하 고 작업 디렉터리를 설정 하지 마십시오.|  
|`SCC_OPT_SHARESUBPROJ`|0x00000006L|작업 디렉터리를 지정 하려면 소스 제어 시스템에서 추가 합니다. 직계 하위 항목 있으면 연결된 된 프로젝트를 공유 하려고 합니다.|  
  
## dwVal 비트  
 이러한 플래그를 사용 하 여는 [SccSetOption](../extensibility/sccsetoption-function.md) 에 `dwVal` 매개 변수입니다.  
  
|플래그|값|설명|사용 하는 `nOption` 값|  
|---------|-------|--------|-----------------------|  
|`SCC_OPT_EQ_DISABLE`|0x00L|이벤트 큐 작업을 일시 중단합니다.|`SCC_OPT_EVENTQUEUE`|  
|`SCC_OPT_EQ_ENABLE`|0x01L|이벤트 큐 로깅을 사용합니다.|`SCC_OPT_EVENTQUEUE`|  
|`SCC_OPT_HCM_NO`|0 L|\(기본값\) 어떠한 취소 모드입니다. 필요한 경우 플러그 인이 제공 해야 합니다.|`SCC_OPT_HASCANCELMODE`|  
|`SCC_OPT_HCM_YES`|1 L|IDE는 취소를 처리합니다.|`SCC_OPT_HASCANCELMODE`|  
|`SCC_OPT_SCO_NO`|0 L|\(기본값\) 플러그 인 UI;에서 체크 아웃 확인 작업 디렉터리 설정 됩니다.|`SCC_OPT_SCCCHECKOUTONLY`|  
|`SCC_OPT_SCO_YES`|1 L|즉, 없음 플러그 인 UI 체크 아웃 작업 디렉터리가 없습니다.|`SCC_OPT_SCCCHECKOUTONLY`|  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)