---
title: "방법: 플랫폼을 대상으로 한 프로젝트 구성 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project settings [Visual Studio], targeting platforms
- platforms, targeting specific CPUs
- project properties [Visual Studio], targeting platforms
- projects [Visual Studio], targeting platforms
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- CPUs, targeting specific
- 64-bit applications [Visual Studio]
ms.assetid: 845302fc-273d-4f81-820a-7296ce91bd76
caps.latest.revision: 13
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: c730f161ed0a38c94362d63544af1c5f3794d985
ms.contentlocale: ko-kr
ms.lasthandoff: 05/13/2017

---
# <a name="how-to-configure-projects-to-target-platforms"></a>방법: 플랫폼을 대상으로 한 프로젝트 구성
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 64비트 플랫폼을 비롯하여 다양한 플랫폼을 대상으로 하는 응용 프로그램을 설정할 수 있습니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 64비트 플랫폼 지원에 대한 자세한 내용은 [64비트 응용 프로그램](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)을 참조하세요.  
  
## <a name="targeting-platforms-with-the-configuration-manager"></a>구성 관리자에서 대상 플랫폼 지정  
 **구성 관리자**는 프로젝트의 대상이 될 새 플랫폼을 신속하게 추가할 수 있는 방법을 제공합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 포함되어 있는 플랫폼 중 하나를 선택하면 프로젝트의 속성이 선택된 플랫폼에 맞는 프로젝트를 빌드하도록 수정됩니다.  
  
#### <a name="to-configure-a-project-to-target-a-64-bit-platform"></a>64비트 플랫폼을 대상으로 하는 프로젝트를 구성하려면  
  
1.  메뉴 모음에서 **빌드**, **구성 관리자**를 선택합니다.  
  
2.  **활성 솔루션 플랫폼** 목록에서 대상으로 지정할 솔루션으로 64비트 플랫폼을 선택한 다음 **닫기** 단추를 선택합니다.  
  
    1.  **활성 솔루션 플랫폼** 목록에 원하는 플랫폼이 없는 경우 **새로 만들기**를 선택합니다.  
  
         **새 솔루션 플랫폼** 대화 상자가 나타납니다.  
  
    2.  **새 플랫폼 입력 또는 선택** 목록에서 **x64**를 선택합니다.  
  
        > [!NOTE]
        >  구성의 새 이름을 지정한 경우 **프로젝트 디자이너**에서 설정을 수정하여 올바른 플랫폼을 대상으로 지정해야 합니다.  
  
    3.  현재 플랫폼 구성에서 설정을 복사하려면 해당 설정을 선택한 다음 **확인** 단추를 선택합니다.  
  
 64비트 플랫폼을 대상으로 하는 모든 프로젝트의 속성이 업데이트되고 프로젝트의 다음 빌드가 64비트 플랫폼에 최적화됩니다.  
  
## <a name="targeting-platforms-in-the-project-designer"></a>프로젝트 디자이너에서 대상 플랫폼 지정  
 프로젝트 디자이너에서도 프로젝트에 대해 여러 플랫폼을 대상으로 지정하는 방법을 제공합니다. 사용자의 솔루션에 대해 **새 솔루션 플랫폼** 대화 상자의 목록에 있는 플랫폼 중 하나를 선택할 수 없는 경우, 사용자 지정 구성 이름을 만들고 **프로젝트 디자이너**에서 원하는 플랫폼을 대상으로 하도록 설정을 수정할 수 있습니다.  
  
 사용하고 있는 프로그래밍 언어에 따라 이 작업이 다르게 수행됩니다. 자세한 내용은 다음 링크를 참조하세요.  
  
-   [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 프로젝트의 경우 [/platform(Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform)을 참조하세요.  
  
-   [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 프로젝트의 경우 [프로젝트 디자이너, 빌드 페이지(C#)](../ide/reference/build-page-project-designer-csharp.md)를 참조하세요.  
  
-   [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 프로젝트의 경우 [/clr(공용 언어 런타임 컴파일)](/cpp/build/reference/clr-common-language-runtime-compilation)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [빌드 플랫폼 이해](../ide/understanding-build-platforms.md)   
 [/platform(C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option)   
 [64비트 응용 프로그램](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)   
 [Visual Studio IDE 64비트 지원](../ide/visual-studio-ide-64-bit-support.md)
