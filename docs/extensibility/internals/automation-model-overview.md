---
title: "자동화 모델 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], about automation
- extensibility
ms.assetid: 12b6d6db-0d22-4aaa-aa7d-1365f759b7b0
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 208357343a3e77e29b1dc0a98b6159c5ac3f957e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="automation-model-overview"></a>자동화 모델 개요
자동화 모델 된 Visual Studio 추가 기능을 이나 확장을 작성할 수 있습니다 하는 개체의 집합으로 구성 됩니다. 추가 기능에 Visual Studio 환경을 조작 하 고 일반적인 작업을 자동화할 수 있는 응용 프로그램. Visual Studio 확장 Visual Studio의 사용자 지정 구성 요소를 만들 수도 있고 텍스트 편집기와 같은 표준 구성 요소 기능에 추가 됩니다.  
  
## <a name="objects-in-the-automation-model"></a>자동화 모델의 개체  
 관련 된 일반적인 환경의 주요 측면을 제어 하는 개체 그룹의 자동화 모델 구성 됩니다. 다음은 다양 한 자동화 모델을 구성 하는 개체를 보여 주는 다이어그램입니다.  
  
 ![Visual Studio 자동화 개체 차트](../../extensibility/internals/media/vsvisualstudioautomationobjectchart.gif "vsVisualStudioAutomationObjectChart")  
Visual Studio 자동화 개체  
  
 자세한 내용은 참조 [Visual Studio 환경 확장](http://msdn.microsoft.com/Library/4173a963-7ac7-4966-9bb7-e28a9d9f6792)합니다.  
  
 환경의 여러 기능 영역에 대 한 모델을 제공 합니다. 예를 들어, 코드에서 찾을 수 있는 다양 한 요소에 대 한 코드 모델이 됩니다. 다양 한 문서 요소에 대 한 문서 모델이 있습니다. 프로젝트 영역을 한 곳 VSPackage 공급자에 게 특히 관심 사항입니다. 새 프로젝트 형식을 자동화 모델에 영향을 거의 동일한 방법으로 설정할 수 있습니다 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 자동화 모델에 기여 합니다. 프로세스에 설명 된 [Vspackage에 대 한 자동화 제공](../../extensibility/internals/providing-automation-for-vspackages.md)합니다.  
  
 환경의 자동화 모델 확장를 고려할 수 있는 위치:  
  
-   프로젝트  
  
-   문서  
  
-   코드  
  
-   빌드  
  
 자동화에 대 한 자세한 내용은 참조 하십시오. [Visual Studio의 자동화 및 확장성](http://msdn.microsoft.com/Library/f71a2253-3e68-4e5e-9a18-edbba816caf6)합니다. 이 문서와 문서 VSPackage에 대 한 자동화를 제공 해야 하는 방법에 관한 결정을 내릴 수에 대 한 링크를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 추가 기능 만들기](http://msdn.microsoft.com/Library/50be56d2-e3a5-4cd2-8569-2a0666b268ce)