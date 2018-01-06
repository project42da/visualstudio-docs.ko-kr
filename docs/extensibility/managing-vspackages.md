---
title: "관리 Vspackage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3c3201c032d0cae645460e614b6d4138297e4a93
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="managing-vspackages"></a>Vspackage를 관리합니다.
대부분의 경우에서 프로젝트 및 항목 템플릿을 등록 하 고 패키지를 자동으로 로드 되므로 Vspackage, 관리 하는 방법에 대 한 걱정할 필요가 없습니다. 그러나 일부 경우에 패키지를 관리 하기 위해 좀 더 자세한 내용을 보려면 할 수 있습니다.  
  
## <a name="using-the-experimental-instance"></a>실험적 인스턴스를 사용 하 여  
 실험적 인스턴스에 대 한 자세한 참조 [의 실험적 인스턴스](../extensibility/the-experimental-instance.md)합니다.  
  
## <a name="registering-and-unregistering-vspackages"></a>Vspackage를 등록 및 등록 취소  
 등록 하 고 Vspackage 및 다른 형식의 확장명 등록을 취소 하는 방법을 알아보려면 참조 [등록 및 등록 취소 Vspackage](../extensibility/registering-and-unregistering-vspackages.md)합니다.  
  
## <a name="loading-a-vspackage"></a>VSPackage를 로드합니다.  
 Vspackage는 CMDUICONTEXT GUID 켜져 특정 autoload를 설정할 수 있습니다. 자세한 내용은 참조 [로드 Vspackage](../extensibility/loading-vspackages.md)합니다.  
  
## <a name="using-asyncpackage-to-load-vspackages-in-the-background"></a>AsyncPackage를 사용 하 여 백그라운드에서 Vspackage를 로드 하지  
 AsyncPackage 클래스에는 Visual Studio에서 UI 응답성 향상에 대 한 백그라운드 스레드에서 로드 패키지가 수 있습니다. 자세한 내용은 참조 [하는 방법: 백그라운드에서 로드 Vspackage를 사용 하 여 AsyncPackage](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md)합니다.  
  
## <a name="rule-based-ui-context-for-extensions"></a>확장에 대 한 규칙 기반 UI 컨텍스트  
 규칙 기반 UI 컨텍스트 확장 작성자를는 UI 컨텍스트가 활성화 되 고 관련된 Vspackage 로드 정확한 조건을 정의할 수 있습니다. 자세한 내용은 참조 [하는 방법: Visual Studio 확장에 대 한 UI 컨텍스트를 사용 하 여 규칙 기반](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md)합니다.  
  
## <a name="diagnosing-extension-performance"></a>확장 성능 진단  
확장 시작 및 솔루션 로드 성능에 영향을 줄 수입니다. Visual Studio 확장 impact는 어떻게 계산 방법을 분석할 수 있습니다 로컬로 확장 확장에 영향을 주지 성능으로 표시 될 수 있는 경우에 테스트에 대해 알아봅니다. 자세한 내용은 참조 [하는 방법: 확장 성능 진단](how-to-diagnose-extension-performance.md)합니다. 
  
## <a name="troubleshooting-vspackages"></a>Vspackage를 문제 해결  
 로드 되지 않은 또는 오류가 발생 하는 Vspackage의 문제를 해결 하는 기술을 확인: [Vspackage 문제 해결](../extensibility/troubleshooting-vspackages.md)  
  
## <a name="see-also"></a>참고 항목  
 [VSPackage](../extensibility/internals/vspackages.md)