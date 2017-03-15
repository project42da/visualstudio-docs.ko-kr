---
title: "도움말 콘텐츠 관리자 재정의 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 95fe6396-276b-4ee5-b03d-faacec42765f
caps.latest.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# 도움말 콘텐츠 관리자 재정의
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

레지스트리를 수정하여 Visual Studio IDE에서 도움말 뷰어와 도움말 관련 기능의 기본 동작을 변경할 수 있습니다.  
  
|작업|레지스트리 키|값 및 정의|  
|--------|-------------|------------|  
|고유한 서비스 끝점 정의|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VSWinExpress\\14.0\\Help|NewContentAndUpdateService\-\-*HTTPValueForTheServiceEndpoint*.|  
|온라인\/오프라인 기본값 정의|HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VSWinExpress\\14.0\\help|UseOnlineHelp\-\-로컬 도움말을 지정하려면 `0`을 입력하고 온라인 도움말을 지정하려면 `1`을 입력합니다.|  
|고유한 F1 끝점 정의|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VSWinExpress\\14.0\\Help|OnlineBaseUrl\-\-*HTTPValueForTheServiceEndpoint*|  
|BITS 작업 우선 순위 재정의|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\(64비트 컴퓨터에서\)\\Microsoft\\Help\\v2.2|BITSPriority\-\-**foreground**, **high**, **normal** 또는 **low** 값 중 하나를 사용합니다.|  
|온라인\(및 IDE 온라인 옵션\) 사용 안 함|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node \(on a 64\-bit machine\)\\Microsoft\\VisualStudio\\14.0\\Help|OnlineHelpPreferenceDisabled\-\-온라인 도움말 콘텐츠에 액세스할 수 없도록 설정하려면 1로 설정합니다.|  
|콘텐츠 관리 사용 안 함|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node \(on a 64\-bit machine\)\\Microsoft\\VisualStudio\\14.0\\Help|ContentManagementDisabled\-\-도움말 뷰어에서 **콘텐츠 관리** 탭을 사용하지 않도록 설정하려면 1로 설정합니다.|  
|네트워크 공유의 로컬 콘텐츠 저장소 가리키기|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Help\\v2.2\\Catalogs\\VisualStudio11|LocationPath\=”*ContentStoreNetworkShare*”|  
|Visual Studio 처음 시작 시 콘텐츠 설치 기능 사용 안 함|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node \(on a 64\-bit machine\)\\Microsoft\\VisualStudio\\14.0\\Help|DisableFirstRunHelpSelection\-\-Visual Studio가 처음으로 시작될 때 구성된 도움말 기능을 사용하지 않도록 설정하려면 1로 설정합니다.|  
  
## 참고 항목  
 [도움말 뷰어 관리자 가이드](../ide/help-viewer-administrator-guide.md)