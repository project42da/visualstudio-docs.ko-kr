---
title: "Visual Studio에서 프로젝트 및 항목 템플릿에 이름 매개 변수 추가 | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- template parameters
- template parameters, substituting
- Visual Studio templates, using parameters
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ecdd277a36cb1c074653edb2af7f1882e6d25ede
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-substitute-parameters-in-a-template"></a>방법: 템플릿 매개 변수 대체

템플릿으로 파일을 만들 때 템플릿 매개 변수를 사용하여 클래스 이름 및 네임스페이스와 같은 식별자를 바꿀 수 있습니다. 기존 템플릿에 템플릿 매개 변수를 추가하거나, 템플릿 매개 변수를 사용하여 템플릿을 직접 만들 수 있습니다.

템플릿 매개 변수는 $*parameter*$ 형식으로 작성됩니다. 템플릿 매개 변수의 전체 목록은 [템플릿 매개 변수](../ide/template-parameters.md)를 참조하세요.

다음 섹션에서는 네임스페이스의 이름을 "안전한 프로젝트 이름"으로 바꾸도록 템플릿을 수정하는 방법을 보여 줍니다.

## <a name="to-use-a-parameter-to-replace-the-namespace-name"></a>매개 변수를 사용하여 네임스페이스 이름을 바꾸려면

1. 템플릿의 하나 이상 코드 파일에 매개 변수를 삽입합니다. 예:

    ```csharp
    namespace $safeprojectname$
    ```

1. 템플릿에 대한 .vstemplate 파일에서 이 파일을 포함하는 `ProjectItem` 요소를 찾습니다.

1. `ProjectItem` 요소의 `ReplaceParameters` 특성을 `true`로 설정합니다.

    ```xml
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>
    ```

## <a name="see-also"></a>참고 항목

[프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)  
[템플릿 매개 변수](../ide/template-parameters.md)  
[Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)  
[ProjectItem 요소(Visual Studio 항목 템플릿)](../extensibility/projectitem-element-visual-studio-item-templates.md)