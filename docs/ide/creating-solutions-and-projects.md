---
title: "솔루션 및 프로젝트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 03/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.openprojectfromweb
- vs.newproject
- VS.ToolsOptionsPages.Projects.General
- SolutionItemsProject
helpviewer_keywords:
- solutions [Visual Studio], deleting
- solutions [Visual Studio], creating
- projects [Visual Studio], creating
ms.assetid: 836f8ca0-3fc9-4f4b-9090-45f2e4d2e9c8
caps.latest.revision: 46
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: 9a4b04dc59c409a5c68ad1fb376abb33b3859ff6
ms.contentlocale: ko-kr
ms.lasthandoff: 05/24/2017

---

# 솔루션 및 프로젝트 만들기
<a id="create-solutions-and-projects" class="xliff"></a>

프로젝트는 응용 프로그램 빌드에 필요한 모든 항목에 대한 논리적 컨테이너입니다. 주 메뉴에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 프로젝트를 만드는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 프로젝트가 포함될 솔루션을 만듭니다. 그런 다음 필요한 경우 새 프로젝트나 기존 프로젝트를 솔루션에 더 추가할 수 있습니다. 기존 코드 파일에서 프로젝트를 만들 수 있으며 작업을 마쳤을 때 삭제될 임시 프로젝트(.NET만 해당)를 만들 수 있습니다.

> [!NOTE]
>  이 항목의 설명은 Visual Studio Community 버전을 기반으로 합니다. 표시되는 대화 상자 및 메뉴 명령은 설정 또는 Visual Studio 버전에 따라 여기에 설명된 내용과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

## 설치된 프로젝트 템플릿에서 프로젝트 만들기
<a id="create-a-project-from-an-installed-project-template" class="xliff"></a>  
 주 메뉴에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 [새 프로젝트] 대화 상자를 표시합니다. **설치됨**, **템플릿** 아래 왼쪽 창에서 프로그래밍 언어 및 플랫폼이나 기술을 선택한 다음 가운데 창의 사용 가능한 템플릿에서 선택합니다.  

 **새 프로젝트** 대화 상자의 **솔루션** 드롭다운에서는 새 솔루션 또는 기존 솔루션이나 Visual Studio의 새 인스턴스에서 새 프로젝트를 만드는 옵션을 제공합니다.  

## 기존 코드 파일에서 프로젝트 만들기
<a id="create-a-project-from-existing-code-files" class="xliff"></a>  
 느슨한 소스 파일 컬렉션이 있는 경우 파일을 포함하는 프로젝트를 쉽게 만들 수 있습니다. **파일**, **새로 만들기**, **기존 코드의 프로젝트**를 선택하여 **기존 코드 파일에서 프로젝트 만들기** 마법사를 시작하고 프롬프트를 따릅니다.  

> [!TIP]
>  이 옵션은 상대적으로 간단한 파일 컬렉션에 적합합니다.  

## 임시 프로젝트 만들기(C# 및 Visual Basic)
<a id="create-a-temporary-project-c-and-visual-basic" class="xliff"></a>
 임시 프로젝트로 작업하면 디스크 위치를 지정하지 않아도 .NET 프로젝트를 만들고 사용할 수 있습니다. 프로젝트를 만들 때 프로젝트 형식 및 템플릿을 선택하고 **새 프로젝트** 대화 상자에서 이름을 지정하면 됩니다. 임시 프로젝트로 작업하는 동안 언제든지 프로젝트를 저장하거나 삭제할 수 있습니다.  

## .NET Framework의 특정 버전을 대상으로 하는 .NET 프로젝트 만들기
<a id="create-a-net-project-that-targets-a-specific-version-of-the-net-framework" class="xliff"></a>  
 **새 프로젝트** 대화 상자의 맨 위에 있는 **.NET Framework** 버전 드롭다운 메뉴를 사용하여 이전 버전의 .NET Framework를 대상으로 하는 프로젝트를 만들 수 있습니다. 해당.NET Framework 버전과 호환되는 템플릿만 목록에 표시되므로 프로젝트 템플릿을 선택하기 전에 이 값을 먼저 설정합니다.  

 4.0 이전 버전의 프레임워크에 액세스하려면 시스템에 .NET Framework 3.5가 설치되어 있어야 합니다.  

