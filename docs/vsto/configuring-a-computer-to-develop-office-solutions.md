---
title: "Office 솔루션을 개발할 수 있도록 컴퓨터 구성 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, installing tools
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 9b63b3b495b9cb15ea3e9eeedcecedb3a384f8a0
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="configuring-a-computer-to-develop-office-solutions"></a>Office 솔루션을 개발할 수 있도록 컴퓨터 구성

Microsoft Office용 VSTO 추가 기능 및 사용자 지정을 만들려면 지원되는 버전의 Visual Studio, .NET Framework 및 Microsoft Office를 설치합니다.

|소프트웨어|지원되는 버전|
|--------------|------------------------|
|Visual Studio 2017| 포함 된 모든 버전의 **Office/SharePoint 개발** 작업 합니다.|
|.NET Framework|-.NET Framework 4 이상입니다.|
|Microsoft Office|<ul><li>Office Professional Plus for Office 365를 비롯한 Office의 모든 제품군 버전</li><li>다음의 독립 실행형 응용 프로그램<br /><br /> <ul><li>Excel</li><li>InfoPath(Office 2013 및 Office 2010에만 해당)</li><li>Outlook</li><li>PowerPoint</li><li>프로젝트</li><li>Visio</li><li>Word</li></ul></li></ul><br /> Office의 일부분으로 VBA(Visual Basic for Applications)를 설치해야 합니다. **중요:** 간편 실행 버전의 Office 2010 응용 프로그램 지원 되지 않습니다.|

자세한 설치 단계에 대 한 참조 [하는 방법: Office 솔루션을 개발할 수 있도록 컴퓨터 구성](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)합니다.

## <a name="if-project-templates-dont-appear-or-they-dont-work-in-visual-studio"></a>프로젝트 템플릿이 표시 되지 않거나 Visual Studio에서 작동 하지 않는 경우

지원 되는 버전의 Visual Studio,.NET Framework 및 Microsoft Office를 설치 했는데 하거나 Office 프로젝트 템플릿이 Visual Studio에서 표시 되지 **새 프로젝트** 대화 상자 또는 있습니다, 하나를 사용 하려고 할 때 오류가 표시 다음 사항을 확인 합니다.

- 컴퓨터에 Microsoft Office 개발자 도구를 설치했는지 확인합니다.

     Office 개발자 도구는 Visual Studio의 선택적 구성 요소이지만 보통 Visual Studio와 함께 자동으로 설치됩니다. 설치할 기능을 지정하여 Visual Studio 설치를 사용자 지정하는 경우 설치 중에 **Microsoft Office 개발자 도구** 를 선택하여 도구를 설치해야 합니다.

     이러한 도구가 설치 되어 하려면 Visual Studio 설치 프로그램을 시작 하 고 선택 된 **수정** 단추입니다. **Microsoft Office 개발자 도구** 확인란을 선택하고 **업데이트** 단추를 선택합니다.

- 간편 실행으로 제공 되는 office 버전을 실행 하지는 확인 하십시오. [방법: 컴퓨터의 Outlook이 간편 실행 응용 프로그램인지 확인](http://msdn.microsoft.com/library/office/ff864733(v=office.14).aspx)을 참조하세요.

- Microsoft Office의 버전을 하나만 실행 하 고 있는지 확인 합니다.

그래도 문제가 계속 발생하면 [Additional Support for Errors in Office Solutions](../vsto/additional-support-for-errors-in-office-solutions.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[시작 &#40; Visual Studio &#41;에서 Office 개발](../vsto/getting-started-office-development-in-visual-studio.md)  
[방법: Office 솔루션을 개발할 수 있도록 컴퓨터 구성](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)  
[방법: 재배포 가능한 Visual Studio Tools for Office 런타임 설치](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)  
[방법: Office 주 Interop 어셈블리 설치](../vsto/how-to-install-office-primary-interop-assemblies.md).  
[Office 응용 프로그램 및 프로젝트 형식에 따라 사용 가능한 기능](../vsto/features-available-by-office-application-and-project-type.md)
