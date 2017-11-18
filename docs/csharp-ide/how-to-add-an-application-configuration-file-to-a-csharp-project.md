---
title: "방법: C# 프로젝트에 응용 프로그램 구성 파일을 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords: app.config files, adding to C# projects
ms.assetid: 9caf6bb0-c2fc-4ab6-ba69-bed3b880fbf8
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 097e7a2eac78fe85b2a3ab62d5cdf1fd18908d56
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>방법: C# 프로젝트에 응용 프로그램 구성 파일 추가
응용 프로그램 구성 파일 (app.config 파일)에 C# 프로젝트를 추가 하면 공용 언어 런타임 찾아서 어셈블리 파일을 로드을 사용자 지정할 수 있습니다. 응용 프로그램 구성 파일에 대 한 자세한 내용은 참조 [런타임에서 어셈블리를 찾는 방법을](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)합니다.  
  
> [!NOTE]
>  UWP 앱 app.config 템플릿은 포함 하지 않습니다.
  
 프로젝트를 빌드할 때 개발 환경 자동으로 app.config 파일, 실행 파일의 경우 일치 하도록 복사본의 파일 이름을 변경 합니다. 복사한 다음 복사본 bin 디렉터리에 있습니다.  
  
### <a name="to-add-an-application-configuration-file-to-your-c-project"></a>C# 프로젝트에 응용 프로그램 구성 파일을 추가 하려면  
  
1.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  확장 **설치 됨**, 확장 **Visual C# 항목**를 선택한 후는 **응용 프로그램 구성 파일** 서식 파일입니다.  
  
3.  에 **이름** 입력란 이름을 입력 한 다음 선택에서 **추가** 단추입니다.  
  
     App.config 라는 파일을 프로젝트에 추가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 설정 관리(.NET)](../ide/managing-application-settings-dotnet.md)   
 [구성 파일 스키마](/dotnet/framework/configure-apps/file-schema/index)   
 [앱 구성](/dotnet/framework/configure-apps/index)   
 [방법:.NET Framework 버전을 대상 응용 프로그램 구성](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717)   
 [C#용 Visual Studio 개발 환경 사용](../csharp-ide/using-the-visual-studio-development-environment-for-csharp.md)