---
title: '방법: Visual Studio 솔루션에 포함 되지 않은 실행 파일 디버깅 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], executables
- executable files, importing
- executable files, debugging outside of projects
ms.assetid: 3ea176e8-1ce5-42c4-b7a2-abe3a2765033
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e16a938eda683a607dbf7d9418b2a7bd4455a0da
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-debug-an-executable-that-is-not-part-of-a-visual-studio-solution"></a>방법: Visual Studio 솔루션에 포함 되지 않은 실행 파일 디버깅
경우에 따라 프로그램 (.exe 파일) 되지 않은 실행 파일을 디버깅 하려면 수의 일부로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트. 예를 들어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 외부에서 만든 실행 파일이나 다른 사용자로부터 받은 실행 파일이 이러한 경우입니다.  
  
이러한 문제는 일반적으로 Visual Studio 외부에서 실행 파일을 시작하고 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버거를 사용하여 이 파일에 연결하는 방법으로 해결합니다. 자세한 내용은 참조 [실행 중인 프로세스에 연결할](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.  
  
응용 프로그램에 연결하려면 몇 가지 단계를 직접 수행해야 하기 때문에 몇 초 정도 걸립니다. 이러한 약간의 시간 지연으로 인해, 시작할 때 발생하는 문제를 디버깅하려는 경우에는 연결 방법을 사용할 수 없습니다. 또한, 사용자가 입력할 때까지 대기하지 않고 바로 종료되는 프로그램을 디버깅하는 경우에는 프로그램에 연결할 시간이 없을 수도 있습니다. 있는 경우 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 및 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 설치 이러한 프로그램에 대 한 EXE 프로젝트를 만들 수 있습니다.

> [!NOTE]
>  모든 프로그래밍 언어가 EXE 프로젝트를 지원하는 것은 아닙니다.

Visual Studio 솔루션의 일부가 되지 않은 실행 파일을 디버깅 하는 경우 사용할 수 있는 디버깅 기능이 제한 될 수 있습니다, 실행 중인 실행 파일에 연결 하는지 실행 파일을 추가 하는지 여부는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션입니다.

- 따라서, 소스 코드가 있는 경우에는 소스 코드를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]로 가져온 다음 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 실행 파일의 디버그 빌드를 만드는 것이 좋습니다.
- 소스 코드가 없는 및 없이 실행 파일이 빌드된 경우 [디버그 정보](../debugger/how-to-set-debug-and-release-configurations.md) 호환 형식으로 사용할 수 있는 디버깅 기능이 매우 제한 됩니다. 
  
### <a name="to-create-an-exe-project-for-an-existing-executable"></a>기존 실행 파일에 대한 EXE 프로젝트를 만들려면  
  
1.  에 **파일** 메뉴를 클릭 **열려** 선택 **프로젝트**합니다.  
  
2.  에 **프로젝트 열기** 대화 상자, 드롭 다운 목록을 다음을 클릭은 **파일 이름** 상자의 선택한 **모든 프로젝트 파일**합니다.  
  
3.  실행 파일을 찾아서 클릭 하 여 **확인**합니다.  

    실행 파일이 포함된 임시 솔루션이 생성됩니다.

5.  와 같은 실행 명령을 선택 하 여 실행 파일을 시작 **시작**에서 **디버그** 메뉴.    
  
### <a name="to-import-an-executable-into-a-visual-studio-solution"></a>실행 파일을 Visual Studio 솔루션으로 가져오려면  
  
1.  에 **파일** 메뉴에서 **프로젝트 추가**, 클릭 하 고 **기존 프로젝트**합니다.  
  
2.  에 **기존 프로젝트 추가** 대화 상자, 드롭 다운 목록을 다음을 클릭은 **파일 이름** 선택한 상자의 **모든 프로젝트 파일**합니다.  
  
3.  실행 파일을 찾아 선택합니다.  
  
4.  **확인**을 클릭합니다.  
  
5.  와 같은 실행 명령을 선택 하 여 실행 파일을 시작 **시작**에서 **디버그** 메뉴.    
  
## <a name="see-also"></a>참고 항목  
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)   
 [디버거 보안](../debugger/debugger-security.md)   
 [DBG 파일](http://msdn.microsoft.com/en-us/91e449e9-8b65-4123-960f-2107cd1f1cfd)