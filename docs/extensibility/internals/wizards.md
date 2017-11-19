---
title: "마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: projects [Visual Studio SDK], providing wizard support
ms.assetid: 59d9a77f-ee80-474b-a14f-90f477ab717b
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 838b7cac850b8e7eb3401065cf13202d3a3a40ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="wizards"></a>마법사
일반적으로에 추가 하려면 마법사를 만든 후의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다른 사용자가 사용할 수 있도록 통합 개발 환경 (IDE). 그러면 추가 마법사에 표시 된 **새 프로젝트 추가** 또는 **새 항목 추가** 대화 상자. 참조 하는 **새 프로젝트 추가** 또는 **새 항목 추가** 대화 상자에서 열린 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**, 가리킨 **추가**, 및 클릭 **새 프로젝트** 또는 **새 항목**합니다.  
  
 마법사에서 구현할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자가을 열 때 사용 가능한 값의 트리 보기에서 선택는 **새 프로젝트 추가** 대화 상자 또는 **새 항목 추가** 대화 상자 또는 오른쪽 클릭은 에 있는 항목 **솔루션 탐색기**합니다.  
  
 프로그램 마법사에서 새 프로젝트 또는 ites, 이름을 지역화 하는 옵션을 제공할 수 있습니다 하 고 사용자가 마법사를 선택할 때 표시 되는 아이콘을 확인할 수 있습니다. 사용 가능한 다른 항목을 기준으로 새 항목이 나타나는 순서를 제어할 수도 있습니다. 항목은 사전순으로 구성 될 필요가 없습니다.  
  
 요청이 시작 되 면 마법사에 전달 되는 사용자 지정 매개 변수에 따라 다르게 시작 하는 마법사를 제공할 수도 있습니다.  
  
 이 섹션의 항목을 구현 하는 파일에 설명 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **새 프로젝트 추가** 및 **새 항목 추가** 마법사를 사용할 수 있는 마법사 및 서식 파일을 나열 하려면 대화 상자 및 IDE에서 제대로 작동 하도록 마법사를 충족 해야 하는 요구 사항입니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [템플릿 디렉터리 설명(.Vsdir) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)  
 디렉터리 설명 파일 어떤 서식 파일의 개요를 제공 하 고 폴더, 마법사.vsz 파일 및 대화 상자에서 프로젝트와 연결 된 템플릿 파일을 표시 하려면 IDE에서 작동 방식을 설명 합니다.  
  
 [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)  
 IDE가 마법사를 시작 하는 방법을 설명 하 고.vsz 파일의 세 부분을 나열 합니다.  
  
 [마법사 인터페이스(IDTWizard)](../../extensibility/internals/wizard-interface-idtwizard.md)  
 설명의 `IDTWizard` 마법사 IDE에서 작동 하도록 구현 해야 하는 인터페이스입니다.  
  
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)  
 마법사를 구현 하는 방법 및 IDE 구현에 컨텍스트 매개 변수를 전달할 때 발생 하는 상황에 대해 설명 합니다.  
  
 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)  
 사용자 지정 매개 변수를 사용 하 여 마법사를 시작한 후에 마법사의 작업을 제어 하는 방법에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 새 프로젝트 형식을 디자인 하는 방법에 대 한 정보를 제공 하는 추가 항목 링크를 제공 합니다.  
  
 [연습: 만들기 마법사](http://msdn.microsoft.com/Library/adb41fe9-fcca-4e87-bf4f-bf2fa68e8b06)  
 마법사를 만드는 방법을 보여 줍니다.  
  
 [프로젝트 확장](../../extensibility/extending-projects.md)  
 사용 하는 방법에 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 및 솔루션 코드 파일 및 리소스 파일 및 소스 제어를 구현 하는 방법을 구성할 수 있습니다.