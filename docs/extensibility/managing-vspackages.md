---
title: "Vspackage 관리 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
caps.latest.revision: 35
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
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 32e4aa4302f7871e71907d094c12038b00d7e6bb
ms.lasthandoff: 02/22/2017

---
# <a name="managing-vspackages"></a>Vspackage를 관리합니다.
대부분의 경우에서 프로젝트 및 항목 템플릿을 등록 하 고 패키지를 자동으로 로드 되므로 Vspackage, 관리에 신경 쓸 필요가 없습니다. 그러나 경우에 따라 패키지를 관리 하기 위해 좀 더 자세한 내용을 알아보려면 할 수 있습니다.  
  
## <a name="using-the-experimental-instance"></a>실험적 인스턴스를 사용 하 여  
 실험적 인스턴스에서 대 한 자세한 내용을 참조 하십시오 [의 실험적 인스턴스에서](../extensibility/the-experimental-instance.md)합니다.  
  
## <a name="registering-and-unregistering-vspackages"></a>Vspackage를 등록 및 등록 취소  
 등록 및 Vspackage 및 기타 유형의 확장을 등록 취소 하는 방법을 알아보려면 참조 [등록 및 등록 취소 Vspackage](../extensibility/registering-and-unregistering-vspackages.md)합니다.  
  
## <a name="loading-a-vspackage"></a>VSPackage를 로드합니다.  
 Vspackage는 CMDUICONTEXT GUID 켜져 특정 자동 로드를 설정할 수 있습니다. 자세한 내용은 참조 [로드 Vspackage](../extensibility/loading-vspackages.md)합니다.  
  
## <a name="using-asyncpackage-to-load-vspackages-in-the-background"></a>AsyncPackage를 사용 하 여 백그라운드에서 Vspackage를 로드할 수  
 AsyncPackage 클래스에는 Visual Studio에서 더 나은 UI 응답성에 대 한 백그라운드 스레드에서 로드 패키지 수 있습니다. 자세한 내용은 참조 [하는 방법: 백그라운드에서 로드 Vspackage를 사용 하 여 AsyncPackage](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md)합니다.  
  
## <a name="rule-based-ui-context-for-extensions"></a>확장에 대 한 규칙 기반 UI 컨텍스트  
 규칙 기반 UI 컨텍스트는 UI 컨텍스트의 활성화 되 고 관련된 Vspackage 로드 정확한 조건을 정의 하려면 확장 만든을 수 있습니다. 자세한 내용은 참조 [하는 방법: Visual Studio 확장에 대 한 UI 컨텍스트를 사용 하 여 규칙 기반](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md)합니다.  
  
## <a name="diagnosing-extension-performance"></a>확장 성능 진단  
확장 시작 및 솔루션 로드 성능에 영향을 줄 수 있습니다. Visual Studio 확장 영향 계산 되는 방법 및 어떻게 분석할 수 있습니다 로컬로 확장 확장에 영향을 미치는 성능으로 표시 될 수 있는지 테스트에 대해 알아봅니다. 자세한 내용은 참조 [하는 방법: 확장 성능 진단](how-to-diagnose-extension-performance.md)합니다. 
  
## <a name="troubleshooting-vspackages"></a>Vspackage 문제 해결  
 Vspackage 로드 안 함 또는 오류가 발생 하는 문제 해결을 위한 기술을 확인: [Vspackage 문제 해결](../extensibility/troubleshooting-vspackages.md)  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage](../extensibility/internals/vspackages.md)
