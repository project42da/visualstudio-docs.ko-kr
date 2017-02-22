---
title: "POPLISTFUNC | Microsoft Docs"
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
  - "POPDIRLISTFUNC"
helpviewer_keywords: 
  - "POPLISTFUNC 콜백 함수"
ms.assetid: b2199fd5-d707-4628-92dd-e2a01e2f507a
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# POPLISTFUNC
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 콜백은에 제공 되는 [SccPopulateList](../extensibility/sccpopulatelist-function.md) IDE에 의해 소스 제어 플러그 인 파일 또는 디렉터리 목록을 업데이트 하는 데 사용 됩니다 \(에 제공 되는 `SccPopulateList` 함수\).  
  
 사용자가 선택 하는 경우는 **가져오기** 사용자를 가져올 수 있는 모든 파일의 목록 상자를 표시 하는 IDE IDE에 명령 합니다. 아쉽게도 IDE 모르는 사용자가 될 수 있습니다; 모든 파일의 정확한 목록 만 플러그 인이 목록을 있습니다. 다른 사용자가 파일을 소스 코드 제어 프로젝트에 추가한 경우 이러한 파일의 목록에 나타나야 합니다. 하지만 IDE에 대 한 알 수 없습니다. IDE는 것으로 생각 하는 사용자를 가져올 수 있는 파일의 목록을 작성 합니다. 이 목록을 사용자에 게 표시 하기 전에 호출 된 [SccPopulateList](../extensibility/sccpopulatelist-function.md)`,` 소스 제어 플러그 인을 제공 기회를 추가 하 고 목록에서 파일을 삭제 합니다.  
  
## Signature  
 다음과 같은 프로토타입으로 IDE 구현 함수를 호출 하 여 목록을 수정 하는 소스 제어 플러그 인:  
  
```cpp#  
typedef BOOL (*POPLISTFUNC) ( LPVOID pvCallerData, BOOL fAddRemove, LONG nStatus, LPSTR lpFileName );  
```  
  
## 매개 변수  
 pvCallerData  
 `pvCallerData` \(IDE\)는 호출자에 의해 전달 매개 변수는 [SccPopulateList](../extensibility/sccpopulatelist-function.md)합니다. 소스 제어 플러그 인이 매개 변수 내용에 대해 아무 것도 가정해 야 합니다.  
  
 fAddRemove  
 경우 `TRUE`, `lpFileName` 파일이 파일 목록에 추가 해야 합니다. 경우 `FALSE`, `lpFileName` 파일이 파일 목록에서 삭제 해야 합니다.  
  
 nStatus  
 상태 `lpFileName` \(의 조합 된 `SCC_STATUS` 비트; 참조 [파일 상태 코드](../extensibility/file-status-code-enumerator.md) 대 한 자세한 내용은\).  
  
 lpFileName  
 디렉터리의 전체 경로를 추가 하거나 목록에서 삭제할 파일 이름입니다.  
  
## 반환 값  
  
|값|설명|  
|-------|--------|  
|`TRUE`|플러그 인 수 계속 해 서이 함수를 호출 합니다.|  
|`FALSE`|IDE 면 \(예: 메모리 문제 부족\)에 문제가 발생이 했습니다. 플러그 인 작업을 중지 해야 합니다.|  
  
## 설명  
 전달이 함수는 소스 제어 플러그 인을 추가 하거나 파일 목록에서 삭제 하려는 각 파일에 대 한 호출의 `lpFileName`합니다.`fAddRemove` 플래그 목록에 추가할 새 파일 또는 삭제 하려면 이전 파일을 나타냅니다.`nStatus` 매개 변수는 파일의 상태를 제공 합니다. 반환 하는 소스 코드 제어 플러그 인 추가 및 파일 삭제를 완료 하면는 [SccPopulateList](../extensibility/sccpopulatelist-function.md) 를 호출 합니다.  
  
> [!NOTE]
>  `SCC_CAP_POPULATELIST` 기능 비트는 Visual Studio에 필요 합니다.  
  
## 참고 항목  
 [IDE에 의해 구현 되는 콜백 함수](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)   
 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)