## 샘플 솔루션 다운로드
<a id="download-sample-solutions" class="xliff"></a>  
 Visual Studio를 사용하여 Git 리포지토리와 같은 소스뿐 아니라 [MSDN 코드 갤러리](http://go.microsoft.com/fwlink/?LinkId=254185)에서 샘플 솔루션을 다운로드한 후 설치할 수 있습니다.

 샘플을 개별적으로 다운로드하거나 기술 또는 항목을 공유하는 관련된 샘플을 포함하는 샘플 팩을 다운로드할 수 있습니다. 소스 코드 변경 내용이 다운로드하는 샘플에 게시되는 경우 알림을 받게 됩니다.  

 자세한 내용은 [Visual Studio 샘플](../ide/visual-studio-samples.md)을 참조하세요.  

## 솔루션 수준에서 단일 파일 추가
<a id="add-single-files-at-the-solution-level" class="xliff"></a>  
 경우에 따라 여러 프로젝트에서 참조하거나, 특정 프로젝트가 아니라 논리적으로 솔루션 수준에 속하는 텍스트 또는 기타 데이터를 포함하는 파일이 있습니다.  솔루션에 단일 항목을 추가하려면  

- **솔루션 탐색기**에서 솔루션 노드를 마우스 오른쪽 단추로 클릭하고 **추가**, **새 항목** 또는 **추가**, **기존 항목**을 선택합니다.  

## 빈 솔루션 만들기
<a id="create-empty-solutions" class="xliff"></a>  
 프로젝트가 솔루션에 위치할 수 있지만 프로젝트가 없는 솔루션을 만들 수도 있습니다. 또한 솔루션이 필요 없이 코드 프로젝트를 열 수도 있습니다.

#### 빈 솔루션을 만들려면
<a id="to-create-an-empty-solution" class="xliff"></a>  

1.  **파일** 메뉴에서 **새로 만들기**, **새 프로젝트**를 차례로 선택합니다.  

2.  왼쪽 창의 확장된 목록에서 **설치됨**, **기타 프로젝트 형식**, **Visual Studio 솔루션**을 선택합니다.  

3.  가운데 창에서 **빈 솔루션**을 선택합니다.  

4.  솔루션의 **이름** 및 **위치** 값을 설정하고 **확인**을 선택합니다.  

빈 솔루션을 만든 후 **프로젝트** 메뉴에서 **새 항목 추가** 또는 **기존 항목 추가**를 선택하여 새 프로젝트나 항목 또는 기존 프로젝트나 항목을 추가할 수 있습니다.

### 솔루션 삭제
<a id="delete-solutions" class="xliff"></a>  
 솔루션을 영구적으로 삭제할 수 있으나 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 삭제하지는 않습니다. 솔루션을 삭제하기 전에 다른 솔루션에서 다시 사용할 수도 있는 프로젝트를 모두 이동합니다. 그런 다음 파일 탐색기를 사용하여 .sln 및 .suo 솔루션 파일이 포함된 디렉터리를 삭제합니다.  

> [!NOTE]
>  .suo 파일은 파일 탐색기의 기본 설정으로는 표시되지 않는 숨김 파일입니다.  

##### 솔루션을 삭제하려면
<a id="to-delete-a-solution" class="xliff"></a>  

1.  **솔루션 탐색기**에서 삭제하려는 솔루션의 상황에 맞는 메뉴에서 **파일 탐색기에서 폴더 열기**를 선택합니다.

2.  파일 탐색기에서 한 수준 위로 이동합니다.

3.  솔루션을 포함하는 디렉터리를 선택한 다음 DELETE 키를 누릅니다.

## 참고 항목
<a id="see-also" class="xliff"></a>  
 [솔루션 및 프로젝트](../ide/solutions-and-projects-in-visual-studio.md)   

