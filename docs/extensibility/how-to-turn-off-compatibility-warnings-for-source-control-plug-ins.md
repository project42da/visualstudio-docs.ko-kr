---
title: "소스 제어 플러그 인에 대 한 호환성 경고 해제 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
caps.latest.revision: 21
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d5bc147592bfc36247c35f23ac2885055d096af3
ms.openlocfilehash: e1dda3bd8c41efcf74a1b27f764fdfbf817f8d63
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>방법: 소스 제어 플러그 인에 대 한 호환성 경고 해제
사용자에서 소스 제어를 적용 하는 경우 몇 가지 호환성 경고를 볼 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 표시 하는 경고 소스 제어 플러그 인의 기능에 좌우 되며 자세한 다음과 같이 비활성화할 수 있습니다.  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>이 경고를 사용 하지 않도록 설정 하려면: "최적의 소스 제어 통합 하려면 Visual studio..."  
  
-   다음 레지스트리 항목 (필요한 경우 값 추가)를 설정 합니다.  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = dword:&00000;001  
  
     이 경고는 모든 표시는 비-[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] 플러그 인입니다.  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>이 경고를 사용 하지 않도록 설정 하려면: "설치 된 소스 제어 공급자는 모든 기능...을 지원 하지 않습니다"  
  
-   (필요한 경우 값 추가) 다음 두 레지스트리 값을 설정 합니다.  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = dword:&00000;000  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = dword:&00000;001  
  
     이 경고는 소스 제어 플러그 인 지원 하지 않는 경우 명시적으로 재진입 여러 프로젝트에 대 한 (즉, 하는 경우 한 번에 하나의 파일 및 프로젝트에서 확인 가능)에 표시 됩니다.  
  
     재진입을 지원 하는 것이 좋습니다 (`SCC_CAP_REENTRANT` 기능);이 경고가 제거 됩니다. 그러나 이러한 지원이 불가능 이러한 레지스트리 항목을 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [기능 플래그](../extensibility/capability-flags.md)
