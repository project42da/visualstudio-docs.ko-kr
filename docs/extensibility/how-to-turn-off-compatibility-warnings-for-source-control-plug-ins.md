---
title: 소스 제어 플러그 인에 대 한 호환성 경고를 해제 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2d3cffbd6a8b6c21aa6e958495b88eb51a5724a5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>방법: 소스 제어 플러그 인에 대 한 호환성 경고를 해제
사용자의 소스 제어를 적용 하는 경우 몇 가지 호환성 경고를 표시 될 수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 제공 경고 소스 제어 플러그 인의 기능에 좌우 되며 자세한 다음과 같이 비활성화할 수 있습니다.  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>경고를 사용 하지 않도록 설정 하려면: "... Visual Studio와 함께 최적의 소스 제어 통합 되도록"  
  
-   다음 레지스트리 항목 (필요한 경우 값 추가)을 설정 합니다.  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = dword: 00000001  
  
     모든에 대해이 경고를 표시 하는 비-[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] 플러그 인 합니다.  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>경고를 사용 하지 않도록 설정 하려면: "설치한 소스 제어 공급자는 모든 기능...을 지원 하지 않습니다"  
  
-   (필요한 경우 값 추가) 다음과 같은 두 개의 레지스트리 값을 설정 합니다.  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = dword: 00000000  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = dword: 00000001  
  
     이 경고는 소스 제어 플러그 인에서 지원 하지 않으면 명시적으로 재진입 여러 프로젝트에 대 한 (즉, 하는 경우 한 번에 하나의 파일 및 프로젝트에서 확인할 수)에 표시 됩니다.  
  
     재입력을 지 원하는 것이 좋습니다 (`SCC_CAP_REENTRANT` 기능);이 경고가 제거 됩니다. 그러나이 지원 되지 않습니다, 이러한 레지스트리 항목을 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [기능 플래그](../extensibility/capability-flags.md)