---
title: "마법사 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], providing wizard support
ms.assetid: 59d9a77f-ee80-474b-a14f-90f477ab717b
caps.latest.revision: 13
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
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: af0466ea3c11b75090e45cb9b408ed0723cd8a6f
ms.lasthandoff: 02/22/2017

---
# <a name="wizards"></a>마법사
마법사를 만든 후 일반적으로 원하는에 추가 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다른 사용자가 사용할 수 있도록 IDE (개발 환경)를 통합 합니다. 그러면 추가 마법사에 표시 된 **새 프로젝트 추가** 또는 **새 항목 추가** 대화 상자. 참조 하는 **새 프로젝트 추가** 또는 **새 항목 추가** 대화 상자에서 열려 있는 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**, 가리킨 **추가**, 클릭 하 고 **새 프로젝트** 또는 **새 항목**합니다.  
  
 마법사에서 구현할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자가 열 때 사용 가능한 값의 트리 뷰에서 선택는 **새 프로젝트 추가** 대화 상자 또는 **새 항목 추가** 대화 상자 또는 항목에 오른쪽 클릭 하면 **솔루션 탐색기**.  
  
 마법사에서 ite, 새 프로젝트의 이름을 지역화 하는 옵션을 제공할 수 있습니다 하 고 마법사를 선택할 때 사용자가 표시 됩니다 아이콘을 결정할 수 있습니다. 사용 가능한 다른 항목을 기준으로 새 항목이 표시 되는 순서를 제어할 수도 있습니다. 항목은 사전순으로 구성 될 필요가 없습니다.  
  
 마법사를 열 때 전달 되는 사용자 지정 매개 변수에 따라 다르게 시작 하는 마법사를 제공할 수 있습니다.  
  
 이 섹션의 항목을 구현 하는 파일에 설명 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **새 프로젝트 추가** 및 **새 항목 추가** 대화 상자를 사용할 수 있는 마법사와 템플릿 및 마법사에 IDE에서 제대로 작동 하기 위해 충족 해야 하는 요구 사항 간에 마법사에 나열 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [서식 파일 디렉터리 설명 (합니다. Vsdir) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)  
 어떤 서식 파일에 대해 간략하게 설명 파일 디렉터리를 제공 하 고 폴더, 마법사.vsz 파일 및 대화 상자에서 프로젝트와 연결 된 템플릿 파일을 표시 하려면 IDE에서 작동 방법을 설명 합니다.  
  
 [마법사 (합니다. Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)  
 IDE에서 마법사를 시작 하는 방법에 대해 설명 하 고.vsz 파일의 세 부분을 나열 합니다.  
  
 [마법사 인터페이스 (IDTWizard)](../../extensibility/internals/wizard-interface-idtwizard.md)  
 설명의 `IDTWizard` 마법사 IDE에서 작업을 구현 해야 하는 인터페이스입니다.  
  
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)  
 마법사의 구현 방식 및 IDE 구현에 컨텍스트 매개 변수를 전달할 때 발생 하는 상황에 대해 설명 합니다.  
  
 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)  
 사용자 지정 매개 변수를 사용 하 여 마법사를 시작한 후 마법사의 작업을 제어 하는 방법에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 새 프로젝트 형식을 디자인 하는 방법에 대 한 정보를 제공 하는 추가 항목 링크를 제공 합니다.  
  
 [연습: 마법사 만들기](http://msdn.microsoft.com/Library/adb41fe9-fcca-4e87-bf4f-bf2fa68e8b06)  
 마법사를 만드는 방법을 보여 줍니다.  
  
 [프로젝트 확장](../../extensibility/extending-projects.md)  
 사용 하는 방법에 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 및 솔루션 코드 파일 및 리소스 파일 및 소스 제어를 구현 하는 방법을 구성할 수 있습니다.
