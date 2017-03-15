---
title: "종속성 다이어그램을 확장 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
ms.assetid: 83fca301-b008-485a-87eb-218050e71451
caps.latest.revision: 39
author: alexhomer1
ms.author: ahomer
manager: douge
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3d07f82ea737449fee6dfa04a61e195654ba35fa
ms.openlocfilehash: ad673b1bc7d3089c37717dd7e1f1fce4e86d8100
ms.lasthandoff: 02/22/2017

---
# <a name="extend-dependency-diagrams"></a>종속성 다이어그램을 확장 합니다.
만들고 종속성 다이어그램을 업데이트 하 고 Visual Studio에서 종속성 다이어그램에 대해 프로그램 코드의 구조를 확인 하는 코드를 작성할 수 있습니다. 다이어그램의 바로 가기(상황에 맞는) 메뉴에 표시되는 명령을 추가하고, 끌어서 놓기 제스처를 사용자 지정하고, 텍스트 템플릿에서 레이어 모델에 액세스할 수 있습니다. 이러한 확장을 VSIX(Visual Studio Integration Extension)로 패키징하고 다른 Visual Studio 사용자에게 배포할 수 있습니다.  
  
 종속성 다이어그램에 대 한 자세한 내용은 다음을 참조 합니다.  
  
-   [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)  
  
-   [종속성 다이어그램: 지침](../modeling/layer-diagrams-guidelines.md)  
  
-   [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [종속성 다이어그램을 사용 하 여 코드의 유효성을 검사합니다](../modeling/validate-code-with-layer-diagrams.md)  
  
##  <a name="a-nameprereqsa-requirements"></a><a name="prereqs"></a> 요구 사항  
 레이어 확장을 개발하려는 컴퓨터에 다음이 설치되어 있어야 합니다.  
  
-   Visual Studio  
  
-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md)  
  
-   Visual Studio 용 모델링 SDK  


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

  
 레이어 확장을 실행하려는 컴퓨터에 적합한 버전의 Visual Studio가 설치되어 있어야 합니다. 자세한 내용은 참조 [레이어 모델 확장을 배포](../modeling/deploy-a-layer-model-extension.md)합니다.  
  
 종속성 다이어그램을 지 원하는 Visual Studio의 버전을 확인 하려면 참조 [아키텍처 및 모델링 도구에 대 한 버전 지원](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [종속성 다이어그램에 명령 및 제스처 추가](../modeling/add-commands-and-gestures-to-layer-diagrams.md)  
  
 [종속성 다이어그램에 사용자 지정 아키텍처 유효성 검사 추가](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)  
  
 [종속성 다이어그램에 사용자 지정 속성 추가](../modeling/add-custom-properties-to-layer-diagrams.md)  
  
 [프로그램 코드에서 레이어 모델 탐색 및 업데이트](../modeling/navigate-and-update-layer-models-in-program-code.md)  
  
 [레이어 모델 확장 배포](../modeling/deploy-a-layer-model-extension.md)  
  
 [종속성 다이어그램의 확장 문제 해결](../modeling/troubleshoot-extensions-for-layer-diagrams.md)  
  
## <a name="see-also"></a>참고 항목  
 [모델링 확장 정의 및 설치](../modeling/define-and-install-a-modeling-extension.md)   
 [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)   
 [종속성 다이어그램: 지침](../modeling/layer-diagrams-guidelines.md)   
 [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)   
 [종속성 다이어그램을 사용 하 여 코드의 유효성을 검사합니다](../modeling/validate-code-with-layer-diagrams.md)   

